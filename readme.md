# Laravel CircleCI 2.0 Docker Image
Docker container for running tests/build in CircleCI 2.0, 
meant for the PHP Framework [Laravel](https://laravel.com/).

This repo builds off of the `circleci/php:7.2-fpm-stretch-node-browsers` image.

This is built nightly and pushed to the `latest` tag.

## Build Locally
Run: `docker build -t ericdowell/laravel-circleci .`

