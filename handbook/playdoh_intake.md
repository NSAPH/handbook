# Play-Doh Data Intake Form

The `data/play-doh/` folder in the ReD lab share is an unstructured data repository housing datasets that do not conform to the [LEGO](lego_data_model.md) standards, including raw and other data contributions. This page describes the requirements for Play-Doh datasets and the process for importing data into ReD using the [data intake form](https://docs.google.com/forms/d/e/1FAIpQLSdnxBGA71_w7nGiKg0L81GQMkXlI0CN4ogRkp3cBV2VQPgt_A/viewform?usp=header). For general information about working in ReD, see [Working on RED](red.md).

## Play-Doh Requirements

Datasets imported through the Play-Doh process must meet the following requirements:
- Must be registered in the [Play-Doh catalog](https://docs.google.com/spreadsheets/d/1wWP48xTTigh7xwGSEsQax68cpaqoxmfqNX4QK838nYM/edit?usp=sharing), a spreadsheet that lists all Play-Doh datasets and includes basic information such as the dataset name and link to the Dataverse page.
- Whenever possible, the datasets should be catalogued in [Harvard Dataverse](https://dataverse.harvard.edu) and belong to the [NSAPH collection](https://dataverse.harvard.edu/dataverse/nsaph) or [CAFE collection](https://dataverse.harvard.edu/dataverse/cafe).
- The metadata must be [CAFE compliant](https://climate-cafe.github.io/intro.html), meaning that the metadata must follow the CAFE standards and include the required fields.

## Decision Tree

Use the decision tree below to determine whether you need to create a Dataverse entry, whether your catalog entry will include a DOI, and where your data will be stored on ReD.

```{figure} imgs/playdoh_decision_tree.png
---
align: center
---
Play-Doh data intake decision tree
```

### Unrestricted data

If you did **not** get access to the data through a user agreement and it is not restricted to your use only:

| Situation | What to do | Storage location | Visibility to NSAPH members |
|---|---|---|---|
| Data is already in a public repository (Dataverse, Zenodo, etc.) | Fill out the intake form with the required metadata, including the DOI. If the dataset is not in CAFE, the data team will arrange for it to be harvested into the CAFE collection. | `data/play-doh/` | Catalog entry and data available |
| You are the author, or are in close contact with the author(s), and the dataset is ready for publication | Create an entry in the [CAFE collection](https://dataverse.harvard.edu/dataverse/cafe) in Harvard Dataverse, then fill out the intake form with the required metadata, including the DOI. | `data/play-doh/` | Catalog entry and data available |
| You are the author, or are in close contact with the author(s), and the dataset is **not** ready for publication | Fill out the intake form with the required metadata (no DOI). | `data/play-doh/` | Catalog entry and data available |
| You are not in close contact with the author(s), but have sufficient information to create a Harvard Dataverse entry | Create an entry in the [CAFE collection](https://dataverse.harvard.edu/dataverse/cafe) in Harvard Dataverse, then fill out the intake form with the required metadata, including the DOI. | `data/play-doh/` | Catalog entry and data available |
| You are not in close contact with the author(s) and do **not** have sufficient information to create a Harvard Dataverse entry | Fill out the intake form with the required metadata (no DOI). | `data/play-doh/` | Catalog entry and data available |

### Restricted data

If you got access to the data through a user agreement or it is restricted to your use only, you must ask a member of the data team for permission to import restricted data **before moving forward**. Reach out to a member of the [data team](team.md) via Basecamp to request permission. Once permission is granted:

| Situation | What to do | Storage location | Visibility to NSAPH members |
|---|---|---|---|
| Data is shareable with other people in the cluster with your/your PI's permission | Fill out the intake form with the required metadata (no DOI). Update the permissions of your project directory. | Your project directory | Catalog entry available, without the location of the files |
| Data is **not** shareable with other people in the cluster | Fill out the intake form with the required metadata (no DOI). Update the permissions of your project directory. | Your project directory | Catalog entry hidden from other NSAPH members |

## Data Import

Data can be imported into ReD if it is documented with appropriate metadata and shared (with appropriate exceptions) with the rest of the NSAPH research community. This ensures the security of the ReD environment and supports the NSAPH community's goal of promoting [FAIR guidelines](https://www.go-fair.org/fair-principles/) for data use in research.

**Step 1** Follow the [decision tree](#decision-tree) above to determine which case applies to your dataset. If your data is restricted, do not continue until a member of the data team has granted permission to import it.

**Step 2** If the decision tree indicates that you should create a [Harvard Dataverse](https://dataverse.harvard.edu) entry, create it under the [CAFE collection](https://dataverse.harvard.edu/dataverse/cafe) following the [CAFE data management guidelines](https://climate-cafe.github.io/intro.html). If your dataset is already under another collection, please let the data team know so the dataset is linked into the CAFE collection.

**Step 3** Using Globus, create a subfolder named with your username (for example, `jharvard`) within the `/import/` directory and transfer the data that needs to be imported into this folder. See the Globus user guide at ReD Sharepoint site > Documents > ReD-File Transfers with Globus.

NOTE: If you are using Globus for the first time, please notify either [Shreya Nalluri](mailto:snalluri@hsph.harvard.edu) and/or [Mahima Kaur](mailto:mahimakaur@hsph.harvard.edu) with your Globus ID so you can be added to the NSAPH collection.

**Step 4** Once the data transfer is complete, fill and submit the [data intake form](https://docs.google.com/forms/d/e/1FAIpQLSdnxBGA71_w7nGiKg0L81GQMkXlI0CN4ogRkp3cBV2VQPgt_A/viewform?usp=header) with the required metadata (including the DOI, if applicable) so the data team can proceed with the importation process.

>**What Happens After Submission?**
>The data team will:
>* Review the Dataverse entry (if applicable) and associated metadata, and confirm that the dataset meets applicable data standards and Play-Doh requirements.
>* Move the data to its final location on ReD: the `data/play-doh/` directory, or your project directory for restricted data.
>* Add the dataset to the [Play-Doh catalog](https://docs.google.com/spreadsheets/d/1wWP48xTTigh7xwGSEsQax68cpaqoxmfqNX4QK838nYM/edit?usp=sharing) with the appropriate visibility and update the data location in the intake form accordingly.

NOTE: To import new CMS data from physical media, please connect with SPH IT [Matt Ronn](mailto:mronn@sdac.harvard.edu) and [Brian Pedrant](mailto:bpedrant@hsph.harvard.edu). They will maintain the physical asset inventory and upload the data through a secure workstation via Globus to ReD Environment.
