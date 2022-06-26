# Grafana Tempo packaged by Bitnami

## What is Grafana Tempo?

> Grafana Tempo is a distributed tracing system that has out-of-the-box integration with Grafana. It is highly scalable and works with many popular tracing protocols.

[Overview of Grafana Tempo](https://github.com/grafana/tempo)

Trademarks: This software listing is packaged by Bitnami. The respective trademarks mentioned in the offering are owned by the respective companies, and use of them does not imply any affiliation or endorsement.

## TL;DR

```console
$ docker run --name grafana-tempo bitnami/grafana-tempo:latest
```

## Why use Bitnami Images?

* Bitnami closely tracks upstream source changes and promptly publishes new versions of this image using our automated systems.
* With Bitnami images the latest bug fixes and features are available as soon as possible.
* Bitnami containers, virtual machines and cloud images use the same components and configuration approach - making it easy to switch between formats based on your project needs.
* All our images are based on [minideb](https://github.com/bitnami/minideb) a minimalist Debian based container image which gives you a small base container image and the familiarity of a leading Linux distribution.
* All Bitnami images available in Docker Hub are signed with [Docker Content Trust (DCT)](https://docs.docker.com/engine/security/trust/content_trust/). You can use `DOCKER_CONTENT_TRUST=1` to verify the integrity of the images.
* Bitnami container images are released on a regular basis with the latest distribution packages available.

## Supported tags and respective `Dockerfile` links

Learn more about the Bitnami tagging policy and the difference between rolling tags and immutable tags [in our documentation page](https://docs.bitnami.com/tutorials/understand-rolling-tags-containers/).


* [`1`, `1-debian-11`, `1.4.1`, `1.4.1-debian-11-r8`, `latest` (1/debian-11/Dockerfile)](https://github.com/bitnami/bitnami-docker-grafana-tempo/blob/1.4.1-debian-11-r8/1/debian-11/Dockerfile)

Subscribe to project updates by watching the [bitnami/grafana-tempo GitHub repo](https://github.com/bitnami/bitnami-docker-grafana-tempo).

## Get this image

The recommended way to get the Bitnami grafana-tempo Docker Image is to pull the prebuilt image from the [Docker Hub Registry](https://hub.docker.com/r/bitnami/grafana-tempo).

```console
$ docker pull bitnami/grafana-tempo:latest
```

To use a specific version, you can pull a versioned tag. You can view the [list of available versions](https://hub.docker.com/r/bitnami/grafana-tempo/tags/) in the Docker Hub Registry.

```console
$ docker pull bitnami/grafana-tempo:[TAG]
```

If you wish, you can also build the image yourself.

```console
$ docker build -t bitnami/grafana-tempo:latest 'https://github.com/bitnami/bitnami-docker-grafana-tempo.git#master:1/debian-11'
```

## Why use a non-root container?

Non-root container images add an extra layer of security and are generally recommended for production environments. However, because they run as a non-root user, privileged tasks are typically off-limits. Learn more about non-root containers [in our docs](https://docs.bitnami.com/tutorials/work-with-non-root-containers/).

## Configuration

### Running commands

To run commands inside this container you can use `docker run`, for example to execute `grafana-tempo --version` you can follow the example below:

```console
$ docker run --rm --name grafana-tempo bitnami/grafana-tempo:latest -- --version
```

In order for the container to work, you need to mount your custom `tempo.yaml` file in `/bitnami/grafana-tempo/conf/`. The following example runs Grafana Tempo with a custom configuration file:

```console
$ docker run --rm --name grafana-tempo -v /path/to/tempo.yaml:/bitnami/grafana-tempo/conf/tempo.yaml bitnami/grafana-tempo:latest
```

Using docker-compose:

```yaml
version: '2'
services:

  grafana-tempo:
    image: grafana-tempo
    volumes:
      - /path/to/tempo.yaml:/bitnami/grafana-tempo/conf/tempo.yaml
```

Check the [official Grafana Tempo documentation](https://grafana.com/docs/tempo/latest/configuration/) to understand the possible configurations.

## Contributing

We'd love for you to contribute to this container. You can request new features by creating an [issue](https://github.com/bitnami/bitnami-docker-grafana-tempo/issues), or submit a [pull request](https://github.com/bitnami/bitnami-docker-grafana-tempo/pulls) with your contribution.

## Issues

If you encountered a problem running this container, you can file an [issue](https://github.com/bitnami/bitnami-docker-grafana-tempo/issues/new). For us to provide better support, be sure to include the following information in your issue:

- Host OS and version
- Docker version (`docker version`)
- Output of `docker info`
- Version of this container
- The command you used to run the container, and any relevant output you saw (masking any sensitive information)

## License

Copyright &copy; 2022 Bitnami

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
