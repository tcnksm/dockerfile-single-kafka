Dockerfile-single-kafka
====

[![MIT License](http://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)][LICENSE]
[![Docker Pulls](https://img.shields.io/docker/pulls/tcnksm/single-kafka.svg?style=flat-square)][dockerhub]

[LICENSE]: https://github.com/tcnksm/dockerfile-single-kafka/blob/master/LICENCE
[dockerhub]: https://registry.hub.docker.com/u/tcnksm/single-kafka/

Dockerfile for single node [kafka](http://kafka.apache.org/). It also include [zookeeper](https://zookeeper.apache.org/). This docker image is supposed to run for test on development environment, not for production usage. 

## Supported tags

`tcnksm/single-kafka` image support below tags. Link is its `Dockerfile`. 

- [`2.10-0.8.2.1` (0.8/2.10-0.8.2.1/Dockerfile)](0.8/2.10-0.8.2.1/Dockerfile)

Tag is correspond to `${SCALA_VERSION}-${KAFKA_VERSION}`. 

## Usage

To run single node kafka, 

```bash
$ docker run --rm -it --name single-kafka -p 9092:9092 -p 2181:2181 tcnksm/single-kafka
```

To connect it from outside of docker container, you need to expose 2 ports. `9092` for broker and `2181` for zookeeper. 

## Contribution

1. Fork ([https://github.com/tcnksm/dockerfile-single-kafka/fork](https://github.com/tcnksm/dockerfile-single-kafka/fork))
1. Create a feature branch
1. Commit your changes
1. Rebase your local changes against the master branch
1. Push it to your remote repository
1. Create new Pull Request

## Author

[Taichi Nakashima](https://github.com/tcnksm)
