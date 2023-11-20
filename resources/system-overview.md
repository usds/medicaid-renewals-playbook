# The Shape of Eligibility Systems

It can be helpful to undertand the general shape of the systems that you will be intereacting with. There is much variation in capability, acrhtiecture, and even nomenclature across states and vendors. This document tried to capture some generalities.

## System Overview
At the widest perspective the Medicaid eligibility system includes a number of interconnected components: a datastore, a system implementing the business logic of the program, often a separate “rules engine” that implements the business logic specific to eligibility determinations, connections to a variety of state and federal data sources, a system for generating notifications across a range of media, a number of specialized user interfaces for different audiences, and a mechanism for generating reports and dashboards.

These systems process and store both PII and PHI, which adds additional constraints to their design.

<div align="center">
  <img width="500px" src="/images/system_diagram.svg" alt="block diagram of a medicaid elgibility system including web portals, buisness logic, rules engines, and data sources" />
</div>

### User Portal
Narrowly: a set of web pages where the beneficiary can: learn about the program, apply for benefits, check progress of their case, respond to requests for information, provide information about change of circumstances events, learn about successful renewals, or complete a manual renewal.

More broadly, the (potential) beneficiary can interact with the system in many other ways including US mail, text messages, phone-based customer support, in-person customer support from state or county staff, and in-person support from officially designated navigators.

Responses to request for information might involve filling out an electronic form, or uploading photos or scans of a document via the user portal, or submitting physical documents via drop box, US Mail, or even fax.

There are often requirements for the portal to verify the identity of the user. This may be outsourced to a commercial service, or  to a state-wide login service that includes a guarantee of verification. ID verification is often a significant hurdle for beneficiaries and care should be taken to carefully understand what functions of the interface require the highest levels of authentication. This issue becomes particularly salient in cases where families may be changing composition due to separation, divorce, or domestic abuse. The unhoused and recent immigrants are also groups that are disproportionately harmed by overzealous authentication and identity proofing requirements. 

### Eligibility Worker Portal
The super-user interface. Used by state employees to update information in beneficiary files, terminate coverage, extend coverage, finalize manual renewals: everything.

Uploaded documents may appear in this interface or a separate one. Often the eligibility worker must manually copy information from scanned physical forms into the system.

Typically, only certain eligibility staff have the permissions to make changes to cases. Vendor or contractor staff, such as call center workers, will have a reduced access view of the system through this portal.

In a task-based workflow, eligibility workers may be assigned, either manually or automatically, "tasks" that should be completed either in pre-determined amount of time or as soon as feasible. The portal should display the tasks assigned to the logged-in worker.

In a case-based workflow, eligibility workers have a number of "cases", representing households, that they are responsible for managing. The portal should display the cases assigned to the logged-in worker.

### Navigator Portal
Navigators are not state employees, but the navigator role is federally recognized. They are often non-profit employees paid through grants to provide direct assistance to beneficiaries in their communities. The navigator portal allows the navigator to see limited information about the state of cases assigned to them and to take limited actions on behalf of the user related to applying for and renewing eligibility.

Rather than being an limited view of the **Eligibility Worker Portal**, it is often a separate interface, where it exists.

Transferring access between navigators or navigator organizations often requires manual intervention by a call center worker.

### Datastore
Schema and architectural decisions in the datastore end up being major roadblocks to implementing policy changes.

Particularly problematic is the common problem of deeply encoding notions of household membership into the data structures. Individuals must be adjudicated individually, but the input to those decisions often are drawn from household members: in particular household income. Systems will often store information linked to the household, including eligibility, making it impossible to represent individual eligibility, or put another way, impossible to represent households with mixed eligibility.

Systems that must support many Medicaid-like programs, which we call _vertically-integrated_, must be able to represent program membership (i.e., Medicaid, CHIP, Basic Health, Essential Heath, Qualified Health Plan) and even different eligibility end dates at the individual level. Despite this they can still make the mistake of storing components of eligibility as part of the household representation.

Systems that must support Medicaid alongside SNAP and other non-CMS benefit programs, which we call _horizontally-integrated_,  must somehow accommodate conflicting definitions of household membership. You might expect that these systems would do better at representing individual eligibility, but the data does not support that expectation.

Our observations seem to indicate that the datastores used in Medicaid eligibilty systems lack abstraction layers necessary to isolate the details of the database schema from the requirements of the policies.

#### Performance 
The largest systems have tens of millions of beneficiaries and would ideally be able to batch process a month of renewals in a single day. Observed systems often batch monthly jobs into chunks processed across several days of the first week of the month.

### Application Servers
These could be services or batch jobs run on a schedule. For example, the frontend services for the various portals should exist as separate jobs that integrate directly with the datastore. But these services will share a common structure: responding to some trigger, possibly gathering information from various sources, and possibly performing a mutation on the datastore. As such they will likely be built on a common infrastructure supporting specific application logic.

**Portal services** discussed above, are from a technical perspective bread-and-butter web frontends: serving static content, interfacing with authentication services, serving information from the datastore, mutating the datastore.

**Data ingestion jobs** are scheduled to pick up batch data from sources and update the datastore with new information. This might include picking up scans of documents from a drop box and attaching them to cases, or assigning them to a task queue.

**Renewal jobs** are a special form of scheduled job that pull data for individuals matching some criteria (usually those with eligibility end dates some fixed number of days in the future), evaluating that information according to plan rules, and writing determinations back to the datastore. It seems to often be the case that these jobs do not communicate to the datastore directly but expect a bundle of data to be attached to each individual before the run as part of the selection process. This selection and bundling process often seems to be fragile, with failures or inconsistencies encountered during this process causing individuals to be needlessly excluded from further automatic processing.

**Notification jobs** pull data for individuals or households in a given state and generate notifications. These could be text messages, or emails, or even paper notices sent by US Mail. Renewal jobs often have the side effect of triggering these notifications directly. Sometimes they are implemented as separate jobs which facilitates policy changes that might require temporarily delaying or even canceling the delivery of a notice. The output of these jobs aften flow to vendors who run the actual mail room, SMS interfaces, or call centers.

**Reaper Jobs** scan for individuals who have failed to respond to a request for information within the allowed time and disenroll them from the program. These are a common source of detritus in the backlog. During normal operations an unanswered request would result in disenrollment and case closure. Continuous eligibility during the public health emergency resulted in those cases remaining enrolled and open. The changes to implement continuous eligibility in 2020 rarely seemed to include a plan for dealing with these stale notices. Very often the existence of a pending request will exclude individuals or entire households from automatic eligibility determination, even if the request is no longer irrelevant, or only relevant to a particular individual or a non-Medicaid program. The stale requests go by many names: flags, clocks, tasks.

### Data Sources
Most sources will be required for both application and renewal. Often data sources will specify a real time API for applications to facilitate low-latency responses to user interaction on a portal, and a batch interface to allow for renewal operations to avoid overloading the real-time API.

The federal Data Hub provides proxy interface to a number of data sources:
-	Social Security Administration for SSN validation, SSDI, and deaths
-	Internal Revenue Service for income and household composition
-	Department of Labor for unemployment insurance income
-	The Work Number for income
-	Department of Homeland Security for immigration status
-	Interstate exchange for cross-enrollment
-	National Change of Address 

Some states maintain separate interfaces to these services instead of using the Hub.

These services, including those proxied via the Hub do not cache results, and fee-based services may bill for each query. Client-side caching and rate limiting are therefore very important. Data source interfaces should be configured to never make the same query within a source-specific lock out time after a successful response has been received. However, it is rare to observe these limitations or caches in real systems.

Some sources may need to be polled periodically to detect Life Status Change events such as moving across state lines, getting or losing a job. These events can trigger notifications requesting more information.

Horizontally-integrated systems will need to determine the appropriate schedule for each data source based on beneficiary membership. Data collected for one benefit program may trigger life change events for other programs.

### Rules Engine
This is where program eligibility policy belongs. The name “rules engine” isn’t intended to imply a specific implementation, it is a functional definition of the module that evaluates the rules and determines eligibility. The rules engine never disenrolls an individual. During application it returns “Eligible” or “Ineligible”. During renewal it returns “Ex Parte Renewal” or “Manual Renewal”. The set of rules that are evaluated at renewal time is a subset of rules that are run at application.

In the Medicaid context we often see two-stage systems where there is an accretion of pre-filters that exclude individuals (or even whole households) from being considered by the rules engine proper during renewal. Often these exclusions paint with a broad brush, excluding a wide swath of beneficiaries from consideration for the purpose of excluding a small set of (often hypothetical) individuals that might be improperly renewed by the engine.

Some systems are coded by hand, others ingest a description of the rules (i.e. an XML document) into an off-the-shelf evaluation engine.

Typically, the rules engine will not have side effects: it won’t call out to services or mutate datastores directly. A process will collect data about an individual and present it to the rules-engine, collecting the decision and performing actions in response.

It is essential for the rules engine to explain itself. It should generate an audit log with each eligibility decision is recorded along with the set of rules that were evaluated during the determination and the finding of each rule. This is also important information to provide in the case file, but an additional audit log will be useful for test runs, or experiments run outside production.

### Audit and Metrics Logs
As mentioned above, the rules-engine should be extensively logged with detailed information about decisions made. These logs are often valuable for focusing attention on parts of the system that are casing inefficencies or errors that would otherwise go unnoticed.

Each action taken by a human on the portal, or by a job, should generate a detailed log. These logs are useful for understanding the overall performance of the system. Understanding how many people are tencountering each stage of the manual renewal process informs the funnel analysis and similarly focuses attention of teams attempting to make improvements.

## System Heredity
The most common situation we observed was a system that had been hard forked from an existing system in another state. There was no indication of patches being up-streamed for other states to benefit from. The systems in this hereditary model slowly diverge, introducing unique bugs as they all create bespoke solutions to common problems, such as new CMS guidance.

We have observed systems where there was a common code base that pushed updates down to the client states. However, it was not clear to us what value was being delivered via those updates. The majority of the policy implementation seemed to be in locally produced code that overrode the off the shelf implementation, with some set of core generic operations supplied by the underlying grey box system. 
