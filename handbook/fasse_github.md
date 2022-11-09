# FASSE and GitHub Project Work

If you are working in a team on a project which uses GitHub, you might encounter some issues while using FASSE. If you and your teammates are both working from a folder in FASSE and connecting to GitHub through this folder, your work may suddenly start to disappear and be overwritten, even if you and your teammates are working on the project at different times. 

However, we do not have to stop using GitHub! To avoid this problem, you and your teammates can each make your own folder in FASSE in the /Lab/projects/ folder to work on the project. For example, you can have a folder named `johnsmith_health_pollution` and your teammate will have project folder `janesmith_health_pollution` (where health_polllution will be a descriptive title of the exposures and health outcomes). In each of these folders you can link to the project GitHub repository, where you will be able to push and pull without an issue, ideally to different feature branches (see guide to branches [here](https://nsaph.info/collaborative.html)). 

Since you will have multiple folders, it is especially important to remember to use symbolic links to your input data as these files can be very large. When you and your teammates have completed your work on the project, you can collapse back down to your `health_pollution` folder, which should reference the main branch from your GitHub repository.

### Summary

- Each teammate should have their own project folder in FASSE which is connected to one GitHub repository
- Use symbolic links to data sources
- It is a good idea to use different GitHub branches
- At the end of the project, collapse down to one folder in FASSE
