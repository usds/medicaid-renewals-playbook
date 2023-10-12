# Waiver Implementation Issues

## Description

CMS has provided flexibility for states to perform ex parte renewals through the [1902(e)(14)(a)](https://www.medicaid.gov/resources-for-states/coronavirus-disease-2019-covid-19/unwinding-and-returning-regular-operations-after-covid-19/covid-19-phe-unwinding-section-1902e14a-waiver-approvals/index.html) process. However, many states may have struggled with the implementation of these waivers, or may not have the most efficient implementation possible.

Waivers that states may be struggling with:
  - *100% FPL Waiver*: Anyone with a verified income less than 100% FPL can be renewed if there's no data available from electronic sources.
  - *0% FPL Waiver*: Anyone with a verified income at 0% FPL can be renewed if there's no data available from electronic sources.
  - *SNAP/TANF Categorical Eligibility*: Anyone receiving SNAP or TANF is not subject to an income test.
  - *Removal of asset test*: Assets are no longer a consideration for eligibility.

## What this looks like

In some states, the implementation of these waivers may be manual (meaning that eligibility workers are determining who falls under these rules). This process is often inefficient and can lead to a backlog of individuals to be verified.

When the implementation is automatic, the new logic may be at the _end_ of the renewal, meaning that there are logic and checks being run prior to the waiver logic being run. This may result in a person being excluded before they get the chance to be considered for the waiver logic.

A key sign that the implementation may be inefficient is a mismatch between estimates and measurements. Ask the state: how many people did we estimate to be caught by this logic? Ask the vendor: how many actually were? Are the numbers close?

## Potential solutions

In states where waivers are implemented manually, explore the opportunity to automate.

In states where waivers may be implemented inefficiently, recommend they be optimized by moving them up in the renewal process or expanding them to the largest group possible.
