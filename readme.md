# Laravel CircleCI 2.0 Docker Image
[![CircleCI](https://circleci.com/gh/ericdowell/laravel-circleci.svg?style=svg)](https://circleci.com/gh/ericdowell/laravel-circleci)
[![Docker Pulls](https://img.shields.io/docker/pulls/ericdowell/laravel-circleci.svg?style=flat-square)](https://hub.docker.com/r/ericdowell/laravel-circleci/)


Docker container for running tests/build in CircleCI 2.0, 
meant for the PHP Framework [Laravel](https://laravel.com/).

This repo builds off of the `circleci/php:7.3-fpm-buster-node-browsers-legacy` image.

This is built nightly and pushed to the `latest` tag.

## Permissions Issue
Currently there's a permission issue that has to be resolved,
to fix the issue in your laravel build add this step to your `.circleci/config.yml` file:

```yml
version: 2
jobs:
  build:
    docker:
      - image: ericdowell/laravel-circleci:latest
    steps:

      - run:
          name: Fix app folder permissions
          command: sudo chmod -R 0777 storage/ && sudo chmod -R 0775 bootstrap/cache/ && sudo chmod 0775 public/robots.txt
```

## Build Locally
Run: `docker build -t ericdowell/laravel-circleci .`
