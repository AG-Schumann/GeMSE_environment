# GeMSE_environment

Docker software environment for GeMSE analysis and simulations.

Among other libraries and packages, it includes:
+ [miniconda](https://docs.conda.io/en/latest/miniconda.html)
+ [ROOT](https://root.cern/)
+ [BAT](https://bat.mpp.mpg.de/)
+ [Geant4](https://geant4.web.cern.ch/)


## Generate Docker container

There is an [automatic workflow](https://github.com/AG-Schumann/GeMSE_environment/tree/master/.github/workflows) in charge of building the singularity container and uploading it to the [DockerHub](https://hub.docker.com/), after each commit to master branch.

If you want to build this container locally, [install Docker](https://docs.docker.com/engine/install/) and run

```
git clone https://github.com/AG-Schumann/GeMSE_environment.git
cd GeMSE_environment
docker build -t <CONTAINER_NAME>:<TAG>
```

## Convert container into a Singularity image

This works only for containers already uploaded in the [DockerHub](https://hub.docker.com/).

[Install Singularity](https://sylabs.io/guides/3.3/user-guide/installation.html) and run

```
singularity build <SINGULARITY_IMAGE_NAME>:<TAG>.simg docker://<ORGANIZATION>/<CONTAINER_NAME>:<TAG>
```

