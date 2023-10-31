# Income data hierarchy

## Description

Generally, states have a "hierarchy" indicating what income data sources are used in which cases to electronically verify an individual's income. Good income hierarchy rules query as many income data sources as needed to renew an individual or case; poor income hierarchy rules may not query as many income data sources as possible, leaving valuable data on the table.

The data sources that often yield the most successful renewals are:
  - Quarterly wage data 
  - State tax data
  - Social Security
  - Private databases
  - Other program data
  - IRS data

### Quarterly wage data

_Quarterly wage data is generally considered to be of **HIGH** usefulness for Medicaid!_

Sometimes referred to as State Wage Information Collection Agency (SWICA), this refers to data reported by employers on a quarterly basis for the purposes of paying unemployment taxes. **NOTE**: This is NOT the same as unemployment income!

Quarterly wage data **MUST** be reported by most employers. There are some exceptions; for example, employers with less than ten employees are exempt in most states. But the majority of employers do report, and as a result, most "W2" employees will have data in these databases. This data source may contain Individual Taxpayer Identification Numbers (ITINs), and could potentially be [a good source of information for recipients without a Social Security Number (SSN)](./social-security-numbers.md).

This data is generally collected and maintained by the state's Department of Labor (or equivalent). Getting access generally requires setting up a data sharing agreement between the two agencies, and then implementing the data exchange.

### State tax data

_State tax data is generally considered to be of **HIGH** usefulness for Medicaid!_

State tax data is income data gathered by the state's Department of Revenue (or equivalent). Often this data is very similar to IRS data, but with much less stringent security requirements. This data source _is very likely_ to contain ITINs, and could potentially be [a good source of information for recipients without an SSN](./social-security-numbers.md). 

Note that not all states have an income tax, therefore this data will not exist for all states.

Getting access to this data generally requires setting up a data sharing agreement between the two agencies, and then implementing the data exchange.

### Social Security

_Social Security data is generally considered to be of **HIGH** usefulness for Medicaid!_

Income from the Social Security Administration (SSA) must be take into account for calculating an income for Medicaid. However, because SSA benefits are paid out for specific circumstances, _they often don't tell the full story_. SSA information is essential to calculating income for Medicaid, but it should be seen as a _supplement_ to other data sources.

SSA information is available through the Federal Data Services Hub (FDSH). Most states should already have access and be using this data.

### Private databases

_Private databases are generally considered to be of **MEDIUM** usefulness for Medicaid._

States may use private income databases for the purposes of validating a person's income on renewal. These databases are, in general, of varying quality with respect to coverage across states; some states may have high coverage (meaning a large portion of the population has data present in the database), while others may have low or nonexistant coverage.

The data contained within private databases are often paystub-level, including precise details like hours worked, deductions, etc.

Cost can be a prohibitive factor in incorporating private databases. Some private data is available through the Federal Data Services Hub (FDSH).

### Other program data

_Data from other programs is generally considered to be of **MEDIUM** usefulness for Medicaid._

Other benefit programs like the Supplemental Nutrition Assistance Program (SNAP) or Temporary Assistance for Needy Families (TANF) collect and verify income data. Once collected and verified, this data can be used in two ways to facilitate a Medicaid eligibility determination:
1. **Use the raw gross income** - In this case, Medicaid uses the gross income collected by another program to make a Medicaid eligibility determination. This is generally easier with a state that has an integrated eligibility system, but can be acheived without one. Note that the incomes must be utilized for _individuals_, not households! Household definitions may be different between programs, so a person's SNAP household income will not be the same as their Medicaid household income.
2. **Use Express Lane Eligibility (ELE) or a waiver** - In this case, simply being on one of these programs qualifies a person for Medicaid; no income data needs to be exchanged, but the person's enrollment must be confirmed. [Express Lane Eligibility](https://www.medicaid.gov/medicaid/enrollment-strategies/express-lane-eligibility-medicaid-and-chip-coverage/index.html) applies to children only. For adults, [an (e)(14)(a) waiver](./waiver-implementations.md) can be utilized to acheive the same result.

Utilizing data from other programs generally requires a data sharing agreement between the two agencies and a data exchange implementation.

### IRS/FTI data

_IRS/FTI data is generally considered to be of **LOW** usefulness for Medicaid._

Tax data collected by the Internal Revenue Service (IRS), also referred to as Federal Tax Information (FTI), is a potential data source for performing Medicaid renewals. FTI is generally older than other data sources, often up to 16 months old. In addition, there are [strict requirements](https://www.irs.gov/pub/irs-pdf/p1075.pdf) around the usage and storage of FTI. These factors can make FTI a difficult data source to incorporate into an eligibility system.

That said, many states can, and do, use IRS data for Medicaid determinations. If a state is interested in using FTI, work with their policy team to determine the circumstances under which they feel comfortable incorporating it.

---

CMS guidance indicates that states should use a **"get-to-yes" strategy** when testing income. This means that if _any_ income data source provides an income that is under the qualifying threshold, then the state should consider the income verified. Some states have chosen to use a more restrictive definition, where multiple (or all) income data sources must agree before determining someone eligible.

Even if the system is described as stepping through data sources one at a time, often the data is queried separately, in the week before the ex parte process is due to be run. Make sure to have a precise understanding of when and why data sources are queried or skipped. Note that some sources charge on a per-query basis: this may be the reason why a system seems to be attempting to optimize for fewer queries over maximum information.

## What this looks like

The state has a large number of people or cases failing ex parte renewal each month for the following reasons:
  - "No income data available"
  - "Skipping income check"
  - "Not querying X for data"
  - "Income source mismatch"
  - "Indeterminate income"
  - "Income data conflict"

## Potential solutions

Describe to the state how best-in-class income verification systems query _all income data sources available_. Question and challenge any logic that excludes certain types of people from certain types of income checks. If the state is not using a "get-to-yes" strategy, cite [the October CMS guidance](https://www.medicaid.gov/sites/default/files/2022-10/ex-parte-renewal-102022.pdf) indicating best practices. Once policy aligned, determine an implementation path forward.

## Resources

- [CBPP: Streamlining Medicaid Renewals Through the Ex Parte Process](https://www.cbpp.org/research/health/streamlining-medicaid-renewals-through-the-ex-parte-process) (Step 2)
