# Git repository

If you are starting a new analysis project, create a repository under [NSAPH Projects](https://github.com/NSAPH-Projects) organization on GitHub. Keeping all NSAPH analysis projects at [one location](https://github.com/NSAPH-Projects) is preferable for internal review, collaboration and reuse, but also for future data and code curation, and cross-referencing internal material and documentation.

If you already have a working git repository under own username, transfer its ownership to [NSAPH Projects](https://github.com/NSAPH-Projects). You can do that by clicking the following buttons at your repository page: "Settings" -> "Danger Zone" -> "Transfer ownership". Have a look at the [official GitHub guidelines](https://docs.github.com/en/repositories/creating-and-managing-repositories/transferring-a-repository).

```{note}
If you have a git repository of a completed project under own username that you reference in a publication, do not just transfer ownership to [NSAPH Projects](https://github.com/NSAPH-Projects). In this case, you should:

- Transfer ownership and create a **fork** of the repository under own username; or
- Ask a [NSAPH Projects](https://github.com/NSAPH-Projects) admin to fork your repository. Both repositories should be in sync and up-to-date.

This is important so that shared repository URLs are not broken. In this case, do not modify the repository name.
```

## Naming

Your repository name should have the following format:

```
exposure-outcome-method
```

For example: `heat_alert-mortality-reinforcement_learning` or shorter `heat_alert-mortality-rl`.

A repository name can have up to 100 characters.

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

## Special files

A `README.md` file is a standard documentation file where you should put information about the content of your repository.

A `.gitignore` file tells Git which files to ignore when committing your project to the GitHub repository. It should be located in the root directory of your repo. 

````{warning}
Be careful not to push sensitive data on GitHub. Don't forget that Medicare/Medicaid data should not leave RCE, but your analysis code should be versioned with Git.

Add path and/or file names of your data in the `.gitignore` file. For example, if your datasets sit in a `data` folder, add the following line:

```
data/
```

Alternatively, you can ignore all files of a certain format like CSV, NC or RST. Do that by adding `*.csv`, `*.nc` or `*.rst` as new lines in `.gitignore`.
````

