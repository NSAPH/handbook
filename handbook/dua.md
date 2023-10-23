# Data Usage Policies

We would like to take this opportunity to make sure that all FASSE users have read the following
usage policy and agree to it. Please take a few minutes to read the information below.

## Data Access

**1. FASSE accounts are individual accounts that are not sharable.**

*You are not allowed to share your account password with anyone. Allowing other individuals to log into your account or use your account is a violation of our DUA and will result in immediate termination of your account.*

**2. Our DUA and IRB approvals are project specific.**

*Before starting a new project with any health data, you must check in with our team to ensure that this is an approved project. Please do so by submitting a project initiation form. Even if the data already exists and you already have access to it please submit a new request for every new project. Failure to do so will result in immediate termination of your account.*

**3. CMS health data cannot be accessed outside the United States.**

*If you are traveling internationally, please plan for a pause in your work. For more information click [*here*](https://resdac.org/articles/cms-non-us-based-researcher-policy).*

**4. IRB coverage & data security trainings are required.**

*Everyone with data access need to be on IRB and have completed all the data security trainings required.*

## Data Sharing

**1. Health data CANNOT be moved from the FASSE.**

*Per the DUA and IRB, data has to be on the FASSE level 3 data cluster ONLY and cannot be 
downloaded from the level 3 FASSE. Datasets CANNOT be downloaded or moved from FASSE even if they do not have identifying information. Violations come with serious consequences that jeopardize everyone's work. We are very much encouraging sharing reproducible code on GitHub, but please use 
it only for CODE and publicly available data. We suggest adding a `.gitignore` file to your 
repository and using it to prevent unintentional upload of data files. We also suggest using 
the `git status` command before committing to confirm what you are committing.*

**2. CMS Cell size suppression Policy is enforced by the DUA.**

*As outlined for researchers in the data use agreement (DUA), the CMS cell size suppression policy sets minimum thresholds for the display of CMS data. The policy stipulates that no cell (e.g. admissions, discharges, patients, services, etc.) containing a value of 1 to 10 can be reported directly. A value of zero does not violate the minimum cell size policy. In addition, no cell can be reported that allows a value of 1 to 10 to be derived from other reported cells or information. For more information, click [*here*](https://resdac.org/articles/cms-cell-size-suppression-policy).*

## Data Use

**1. Compute resources are limited.**

*Inefficient use of compute resources by a single user can prevent the entire team from getting work done. Users should develop and benchmark their models using the Rstudio profiler on small subsets of their data prior to grabbing large chunks of memory. We monitor compute usage, and users using the cluster inefficiently may have their jobs cancelled.*

**2. Set up GitHub under [NSAPH-Projects](https://github.com/orgs/NSAPH-Projects) and link it to FASSE project space.**

*For more details, please see instructions [here](https://nsaph.github.io/handbook/fasse.html#step-4-create-a-git-repository-on-github).*

**3. Work under the project space, and not in your home folder.**

*Instructions on how to create a project folder and a GitHub repository can be found [*here*](https://nsaph.github.io/handbook/fasse.html#step-3-project-workspace).*

**4. Use a Symbolic link to read in data from your project folder.**

*In order to use any of the analytic datasets available under the dominici_nsaph FASSE group, please make sure to use a symbolic link to read in data from your project folder located under `/n/dominici_nsaph_l3/Lab/projects`. **Please do not copy the data**; we have limited storage capacity and cannot have multiple copies of the data. For more information on this step, click [here](https://nsaph.github.io/handbook/fasse.html#step-5-analytic-data).*

**Useful links on data privacy **
- "Why Anonymous Data Sometimes Isn't" 
SCHNEIER, B. (2007), "Why Anonymous Data Sometimes Isn't", WIRED, [https://www.wired.com/2007/12/why-anonymous-data-sometimes-isnt/](https://www.wired.com/2007/12/why-anonymous-data-sometimes-isnt/) 
- "Harvard Professor Re-Identifies Anonymous Volunteers In DNA Study"
Adam Tanner (2013), Harvard Professor Re-Identifies Anonymous Volunteers In DNA Study, FORBES, [https://www.forbes.com/sites/adamtanner/2013/04/25/harvard-professor-re-identifies-anonymous-volunteers-in-dna-study/?sh=7964abc92c9b] (https://www.forbes.com/sites/adamtanner/2013/04/25/harvard-professor-re-identifies-anonymous-volunteers-in-dna-study/?sh=7964abc92c9b)
