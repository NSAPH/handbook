# Computing Spaces

NSAPH work happens in two main computing spaces. Choose the space you work in based on the data sensitivity and tooling you need.

## Choosing the right space

- ReD — regulated data that require higher security controls (Medicare, Medicaid, IRB-restricted or other sensitive health data).
- Cannon — general-purpose HPC for non-regulated data (environmental, geospatial, modeling, exploratory analysis).
- FASSE sync — legacy access for finishing work that still lives there; do not start new projects in this environment.

## ReD

- Purpose: secure environment for regulated health data with stricter access controls and auditing.
- Use ReD when working with Medicare, Medicaid, or any data covered by DUAs/IRB that contain PHI/PII.
- Account setup and workflows are in [ReD](red.md).
- Follow [project setup](project_setup.md) guidelines for consistent workspace structure
- GitHub access is not currently available; you must export your code upon project completion and upload to GitHub per NSAPH guidelines (see ReD documentation for export instructions).

## Cannon


- Purpose: general HPC cluster for data that do not require the regulated controls of ReD.
- Use Cannon for environmental and geospatial datasets, simulations, and analysis that exclude regulated health data.
- Cluster usage guidance and fairshare details are in [Cannon](cannon.md) and [Fairshare](fairshare.md).
- Git/GitHub are available; follow [project setup](project_setup.md) guidelines for consistent workspace structure.

## FASSE sync

- Legacy environment that mirrors work predating the move to ReD.
- Use only to finish projects that still reside there; new work should be on ReD (regulated data) or Cannon (non-regulated data).
- Access requires coordination with the [data team](team.md) 