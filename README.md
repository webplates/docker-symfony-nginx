# Symfony Nginx webserver container

This container works together with [symfony-standard](https://github.com/webplates/symfony-standard) and its derivatives.


## Environment variables

| Variable | Default | Description         |
| -------- | ------- | ------------------- |
| FPM_HOST | app     | PHP FPM hostname    |
| FPM_PORT | 9000    | PHP FPM public port |


## Versioning strategy

The containers follow the versions of the official parent nginx image versioning: https://hub.docker.com/_/nginx/

The four "main" versions are separated into branches, the version numbers are represented as tags. For example:

There are five branches: master, latest, stable, mainline-alpine, stable-alpine

Master contains the nginx config and a non-functional template Dockerfile.

For the latest branch the respective tags are: 1, 1.11, 1.11.1

In case the above tags change (like there is a new minor version 1.11.2 => 1.11) or there is a change in this repo (nginx config) the above branches are updated, the tags are force pushed. In order to maintain backward compatibility, every nginx config changes receive a revision tag too, starting with revision one. Revision tags are created BEFORE applying any changes which means you need to update your configuration when a BC break is found, although there is a low chance for that.

The recommended usage of this image is to rely on the branch-versions and in case of incompatibility, fall back to a numeric version tag.
