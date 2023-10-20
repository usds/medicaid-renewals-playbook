# Social Security Number challenges

## Description

States are required to ask for an individual's social security number when they apply for Medicaid, but individuals are **not** required to supply it. In addition, there are large groups of people who may not have social security numbers on file with the Medicaid agency:
  - Children under the age of 3
    - When a child is born, they do not have a social security number right away. Most new births during the public health emergency were not followed up on in order to obtain an SSN.
  - Immigrants and non-citizens
    - These people may have an ITIN, which is not the same as an SSN.

SSNs are required to perform electronic income checks. However, many of these people may not need to have an electronic income check performed for the following reasons:
  - Anyone under the age of 14 cannot legally make an income, and therefore do not need an income check run on them individually. These children should not be excluded from ex parte renewal if they do not have an SSN on file.
  - If the state is verifying income via categorical eligibility (SNAP, for example), they do not need to perform an additional income check

Despite these considerations, many state eligibility systems exclude **all** individuals without an SSN from being run through the full ex parte before eligibility logic. 

## What this looks like

The following failure reasons may be symptoms of SSN challenges:
  - "No SSN"
  - "Missing SSN"
  - "Cannot query income data sources"
  - "SSN required"
  - "SSN requested"

## Potential solutions

Citing CMS waivers or labor laws, reiterate that there are automatic eligibility pathways for members without SSNs. Work with the state to determine a set of people who can be passed to the ex parte process, despite having a missing SSN. Work with the vendor team to ensure a missing SSN _alone_ does not cause a person to be excluded from ex parte at _any_ stage of the process. 
