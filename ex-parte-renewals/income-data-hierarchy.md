# Income Data Hierarchy

## Description

Generally, states have a "hierarchy" indicating what income data sources are used in which cases to electronically verify an individual's income. Good income hierarchy rules query as many income data sources as needed to renew an individual or case; poor income hierarchy rules may not query as many income data sources as possible, leaving valuable data on the table.

The data sources that often yield the most successful renewals are:
  - Quarterly wage data (also called SWICA or Department of Labor database; note this is NOT the same as unemployment income)
  - State tax data
  - IRS data
  - Social Security
  - Private databases (e.g., Equifax's The Work Number)

States may also have the ability to query income from other programs like SNAP or TANF.

CMS guidance indicates that states should use a **"get-to-yes" strategy** when testing income. This means that if _any_ income data source provides an income that is under the qualifying threshold, then the state should consider the income verified. Some states have chosen to use a more restrictive definition, where multiple (or all) income data sources must agree before determining someone eligible.

Even if the system is described as stepping through data sources one at a time, often the data is queried deparately, in the week before the ex parte process is due to be run. Make sure to be crisp about when data sources are queried or skipped. Note that some sources charge on a per-query basis: this may be the reason why a system seems to be attempting to optimize for fewer queries over maximum information.

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
