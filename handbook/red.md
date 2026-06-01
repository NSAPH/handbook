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
* Follow the naming convention described in Step 1 of the [Project Setup](project_setup.md) section of the handbook.
* After creating your project folder change permissions by doing `chmod -R 770 /path/to/folder/`

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

## Data Import

Data can be imported into ReD if it is documented with appropriate metadata and shared (with appropriate exceptions) with the rest of the NSAPH research community. This ensures the security of the ReD environment and supports the NSAPH community's goal of promoting [FAIR guidelines](https://www.go-fair.org/fair-principles/) for data use in research. The metadata for all data imports will be pulled from the [Harvard Dataverse](https://dataverse.harvard.edu). If your dataset is not fully sharable at this time, you can create a metadata-only entry as described below.

**Step 1** Decide which option applies best to your case:
* **Fully sharable** you are ready to share your dataset with the public, including data files and metadata.
* **Metadata only** there are two instances when this applies:
    - **Draft publication** your data files are not ready for publication
    - **Restricted data** your data files cannot be shared because of sensitive or restricted content

**Step 2** Create your [Harvard Dataverse](https://dataverse.harvard.edu) entry. Regardless of whether your dataset is fully shareable or metadata only, you will need to create a Dataverse entry for your dataset in order to be imported into ReD.
  - Preferably, create your dataset under the [NSAPH Dataverse collection](https://dataverse.harvard.edu/dataverse/nsaph) following the [CAFE data management guidelines](https://climate-cafe.github.io/intro.html). 
  - If your dataset is under another collection, please let the data team know so the dataset is linked into the [CAFE collection](https://dataverse.harvard.edu/dataverse/cafe).

**Step 3** Using Globus, create a subfolder named with your username (for example, `jharvard`) within the `/import/` directory and transfer the data that needs to be imported into this folder. See the Importing Data using Globus guide at ReD Sharepoint site > Documents > ReD-File Transfers with Globus.
Note : If you are using Globus for the first time, please notify either [Shreya Nalluri](mailto:snalluri@hsph.harvard.edu) and/or [Mahima Kaur](mailto:mahimakaur@hsph.harvard.edu) with your Globus ID so you can be added to the NSAPH collection.

Once the data transfer is complete, fill and submit the [data intake form](https://docs.google.com/forms/d/e/1FAIpQLSdnxBGA71_w7nGiKg0L81GQMkXlI0CN4ogRkp3cBV2VQPgt_A/viewform?usp=header) so the data team can proceed with the importation process.

>**What Happens After Submission?**
The data team will :
>*  Review the Dataverse entry and associated metadata, confirm that the dataset meets applicable data standards and folder-specific requirements (such as LEGO or Play-Doh).
>* Move the data to its final location on ReD. If the data cannot be shared with other lab members due to access, licensing, or sensitivity constraints, it may instead be placed in a user-specific location on ReD.
>* Update the data location in the intake form accordingly.

NOTE: To import new CMS data from physical media, please connect with SPH IT [Matt Ronn](mailto:mronn@sdac.harvard.edu) and [Brian Pedrant](bpedrant@hsph.harvard.edu). They will maintain the physical asset inventory and upload the data through a secure workstation via Globus to ReD Environment.

## Code Import

Code imports ensure the code brought into the regulated environment is traceable and reviewed

Code includes any of the following entering the environment:
- Source code (scripts, notebooks, pipelines)
- Configuration files (YAML/JSON/INI)
- Dependency files (requirements.txt, environment.yml)

### Required Rules

- No PHI/PII/sensitive identifiers may be included in code, comments, example files, or logs.
- Do not include IP addresses, ARNs, or full system paths.
- Do not include SSH keys, PGP keys, secrets, tokens, or any hashes or keys that could be considered personal or sensitive.
- Do not import executables or binaries.

**Step 1** Upload code to GitHub.
- Create a GitHub repository under the [NSAPH organization](https://github.com/NSAPH-Projects).
- Ensure the code is committed and pushed.
- Include a `README.md` with purpose, usage, and required inputs/outputs.

**Step 2** Download a ZIP of your repository.
- Note the most recent commit hash; you will need it for the filename.
- Download a ZIP of the repository.
- Name the file in a consistent, traceable format, such as `heat_alert-mortality-rl_a1b2c3d.zip`.
- Confirm the ZIP contains only what you intend to import (no data, secrets, or binaries).

**Step 3** Stage your transfer folder locally.

Name your local folder with your username.

For example:

```bash
mkdir jharvard
cp heat_alert-mortality-rl_a1b2c3d.zip jharvard/
```

**Step 4** Transfer your local folder via Globus.

In Globus, navigate to the `/import/` directory and use the Upload button to transfer your local folder.
- Reference: ReD Sharepoint site > Documents > ReD-File Transfers with Globus

**What happens after transfer?**

The import process is automatic; no ticket submission is needed. A malware scan and security compliance check will run once your files arrive. A member of the NSAPH data team will move the code to your preferred project location.


## Data/Code Exports on ReD

Exports from ReD require review before files can leave the regulated environment. This applies to code, figures, tables, manuscripts, notes, and other analysis outputs. Raw data, data extracts, individual-level data, PII, and PHI should not be exported.

GitHub is not currently configured to work with ReD, so you cannot push or pull directly between ReD and GitHub. When code needs to leave ReD, export it through the process below and upload it to GitHub after approval.

Please allow up to 5 working days for review, depending on the number and size of the files.

**Before submitting an export request:**
* Export only the files needed outside ReD.
* Prefer plots, figures, tables, code, manuscripts, notes, or other small analysis outputs.
* For code exports, remove sensitive paths, credentials, tokens, keys, and any values copied from restricted data.
* Do not include generated data, temporary files, logs, or cache files in code export folders.
* Make sure tables follow CMS cell suppression rules: all cell sizes must be 10 or greater, including weighted, unweighted, zero-count, and missing-data cells.
* Make sure maps or visualizations do not reveal exact respondent locations.
* Include a brief `README` describing the exported contents.
* Confirm that file permissions allow the Data Manager and ReD team to inspect the files.

**Step 1** Create a folder in `lab_share/export/` using your username, date, and approximate request time.

For example:

```bash
mkdir lab_share/export/jharvard_260416_1443
```
**Step 2** Create a `README.md` in your export folder containing:

For data exports:
- General description of export contents
- Dataset name
- Sample size
- Table-cell description
- Data dictionary

For code exports:
- General description of export contents
- Attestation that you have checked that no paths, data, or identifiers are exposed in the code you are exporting

**Step 3** Copy only the files you want reviewed into that folder.

For example:

```bash
cp figure1.png lab_share/export/jharvard_260416_1443/
```

**Step 4** Email [Emre Kaskin](mailto:emre_keskin@harvard.edu) and cc [Bob Freeman](mailto:robert_freeman@harvard.edu) to request review. Include:
* Subject line, such as `Export Request: NSAPH Lab, Standard`
* PI name
* Data Manager name: Emre Kaskin & Bob Freeman
* DUA, IRB, or project title
* Deadline, if applicable
* Name and relative path of the export folder
* A brief description of the files being exported

**Step 5** Wait for approval. One of the Data Managers will review the files and reply with an explicit approval stating that the files do not contain sensitive, regulated, or identifying information and comply with applicable DUA sanitization or de-identification requirements.

**Step 6** Forward the approved email thread to [regulated_data_environment@harvard.edu](mailto:regulated_data_environment@harvard.edu), cc'ing [Emre Kaskin](mailto:emre_keskin@harvard.edu) and [Bob Freeman](mailto:robert_freeman@harvard.edu).

After submitting the request, you will receive an automated ServiceNow ticket. Avoid replying separately to the ticket unless the ReD team asks for more information, since extra replies may create duplicate tickets.

**Step 7** Wait for the ReD team to review and scan the files. If approved, the ReD team will move the files to the Globus export folder and respond through the ticket with next steps.

**Step 8** Download the approved files from Globus. See the Importing Data using Globus guide at ReD Sharepoint site > Documents > ReD-File Transfers with Globus

**Step 9** After download, delete the export copies from both the ReD export folder and the Globus export folder.

If the ReD team identifies a problem with the export contents, revise the files and continue communicating through the same ServiceNow ticket.
