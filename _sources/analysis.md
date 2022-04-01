# Git repository

[NSAPH Projects](https://github.com/NSAPH-Projects) GitHub organization is a shared account where all NSAPH members can collaborate across many projects at once. 

```{tip}
If you are not already a member of [NSAPH Projects](https://github.com/NSAPH-Projects), ask Amit or one of the admins to add you to the organization.
```

The goal is to keep all NSAPH analysis projects at [one location](https://github.com/NSAPH-Projects) to encourage internal review, collaboration and reuse. It would also facilitate future data and code curations, migrations, and cross-referencing material and documentation.

:::{admonition} New project 
:class: note 
If you are starting a new analysis project, create a repository under [NSAPH Projects](https://github.com/NSAPH-Projects) organization on GitHub. You can make contributions to the repository directly, or create a fork under own account.
:::

:::{admonition} Existing project 
:class: note 
If you already have a working git repository under own username, transfer its ownership to [NSAPH Projects](https://github.com/NSAPH-Projects). You can do that by clicking the following buttons at your repository page: "Settings" -> "Danger Zone" -> "Transfer ownership". Have a look at the [official GitHub guidelines](https://docs.github.com/en/repositories/creating-and-managing-repositories/transferring-a-repository).
:::

:::{admonition} Published project 
:class: note 
If you have a git repository of a completed project under own username that you reference in a publication, do not just transfer ownership to [NSAPH Projects](https://github.com/NSAPH-Projects). In this case, you should:

- Transfer ownership and create a **fork** of the repository under own username; or
- Ask a [NSAPH Projects](https://github.com/NSAPH-Projects) admin to fork your repository. Both repositories should be up-to-date.

This is important so that shared repository URLs are not broken. In this case, do not modify the repository name.
:::

(naming-convention)=
## Repository naming convention

Your repository name should be informative for the group members and outsiders. Consider the following format:

```
<EXPOSURE>-<OUTCOME>-<SUBPOPULATION>-<METHOD>
```

- Exposure examples: `pm-components`, `pm-no2`, `pm-no2-o3`, `heat-alert`
- Outcome examples: `cardiovascular`, `respiratory`, `adrd`
- Subpopulation examples: `medicare`, `race`, `ethnicity`
- Method: `reinforcement-learning`, `causalgps` 

For example: `heat_alert-mortality-reinforcement_learning` or shorter `heat_alert-mortality-rl`.

A repository name can have up to 100 characters.

```{tip}
In pratice you may have multiple exposures and outcomes. In that case, use your best jugement to name your repository based on the guidelines. Avoid information such as usernames and current date or year.
```

```{note}
To learn more about file naming conventions and why they are important, have a look at [the Harvard's research data management page](https://datamanagement.hms.harvard.edu/collect/file-naming-conventions).
```


## Repository structure

Consider organizing your repository as follows:

```
|-- README.md
|-- data/
|-- code/
|-- figures/
|-- reports/
|-- results/
|-- .gitignore
```
Have a look at the [NSAPH Project Template](https://github.com/NSAPH/project_template).

```{tip}
If you are using R software in your analysis, have a look at best practices and recommendations [here](https://swcarpentry.github.io/r-novice-inflammation/06-best-practices-R/) and [here](https://www.nature.com/articles/s41597-022-01143-6#Sec18).
```

## Special files

A `README.md` file is a standard documentation file where you should put information about the content of your repository. See more here: {ref}`readme-md`.

A `.gitignore` file tells Git which files to ignore when committing your project to the GitHub repository. It should be located in the root directory of your repo. Large data file and sensitive data should be ignored by Git.

```{warning}
Be careful not to push sensitive data on GitHub. Don't forget that Medicare/Medicaid data should not leave Harvard, but your analysis code should be versioned with Git. A `.gitignore` file helps with that.
```

Add path and/or file names of your data in the `.gitignore` file. For example, if your datasets sit in a `data` folder, add the following line:

```
data/
```

Alternatively, you can ignore all files of a certain format like `.csv`, `.nc` or `.rst`. Do that by adding `*.csv`, `*.nc` or `*.rst` as new lines in `.gitignore`. For example:
```
*.csv 
*.nc
*.rst
```

