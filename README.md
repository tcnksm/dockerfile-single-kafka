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
$ docker run --rm -it \
    --name single-kafka \
    --publish 9092:9092 \
    --publish 2181:2181 \
    --env ADVERTISED_HOST=192.168.59.103 \
    --env ADVERTISED_PORT=9092 \
    tcnksm/single-kafka
```
    
To connect it from outside of docker container, you need to expose 2 ports and set 2 env variables. `9092` for broker and `2181` for zookeeper. `ADVERTISED_HOST` is host IP where kafka works (in this case it is docker host) and `ADVERTISED_PORT` is broker port.

## Testing

To try kafka you can use [kafkacat](https://github.com/edenhill/kafkacat),

```bash
$ echo 'This is test message' | kafkacat -t test-topic -b 192.168.59.103:9092
```

```bash
$ kafkacat -C -t test-topic -b 192.168.59.103:9092
```

## Contribution

1. Fork ([https://github.com/tcnksm/dockerfile-single-kafka/fork](https://github.com/tcnksm/dockerfile-single-kafka/fork))
1. Create a feature branch
1. Commit your changes
1. Rebase your local changes against the master branch
1. Push it to your remote repository
1. Create new Pull Request

## Author

[Taichi Nakashima](https://github.com/tcnksm)
