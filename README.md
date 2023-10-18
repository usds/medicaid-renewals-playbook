<a name="top"></a>

<div align="center">
  <img
    width="300px"
    src="./images/usds-logo.svg"
    alt="The US Digital Service shield logo">
  </img>

  # [DRAFT] U.S. Digital Service - Medicaid Renewals Playbook 
</div>

## Background

This playbook was created by the U.S. Digital Service as a rapid-response guide for civic technologists providing direct technical assistance to states during the COVID-19 Public Health Emergency (PHE) Unwinding. The content in this playbook focuses on strategies to rapidly decrease the burden of Medicaid renewals on members of the public and state staff.

**_This playbook is **NOT** a source of authoritative, legal, or regulatory guidance and has not been officially endorsed by the Center for Medicaid and CHIP Services (CMCS). It is advisory only, and should be adapted appropriately for each state and scenario. Ultimately, it is the responsibility of state Medicaid officials to ensure that implementation of any project is compliant with federal Medicaid statute and regulations. Refer to CMCS's [website](https://www.medicaid.gov/resources-for-states/coronavirus-disease-2019-covid-19/unwinding-and-returning-regular-operations-after-covid-19/index.html) for up to date official guidance._**

Please contribute to this repository with your questions or additions. To do so, check out [our contributing guide](./CONTRIBUTING.md)!

### Table of contents

[Framing](#framing)

Plays and resources:
1. [Establish Trust and Urgency](#play-1)
2. [Identify Problems](#play-2)
3. [Generate Solutions](#play-3)
4. [Prioritize and Implement](#play-4)

Common opportunities:
- [Common Ex Parte Opportunities](./ex-parte-renewals)
- [Common Manual Renewal Opportunities](./manual-renewals)

---

<a name="framing"></a>
## Advice on Framing

As civic technologists jumping in to support states, it is important that teams are clear on the **framing** of their work. Without a clear well-messaged offerings state partners won't understand - and won't invest in - the team.

- **Close the gap between policy and implementation** - Most states have adopted helpful policy postures for the unwinding period and have a broad range of flexibilities that should make renewals more seamless for beneficiaries. States are proud of and have conviction in the work that they have done to rapidly adopt these policy wins. Unfortunately, many of these policies remain on paper only and have not been implemented in systems and optimized to have the maximum impact for beneficiaries. As civic technologists, we are here to help states realize the goals of their good policy making through implementation and delivery support. 
- **Deliver actionable recommendations.** - State Mediciad eligibility systems are inefficient in 100s of ways and states already have a list of existing priorities a mile long. Layered on top of these long standing challenges is the enormous task of Medicaid unwinding. Today, states are not interested in more to-dos or complex journey maps. States need analysis and recommendations that will make a big difference for them **now**. If there is long-term work to be done that is uncovered, we  bring that to light when possible, but our focus is on the improvements that can be made quickly and will minimize burden on already overwhelmed state staff. 
- **Start with the known priorities** - States are reporting metrics like ex parte rate and procedural terminations, which are highly scrutinized right now. States are also hearing directly from their eligibility worker staff about the enormous workload that they are experiencing. As civic technologists, we should focus first on the data analysis and recommendations that get at the core of these well-known concerns and identify the low hanging fruit opportunities that will rapidly improve outcomes for beneficiaries, eligibility workers, and state staff. Outside of these outcomes, one state priority that civic technologists _**should not**_ weigh in on (unless explictly asked to) is system legal compliance. 
- **Make the state the hero.** - In all cases, the state has the final say on what is most helpful in a crisis and civic technologists are here to surge capacity to deliver outcomes rapidly. Civic technologists can assist with rapid recommendations and steer implementation, but ultimately existing state vendors will be the ones committing lines of code. The process defined in this playbook has served previous engagements well, but ultimately we should follow the state's lead to determine what activities are best suited for the time that they're investing. 

[Back To Top](#top)

---

## Plays

<a name="play-1"></a>
### 1. Establish Trust and Urgency

It's crucial to establish a relationship of trust and clear expectations with state partners at the beginning of the project. Every stage of the process is predicated on an open exchange of details and data about how systems are performing.

In addition, all members of the team -- including vendors -- must understand the urgency and criticality of the project. Leadership should be engaged regularly from the beginning, and the work should be made a top priority. Common goals should be established at the beginning of the project so that everyone understands what success looks like.

* **Keep states' needs top of mind.** States are under an immense amount of pressure right now. Be mindful of the amount of work state staff have on their plates, celebrate the great work they're already doing, and focus the scope of work around the most urgent needs.
* **Orient the team towards OUTCOMES, not compliance.** Establish common goals with state partners to rapidly alleviate burden on the public and state staff. Discuss norms around confidentiality and information sharing about the project.
* **Get buy-in from senior leadership, including the [State Medicaid Director](https://medicaiddirectors.org/wp-content/uploads/2023/06/Public_DirectorsList_June2023-1.pdf) and Deputy Director.** Establish this work as the top priority for the team.
* **Convene a cross functional group** of subject matter experts and decision makers, including Policy, Communications, Human-Centered Design and Technical experts across state staff and vendor teams.
* **Determine one or two North Star(s).** What goals are we specifically working towards? These should be measurable (“increase automatic renewals to XX%”) but don't have to be numeric (“stand up an online renewal form”).
* **Adopt terminology from the state.** For example, if a "renewal" is called a “review” in the state, this term should be used throughout the project. 
* **Go where the work is.** Travel to where your state partners and their Medicaid members are. This establishes urgency for the work, builds rapport, and creates momentum around generating solutions and decision-making.

#### Resources
Guides
  * [Medicaid 101](./resources/medicaid-101.pdf): A _brief and informal_ overview of the Medicaid program. This presentation **should not** be taken as legal authority or advice, but used as a quick introduction to the program.

Templates
 * [Project Charter](./resources/example-project-charter.docx): An example charter used to establish the goals, dates, and activities of the engagement between the civic tech organization and the state health and human services agency.
 * [On-Site Schedule](./schedule.md): An example schedule for the week of the on-site engagement. Work typically begins virtually 3-4 weeks prior and 3-4 weeks following, but the on-site week is typically the most impactful and intense period of work.

Workshops
  * [Kickoff Meeting](./workshops-and-meetings/kickoff.md): Sample agenda and materials for the project kickoff, where state staff and the full team align on goals, norms, and the work moving forward.
  * [Hypothesis Generation Workshop](./workshops-and-meetings/hypothesis-generation-workshop.md): Sample agenda and materials for a workshop focused on generating hypotheses on where the team could have the biggest impact.

---

<a name="play-2"></a>
### 2. Identify Problems

Working with the state and external partners, determine the largest sources of administrative burden and churn during renewal. Where are people being moved from automatic renewal to manual renewal? Where are people struggling or falling off when completing a renewal? What methods are most commonly utilized, and what are the biggest problems with those methods?

When determining the problems, it's important to keep the focus on the “end-to-end” renewal process. An ex parte attempt is only the first step in a person's renewal. For the millions of people manually renewing, there are vast opportunities to improve the experience and increase renewal rates.

* **Pull the numbers.** Pull end-to-end funnel data, including where drop-offs occur at each step in the renewal process. Pull ex parte failure reasons, and organize by the number of people impacted. Pull web traffic numbers to understand how people are accessing online renewal materials.
* **Be a renewer.** Put your renewer hat on and do some Googling to figure out how to renew Medicaid in your state. Do this on mobile, record screenshots as you go, and note pain points throughout the process. Call customer support when you get stuck, take notes on the interactive voice response (IVR) and overall experience.
* **Learn from experts.** Meet with Navigators and eligibility workers to identify top challenges across the renewal process that members of their community experience. Meet in smaller groups with state SMEs and decision makers to better understand the challenges they've been dealing with.
* **Map the experience.** Map a high-level user journey of the end-to-end renewal experience, noting common pain points and workarounds. Use this journey map to target the focus of your interventions to specific and achievable areas.
* **Don't split the party.** Approach the system from a holistic, human-centered perspective; don't separate into siloed engineering, policy, design, or research teams. Those responsible for ex parte policy and systems changes may not have had the opportunity to meet with eligibility workers to understand how they process a renewal, necessary context for identifying root causes of ex parte failures. Common challenges reported by Navigators highlight not only opportunities to improve the manual renewal process, but also opportunities for ex parte logic changes. 


#### Resources
Guides
  * [Navigator Research Guide](./resources/navigator-research-guide.docx): Working with [Navigators](https://www.healthcare.gov/glossary/navigator/) is crucial for the success of renewals work. This guide provides a set of resources for explaining, justifying, preparing, and performing work with Navigators. It includes background information on Navigator organizations, example research plans, and email templates for correspondence.

Templates
  * [Data Request Worksheet](./resources/data-request-worksheet.xlsx): A worksheet that can be used by the state to begin measuring their end-to-end renewal funnel. Some states will not be able to fill out all fields in the template; that's okay! This template can and should be adapted for the particular state.
  * [State Renewals Funnel](https://app.mural.co/t/usdigitalservice0135/m/usdigitalservice0135/1697032143290/0ae29a54efb9ed41a03dbba35e11e7eba60cfa1e?sender=u46dc9256beb1576a38081536): A method for visualizing the end-to-end funnel of Medicaid renewals, and determining which drop-off points are the most critical to focus on.
  * [Renewal Journey Map](https://app.mural.co/t/usdigitalservice0135/m/usdigitalservice0135/1697052445632/f3f79359e57b77d23f41d325a131b736c5740263?sender=u46dc9256beb1576a38081536): A method for mapping a member's renewal journey from start to finish. This can be used throughout the investigation and research process for determining challenges and opportunities for improvement.

Workshops
  * [Navigator Workshop](./workshops-and-meetings/navigator-workshop.md): Typically, at the beginning of the week, we hold a convening of Navigators focused on generating potential solutions.
  * [Ex Parte Workshop #1](./workshops-and-meetings/ex-parte-workshop.md): The first ex parte workshop, typically held in the week of the on-site, is focused on identifying opportunities for improvement in the ex parte renewal flow.
  * [Manual Renewal Workshop #1](./workshops-and-meetings/manual-renewal-workshop.md): The first manual renewal workshop, typically held in the week of the on-site, is focused on bringing the experiences and solutions from research with Navigators to the state so that solutioning can begin.

---

<a name="play-3"></a>
### 3. Generate Solutions

Once problems have been identified, work with the broader cross-functional team to start generating solutions. Often times there will be more problems available to solve than possible to talk through in the given time. Start with high-impact and/or low-effort problems, and present them in turn for consideration. Solutions should be high-level, but estimable. Whenever possible, rely on data or similar solutions in other states as evidence that the solution will, in fact, solve the problem.


Whenever possible, scope should be reduced towards the minimum viable solution. When implementation timelines are given, look for reasonable opportunities to reduce estimates and remove unnecessary requirements. Ask for clarity on the stages of implementation, and which are projected to take the most amount of time. Can they be reduced? For example, if a change is completely back-end, eliminate any front-end testing. If a change will only affect mobile users, eliminate desktop testing. If a website is not functional on mobile, change only the pieces to make it functional (as opposed to friendly). Keep asking “why” until the timeline is definitively as small as possible.

* **Use the lived experiences of experts.** If the team was able to meet with Navigators and case workers before a solutioning session with the state, bring their ideas and solutions to the table. Treat these as expert opinions, and champion them whenever possible.
* **Work collaboratively and let states be the heroes.** When solutions are being discussed, the decision makers and implementors should be in the room, driving the process. Give equal weight to everyone's voice, and specifically call out those with on-the-ground knowledge. Empower state policy staff to reconsider assumptions and ask questions about implementation. Pass around artifacts (like a copy of the renewal packet, if available) and let them make changes themselves.
* **Reference Medicaid rules and regulations.** Any solution MUST be palatable to state policy experts, or it cannot be implemented. Whenever possible, use rules and regulations to create a safe policy space for solutioning. If policy concerns are brought up broadly, read the policy and use it to make a risk calculation. A policy may prohibit something, but in practice that situation may never occur; use lived experiences of Navigators and case workers to make that clear. Ultimately, it is up to the discretion of state Medicaid officials to decide what changes are appropriate and it is the role of civic technologists to empower them with all of the data, evidence, and implementation clarity that they need to make well reasoned decisions.
* **Keep asking “why”.** If a timeline doesn't make sense, or seems unrealistic, ask for specifics. If the explanation doesn't make sense, ask for more. We don't need to be the experts on the state systems or processes, but we do need to recognize when a solution isn't as efficient (or impactful) as it can be. “Policy” is often cited as a reason something can't be done; ask for the regulation.
* **Find the minimum viable solution.** Working with the state staff, eliminate parts of the implementation process that are unnecessary. Focus specifically on stages that may are prone to inflation: testing, for example, or administrative processes. Can these stages be reduced? Don't be satisfied until any solution is the smallest viable solution possible. Ask about the emergency release process. Strive to land changes before, rather than just after, any monthly batch run.

#### Resources
Workshops
  * [Ex Parte Workshop #2](./workshops-and-meetings/ex-parte-workshop.md): The second ex parte workshop is focused around implementation details and aligning on potential solutions.
  * [Manual Renewal Workshop #2](./workshops-and-meetings/manual-renewal-workshop.md): The second manual renewal workshop is focused on determining implementation plans and assigning owners to action items.

---

<a name="play-4"></a>
### 4. Prioritize and Implement

There will always be more problems to solve than there are resources available to solve them. State Medicaid teams are overwhelemed with priorities and ongoing work, and providing clarity through data-driven priortization is critical. Driving clear priortization with stakeholders allows the implementation teams to focus correctly on areas with the highest impact and quickest timelines.

The two most important metrics to consider when prioritizing are impact and speed. Impact is typically measured in number of successful renewals per month, while speed is measured in time to implementation. Importantly, these numbers are almost always estimates, and can be very rough; for example, improving the design of a renewal notice may increase the number of successful renewals based on the number of people receiving the notice, but it is difficult to estimate.

Once a set of solutions is prioritized, the state and vendor work together to schedule implementation and begin work. If helpful, play a part in that process as well, taking on roles ranging from advisor to individual contributor.

* **Let the state drive implementation.** States should own and manage the implementation work, and use the civic technology team as much (or as little) as they see fit. Ensure stakeholders are aware of the team's availability, strengths, and connections. If they don't need any extra help, let them do the work!

* **Meet regularly if needed.** If helpful, meet with stakeholders on a regular basis after the engagement. Gauge how well the work is progressing, and where potential roadblocks could occur. Providing basic project management of the priorities that you have agreed to can be a powerful tool. In particular, more junior vendor teams may require coaching if they are being asked to deviate from their usual process.

* **Ask for metrics.** Measuring the impact of the engagement is crucial to ensuring the state and civic technology team's time was well spent. If possible, utilize rigorous methods like A/B testing, pilots, and randomized trials to gather quality data of the effectivity of solutions.

#### Resources
Templates
 * [Example Recommendations Document](./resources/example-recommendations-document.docx): At the end of the on-site week, all recommendations agreed upon by _both the state and the civic technology team_ are documented in this recommendations report, which is then delivered to the state Medicaid leadership.

Workshops
  * [Closing Meeting](./workshops-and-meetings/closing.md): This meeting is typically held at the end of the on-site week. It is an opportunity to present recommendations to the state senior leadership, and re-affirm the agreed upon actions.
  * [Prioritization Session](./workshops-and-meetings/prioritization-session.md): This session can help the state determine which recommendations require immediate action versus long-term changes.
