# Singularity

On occasion, the operating system and Rstudio installations that are available via [FASRC VDI Apps](https://docs.rc.fas.harvard.edu/kb/vdi-apps/) are not compatible with some R packages. A viable way to surmount package incompatibility issues is using docker containers. The [Rocker Project](https://rocker-project.org/images/) images run R and Rstudio containerized installations that come in various flavors. Three of the most popular rocker image builds are: `rocker/tidyverse`, `rocker/verse`, and `rocker/geospatial`. The official overview of these images is found [here](https://rocker-project.org/images/versioned/rstudio.html#overview). 

## Downloading a rocker/docker image with singularity

To work on a containerized Rstudio in FASSE, first identify the rocker distribution that best fits your needs. For the purpose of this tutorial, we will work with `rocker/geospatial:3.6.0`.

Once logged in to FASSE, create an `images` folder in your user directory and run

```
cd images
singularity pull docker://rocker/geospatial:3.6.0
```

Once the download has completed you should be able to see the file `geospatial_3.6.0.sif`.

## Running a rocker/docker image with singularity

Go to [FASRC VDI Apps](https://docs.rc.fas.harvard.edu/kb/vdi-apps/) and open a Remote Desktop session. Within the Remote Desktop, open a new terminal and inside the images folder run  

```
cd images
singularity shell geospatial_3.6.1.sif
```

Inside the running container, copy the following lines. You can chose the password of your preference.

```
export PASSWORD=geospatial
/usr/lib/rstudio-server/bin/rserver --auth-none=0 --auth-pam-helper-path=pam-helper
```

Open firefox (to do this you can open a new terminal tab and simpy run the command `firefox`) and position the browser in `localhost:8787`. An Rstudio homepage will require your username and password. Your username is your FASSE username and the password is `geospatial` (or the password that you established). Now you can start working in your dockerized Rstudio session!

When you have finished working, you can quit firefox. In the terminal that is running the container type `ctrl + d` to stop the running container.

## Installing new packages in the image/container

...
