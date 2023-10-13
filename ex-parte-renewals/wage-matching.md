# Wage Matching

## Description

Wage matching is the process in which an person's income is compared against external data sources for verification. This process includes using the reasonable compatibility test, and incorporates any reasonable compatibility threshold the state is using.

While the regulations and guidance are fairly clear around reasonable compatibility, states may be taking an unnecessarily strict stance. The process should be:
  - Compare the income on the account to the person's income threshold
  - Compare the income from the data source to the person's income threshold.
  - If BOTH are *below* the threshold: the two incomes are reasonably compatible, and the person should be renewed.
  - If BOTH are *above* the threshold: the two incomes are reasonably compatible, and the person should be sent a renewal packet.
  - If ONE is above and one is below:
    - If the two values are _within the reasonable compatibility threshold of each other_: the two incomes are reasonably compatible, and the person should be renewed.
    - If the two values are NOT within the reasonable compatibility threshold of each other: the two incomes are NOT reasonably compatible, and the person should be sent a renewal packet.

Within in this process, there are flexibilities. Some states may choose to ignore the stored income completely; this is okay because the stored income will always be below the threshold anyway (since they qualified previously).

However, some states may be taking strategies like:
  - Requiring that the incomes are within a certain distance of each other BEFORE comparing to the threshold
  - Requiring that the incomes have matching employer names
  - Requiring that the case have an income from within the past X months
  - Requiring that all income data sources confirm a source of income

## What this looks like

The following signs may indicate a wage match issue:
  - Errors like "Employer name mismatch"
  - Large numbers of people failing for "reasonable compatibility" errors
  - Errors related to multiple sources of income
  - Errors indicating the stored income data is too old

## Potential solutions

The first step in diagnosing a wage match issue is to ask the state to describe _in detail_ how their wage match process is implemented. Ask the following questions:
  - Do you use stored income when doing wage matching?
  - How old can stored income be?
  - What data sources do you compare against?
  - When do you compare against each data source?
  - How is reasonable compatibility implemented?
  - What's your reasonable compatibility threshold? When does it come into play?

Describe to the state how best-in-class income verification processes do wage matching in the simplest way possible.  Question and challenge any logic that strays outside of these bounds. Cite [the October CMS guidance](https://www.medicaid.gov/sites/default/files/2022-10/ex-parte-renewal-102022.pdf) indicating best practices, and the regulations for definitions of technical terms.
