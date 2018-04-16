# Laravel CircleCI 2.0 Docker Image
Docker container for running tests/build in CircleCI 2.0, 
meant for the PHP Framework [Laravel](https://laravel.com/).

This repo builds off of the `circleci/php:7.2-fpm-stretch-node-browsers` image.

This is built nightly and pushed to the `latest` tag.

## Permissions Issue
Currently there's a permission issue that has to be resolved,
to fix the issue in your laravel build by adding 
this step to your `.circleci/config.yml` file:

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
