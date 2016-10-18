# drone-sftp

[![Build Status](https://travis-ci.org/appleboy/drone-sftp.svg?branch=master)](https://travis-ci.org/appleboy/drone-sftp) [![codecov](https://codecov.io/gh/appleboy/drone-sftp/branch/master/graph/badge.svg)](https://codecov.io/gh/appleboy/drone-sftp) [![Go Report Card](https://goreportcard.com/badge/github.com/appleboy/drone-sftp)](https://goreportcard.com/report/github.com/appleboy/drone-sftp)

[Drone](https://github.com/drone/drone) plugin to publish files and artifacts via SFTP. 

## Build

Build the binary with the following commands:

```
$ make build
```

## Testing

Test the package with the following command:

```
$ make test
```

## Docker

Build the docker image with the following commands:

```
$ make docker
```

Please note incorrectly building the image for the correct x64 linux and with
GCO disabled will result in an error when running the Docker image:

```
docker: Error response from daemon: Container command
'/bin/drone-sftp' not found or does not exist..
```

## Usage

Execute from the working directory:

```
docker run --rm \
  -e PLUGIN_BASE_URL=http://example.com \
  -e PLUGIN_USERNAME=xxxxxxx \
  -e PLUGIN_TOKEN=xxxxxxx \
  -e PLUGIN_JOB=xxxxxxx \
  -e DRONE_REPO_OWNER=appleboy \
  -e DRONE_REPO_NAME=go-hello \
  -e DRONE_COMMIT_SHA=e5e82b5eb3737205c25955dcc3dcacc839b7be52 \
  -e DRONE_COMMIT_BRANCH=master \
  -e DRONE_COMMIT_AUTHOR=appleboy \
  -e DRONE_BUILD_NUMBER=1 \
  -e DRONE_BUILD_STATUS=success \
  -e DRONE_BUILD_LINK=http://github.com/appleboy/go-hello \
  -v $(pwd):$(pwd) \
  -w $(pwd) \
  appleboy/drone-sftp
```
