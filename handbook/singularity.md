# Singularity

On occasion, the operating system and Rstudio installations that are available via [FASRC VDI Apps](https://docs.rc.fas.harvard.edu/kb/vdi-apps/) are not compatible with some R packages. 

A viable way to surmount package incompatibility issues is using docker containers. The [Rocker Project](https://rocker-project.org/images/) images run R and Rstudio containerized installations that come in various flavors. Three of the most popular rocker image builds are: `rocker/tidyverse`, `rocker/verse`, and `rocker/geospatial`. The official overview of these images is found [here](https://rocker-project.org/images/versioned/rstudio.html#overview). 

Docker is usually not available on HPC clusters, Singularity is a secure HPC alternative to Docker.

## Downloading a rocker/docker image with singularity

To work on a containerized Rstudio in FASSE, first identify the rocker distribution that best fits your needs. For the purpose of this tutorial, we will work with `rocker/geospatial:3.6.3`.

Once logged in to FASSE, create an `images` folder in your user directory and run

```
cd images
singularity pull docker://rocker/geospatial:3.6.3
```

Once the download has completed you should be able to see the file `geospatial_3.6.0.sif`.

## Running a rocker/docker image with singularity

Go to [FASRC VDI Apps](https://docs.rc.fas.harvard.edu/kb/vdi-apps/) and open a Remote Desktop session. Within the Remote Desktop, open a new terminal and inside the images folder run  

```
singularity shell images/geospatial_3.6.3.sif
```

Inside the running container the location of the rserver in the container is `/usr/lib/rstudio-server/bin/rserver`. To run it simply write 

```
rserver
```

Open firefox (to do this you can open a new terminal tab and run the command `firefox`) and position the browser in `localhost:8787`. Now you can start working in your dockerized Rstudio session!

### Options

Some useful options include `RSTUDIO_SESSION_TIMEOUT='0'`, `--bind <directory>`, and `--no-mount <directory>`. 

* `singularity shell apps/geospatial_3.6.3.sif RSTUDIO_SESSION_TIMEOUT='0'` will avoid Rstudio from timing out.
* `singularity shell --bind <directory> apps/geospatial_3.6.3.sif` is useful when directories inside the container are not mapped to the host system. 
* `singularity shell --no-mount <directory> apps/geospatial_3.6.3.sif` will overide the mounting of a specific directory.

### Quit and exit

When you have finished working, quit the R session and quit firefox. T do this, in the terminal that is running the container type `ctrl + c` which will stop the rserver and `ctrl + d` which will stop the running container.

To list and clean the cached information of your containers, use

```
singularity cache list
singularity cache clean
```

## Installing additional R packages

`rocker` images are meant to have the minimal amount of pre-installed packages. As such, users can add the packages (R or system/linux) that are specific for a project. While it may be practical to install packages in a running container, creating an image that is specific for your project is ideal for reproducibility purposes. How to-do's are provided next.

* To **install packages in a running rocker container** follow the instructions provided by FASRC. Found [here](https://docs.rc.fas.harvard.edu/kb/r-packages-with-singularity/).

* To **create a project specific image for reproducibility purposes** work locally in your machine. First, install docker and decide a name for your image, for the purpose of the example we use `core_geospatial`. Make a folder with the same name of the image and inside the folder create a file named `dockerfile`. The content of the dockerfile will be similar to 
```
FROM rocker/geospatial:3.6.3

RUN install2.r --error \
    tictoc \
    fst
```

Which is found [here](https://github.com/audiracmichelle/images/tree/main/core_geospatial). Instead of `tictoc` and `fst`, sustitute with the packages that you used in your project. 

Build the image with

```
cd core_geospatial
docker build -t . core_geospatial
```

Create a docker account and push into dockerhub following instructions [here](https://docs.docker.com/docker-hub/repos/#pushing-a-docker-container-image-to-docker-hub).

You can then pull the image you created into FASSE with `singularity pull` as explained at the beginning of the **Singularity** section.
