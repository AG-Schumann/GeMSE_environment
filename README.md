# GeMSE_environment

Docker software environment for GeMSE analysis and simulations.

Among other libraries and packages, it includes:
+ [miniconda](https://docs.conda.io/en/latest/miniconda.html)
+ [ROOT](https://root.cern/)
+ [BAT](https://bat.mpp.mpg.de/)
+ [Geant4](https://geant4.web.cern.ch/)


## Generate Docker container

There is an [automatic workflow](https://github.com/AG-Schumann/GeMSE_environment/tree/master/.github/workflows) in charge of building the container and uploading it to the [DockerHub](https://hub.docker.com/), after each commit to master branch.

If you want to build this container locally, [install Docker](https://docs.docker.com/engine/install/) and run

```
git clone https://github.com/AG-Schumann/GeMSE_environment.git
cd GeMSE_environment
docker build -t <CONTAINER_NAME> .
```

where `<CONTAINER_NAME>` can optionally be `<CONTAINER_NAME>:<TAG>` (otherwise a default tag is assigned that can afterwards be changed). 

## Convert container into a Singularity image

This works only for containers already uploaded in the [DockerHub](https://hub.docker.com/), for the moment under [Diego's profile](https://hub.docker.com/u/ramirezdiego).

[Install Singularity](https://sylabs.io/guides/3.3/user-guide/installation.html) and run

```
singularity build <SINGULARITY_IMAGE_NAME>.simg docker://<ORGANIZATION>/<CONTAINER_NAME>:<TAG>
```

To load this image, just execute:
```
singularity shell <SINGULARITY_IMAGE_NAME>.simg
```
and enjoy GeMSE analysis.
