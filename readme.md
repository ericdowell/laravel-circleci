# Laravel CircleCI 2.0 Docker Image
This is a Docker container for running tests/build in CircleCI 2.0. 
The main application this is meant for is the PHP Framework [Laravel](https://laravel.com/).

This repo builds off of the `circleci/php:7.2-fpm-stretch-node-browsers` image.

This is built nightly and pushed to the `latest` tag.

## Build Locally
Run: `docker build -t ericdowell/laravel-circleci .`

