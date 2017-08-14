# Docker Debian 7 image for Ansible role testing through Molecule

[![Build Status](https://travis-ci.org/mplachter/docker-debian7-molecule.svg?branch=master)](https://travis-ci.org/mplachter/docker-debian7-molecule) [![Docker Automated build](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/mplachter/docker-debian7-molecule/)

Debian 8 Docker image for Ansible role testing on Molecule.

## How to Build

Docker Hub builds this image from a webhook posted by travis-ci, any time a commit is made or merged to the `master` branch. The following steps let you build the image on your own locally.

1. [Install Docker](https://docs.docker.com/engine/installation/).
1. `cd` into this directory.
1. Run `docker build -t debian7-molecule .`

## How to Use

This image was created to use for Molecule testing.

1. [Install molecule](https://molecule.readthedocs.io/en/latest/usage.html#quick-start).
1. Add the image to your molecule.yml

    ```
    dependency:
        name: galaxy
    driver:
        name: docker
    docker:
    containers:
      - name: docker-molecule-example
        hostname: docker-molecule-example
        image: mplachter/docker-debian7-molecule
        image_version: latest
    ```

## Author

Matt Plachter