# GeMSE_environment

Docker software environment for GeMSE analysis and simulations.

## Generate Docker container

[Install Docker](https://docs.docker.com/engine/install/) and run

```
git clone https://github.com/AG-Schumann/GeMSE_environment.git
cd GeMSE_environment
docker build -t <CONTAINER_NAME>:<TAG>
```

## Convert container into a Singularity image

[Install Singularity](https://sylabs.io/guides/3.3/user-guide/installation.html) and run

```
singularity build <SINGULARITY_IMAGE_NAME>:<TAG> docker://<ORGANIZATION>/<CONTAINER_NAME>:<TAG>
```

if your container is uploaded to the [DockerHub](https://hub.docker.com/); or, if working locally, run


```
singularity build <SINGULARITY_IMAGE_NAME>:<TAG> <CONTAINER_NAME>:<TAG>
```
