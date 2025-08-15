# Working on RED

The [Regulated Data (ReD) Environment](https://rc.harvard.edu/services/regulated-data-services-user-guide/) is a secure environment for managing and analyzing sensitive data.

## Access and Logging In
Access to the ReD environment is restricted and requires approval. To request a ReD account and log into ReD please follow the instructions in the [ReD](https://rc.harvard.edu/services/regulated-data-services-user-guide/) site.

## Home Directory vs Lab Share
Your initial working directory upon login is your home directory (aka homedir). The lab share is a shared space accessible to all members of your lab or group. The home directory is used for personal configurations (e.g. .bashrc files), while the lab share is used for all research and analysis data and code.

> **Good practices:**
> * Your homedir has good performance only for simple tasks. Computation in homedir results in poor performance for all users. Only store configuration files in your home directory.
>* Research projects typically require intensive or large numbers of jobs and should NOT be sitting in home directories. **Only use our lab share for data and code**.

## Lab Share and Permissions
The specific location of our lab share remains confidential to protect sensitive data. For the purpose of this guide, we will refer to the lab share location in ReD as `lab_share/`.

There are two permission groups in the lab share: 
* `urc-nsaph-lab` all members of NSAPH belong to this group and have read/write access to the lab share.
* `urc-nsaph-lab-data` only members of the NSAPH data team belong to this group. The data team has special permissions to manage data files and directories within the lab share.

The folder structure in the lab share is designed to facilitate collaboration and organization. The main folders in the lab share are as follows:

```
/.../
├── lab_share/
│   ├── data/
│   │   ├── lego/
│   │   └── play-doh/
│   ├── data_management/
│   └── research_projects/
```

### Folder Structure
* **research_projects/**: directory containing individual research projects, all members in the `urc-nsaph-lab` group have access.
* **data/**: accessible to members of the `urc-nsaph-lab` for data storage and sharing.
* **data_management/**: accessible only to members of the `urc-nsaph-lab-data` group.

### Research Projects
The `research_projects/` folder is used to store individual research projects. Each project should have its own folder. 
* Follow the naming convention described in Step 4 of the [Working in FASSE](fasse.md) section of the handbook.
* After creating your project folder change permissions by doing `chmod -R 770 /path/to/folder/`
* If you need to import code for your project, look at the [Code Imports on ReD](#code-imports-on-red) section below.

### LEGO and Play-Doh 
Both the `lego/` and `play-doh/` folders are used to store data, but they have different requirements and cataloging mechanisms. If you want to import data into ReD, please follow the steps outlined in the [Data Imports on ReD](#data-imports-on-red) section below.

* **data/lego/**: a structured data warehouse housing standardized, modular, and vetted datasets following the [LEGO data model](lego_data_model.md). As a requirement, the datasets in this folder must be LEGO compatible, that is:
    - The datasets must conform to the LEGO schema and data model standards
    - Must be registered in the [LEGO catalog](https://lego-catalog.netlify.app/)
    - Must be fully reproducible, meaning that the data versions can be regenerated from the source data and scripts
* **data/play-doh/**: an unstructured data repository housing datasets that do not conform to the LEGO standards, including raw and other data contributions. The datasets in this folder must be catalogued in [Harvard Dataverse](https://dataverse.harvard.edu) and meet the following requirements:
    - The datasets must belong to the [NSAPH collection](https://dataverse.harvard.edu/dataverse/nsaph) or [CAFE collection](https://dataverse.harvard.edu/dataverse/cafe) in Dataverse.
    - The metadata must be [CAFE compliant](https://climate-cafe.github.io/intro.html), meaning that the metadata must follow the CAFE standards and include the required fields.
    - Must be registered in the [Play-Doh catalog](https://docs.google.com/spreadsheets/d/1wWP48xTTigh7xwGSEsQax68cpaqoxmfqNX4QK838nYM/edit?usp=sharing), a spreadsheet that lists all datasets in the `play-doh/` folder and includes basic information such as the dataset name and link to the Dataverse page.

## Data Imports on ReD

Additional data can only be imported into ReD if it is documented with appropriate metadata and shared (with appropriate exceptions) with the rest of the NSAPH research community. This ensures the security of the ReD environment and supports the NSAPH community's goal of promoting [FAIR guidelines](https://www.go-fair.org/fair-principles/) for data use in research. The metadata for all data imports will be pulled from the [Harvard Dataverse](https://dataverse.harvard.edu). If your dataset is not fully sharable at this time, you can create a metadata-only entry as described below.

**Step 1** Decide which option applies best to your case:
* **Fully sharable** you are ready to share your dataset with the public, including data files and metadata.
* **Metadata only** there are two instances when this applies:
    - **Draft publication** your data files are not ready for publication
    - **Restricted data** your data files cannot be shared because of sensitive or restricted content

**Step 2** Create your [Harvard Dataverse](https://dataverse.harvard.edu) entry. Regardless of whether your dataset is fully shareable or metadata only, you will need to create a Dataverse entry for your dataset in order to be imported into ReD.
  - Preferably, create your dataset under the [NSAPH Dataverse collection](https://dataverse.harvard.edu/dataverse/nsaph) following the [CAFE data management guidelines](https://climate-cafe.github.io/intro.html). 
  - If your dataset is under another collection, please let the data team know so the dataset is linked into the [CAFE collection](https://dataverse.harvard.edu/dataverse/cafe).

**Step 3** Fill and submit the [data intake form](https://docs.google.com/forms/d/e/1FAIpQLSdnxBGA71_w7nGiKg0L81GQMkXlI0CN4ogRkp3cBV2VQPgt_A/viewform?usp=header) so the data team can proceed with the importation process.

>**What Happens After Submission?** The data team will:
>* Review the Dataverse entry and metadata.
>* Check that the dataset meets the folder-specific requirements (e.g., LEGO schema, Play-Doh catalog entry).
>* Copy/import data into the appropriate lab_share location.
>* Update catalogs or tracking systems.

## Code Imports on ReD
