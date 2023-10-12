# Individual VS Household Determinations

## Description

Medicaid determinations should be made at the _individual_ level, meaning that individuals within the same household may have different determination statuses. Unfortunately, many states determine eligibility at the household level, meaning individuals who may be eligible are "swept up" in the determination of the household as a whole.

## What this looks like

States were required to self-report this issue to CMS; however, there may be additional symptoms of the issue.

Some signs this may be happening:
- Data is only available at the case or account level.
- A flag on one person in the case blocks (or excludes) an entire case from moving forward. 
- A case uses the lowest income threshold available for MAGI determinations.
- Mixed cases (MAGI and non-MAGI) are excluded from ex parte.

## Potential solutions

Sandbox solution:
  - Prior to a month's renewal run, setup a sandboxed environment
  - Load production data to simulate the current production environment
  - Run eligibility for a month of data
  - Using a script or query, determine individuals who were incorrectly terminated during that run
  - In the _real_ production environment, pre-emptively renew these individuals before running that month's eligibility

Notice solution:
  - Run ex parte as normal. If anyone in the household fails renewal, send the household a renewal packet
  - If the packet DOES NOT come back:
    - Renew anyone on the case who would have been successfully renewed at ex parte
    - Terminate anyone on the case who needed more information
  - If the packet DOES come back:
    - Use the packet to renew (or terminate) members of the household based on the new information
