# qbgbaAnalysis <img src='images/logo.png' align="right" height="139" />

This repo contains the (small) dockerfile that builds the docker container for analyzing some data from the German "Qualitaetsberichte der Kranken-haeuser" obtained from the "Gemeinsamer Bundesausschuss" (GBA).

## Standing on the shoulder of giants

The infrastructure part of this project would have been a lot harder if not for the great work of the rocker project which delivers up-to-date R docker container for many purposes and the corresponding building blocks to get something that just works. See here for the [Rocker Project](https://www.rocker-project.org/) and have a look at specific R-based containers [here](https://github.com/rocker-org/rocker-versioned2), If you want to inform yourself about the great possibility to enhance a specific container with other components like shiny easily [here](https://github.com/rocker-org/rocker-versioned2#modifying-and-extending-images-in-the-new-architecture).

## Installation

To display the Klinik-DB-based interactive analyses, you need to get the respective docker container (either using [Docker](https://www.docker.com/) or [Podman](https://podman.io/)). Therefore, you have two possibilities: 

1. Clone this repo and build the container for yourself:

```
git clone https://gitlab.com/klinik-db/qbgbaAnalysis.git
cd qbgbaAnalysis
docker build --tag klinikdb/qbgbaapp -f dockerfile
docker run -it --rm --name qbgbaAnalysis -p 8787:8787 -p 8080:80 klinikdb/qbgbaapp

```
and then go to http://localhost:8080

Or, you can pull a prebuild container from our gitlab-based container registry:

```
docker pull registry.gitlab.com/klinik-db/qbgbaanalysis
docker run -it --rm qbgbaanalysis
```

Good luck!

## Funding

Sponsored through the Prototype Fund by the German Federal Ministry of Education and Research from March 2021 to August 2021. 

<a href='https://klinik-db.de'><img src='man/figures/BMBF_eng.png' align="left" height="139" /></a>
