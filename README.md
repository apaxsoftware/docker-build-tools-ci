# Docker Build Tools CI

[![docker pull apax/build-tools](https://img.shields.io/badge/dockerhub-image-blue.svg?logo=Docker)](https://hub.docker.com/repository/docker/apax/build-tools)

This is the source Dockerfile for the [apax/build-tools](https://hub.docker.com/repository/docker/apax/build-tools) docker image.

## Image Contents

- [CircleCI PHP 7.4/8.1, Node, Headless browser Docker base image](https://hub.docker.com/r/circleci/php)
- [Terminus](https://github.com/pantheon-systems/terminus)
- Terminus plugins
  - [Terminus Build Tools Plugin](https://github.com/pantheon-systems/terminus-build-tools-plugin)
  - [Terminus Secrets Plugin](https://github.com/pantheon-systems/terminus-secrets-plugin)
  - [Terminus Rsync Plugin](https://github.com/pantheon-systems/terminus-rsync-plugin)
  - [Terminus Quicksilver Plugin](https://github.com/pantheon-systems/terminus-quicksilver-plugin)
  - [Terminus Composer Plugin](https://github.com/pantheon-systems/terminus-composer-plugin)
  - [Terminus Drupal Console Plugin](https://github.com/pantheon-systems/terminus-drupal-console-plugin)
  - [Terminus Mass Update Plugin](https://github.com/pantheon-systems/terminus-mass-update)
  - [Terminus Aliases Plugin](https://github.com/pantheon-systems/terminus-aliases-plugin)
  - [Terminus CLU Plugin](https://github.com/pantheon-systems/terminus-clu-plugin)
- Test tools
  - headless chrome
  - phpunit
  - bats
  - behat
  - php_codesniffer
  - hub
  - lab
- Test scripts

## Branches

- 8.x: Most recent form of pantheon. Produces php7.4, php8.1, php8.2, php8.3 image tags.
- 6.x: Older deprecated fork of pantheon

## 8.x Docker images

### Building the image

From project root:

```
# PHPVERSION could be 7.4, 8.0, 8.1, 8.2 or 8.3.
PHPVERSION=7.4
docker build --build-arg PHPVERSION=$PHPVERSION -t apax/build-tools:php${PHPVERSION} .
```

### Using the image

#### Image name and tag

- apax/build-tools:php7.4
- apax/build-tools:php8.1
- apax/build-tools:php8.2
- apax/build-tools:php8.3

#### Usage example

Set the right image tag in the following files and it will work as expected:

- [Drupal 8 Github Actions](https://github.com/pantheon-systems/example-drops-8-composer/blob/master/.ci/.github/workflows/build_deploy_and_test.yml)
- [Drupal 8 CircleCI](https://github.com/pantheon-systems/example-drops-8-composer/blob/master/.circleci/config.yml)
- [Drupal 8 GitlabCI](https://github.com/pantheon-systems/example-drops-8-composer/blob/master/.gitlab-ci.yml)
- [Drupal 8 Bitbucket Pipelines](https://github.com/pantheon-systems/example-drops-8-composer/blob/master/bitbucket-pipelines.yml)
