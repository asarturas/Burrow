我是光年实验室高级招聘经理。
我在github上访问了你的开源项目，你的代码超赞。你最近有没有在看工作机会，我们在招软件开发工程师，拉钩和BOSS等招聘网站也发布了相关岗位，有公司和职位的详细信息。
我们公司在杭州，业务主要做流量增长，是很多大型互联网公司的流量顾问。公司弹性工作制，福利齐全，发展潜力大，良好的办公环境和学习氛围。
公司官网是http://www.gnlab.com,公司地址是杭州市西湖区古墩路紫金广场B座，若你感兴趣，欢迎与我联系，
电话是0571-88839161，手机号：18668131388，微信号：echo 'bGhsaGxoMTEyNAo='|base64 -D ,静待佳音。如有打扰，还请见谅，祝生活愉快工作顺利。

[![Join the chat at https://gitter.im/linkedin-Burrow/Lobby](https://badges.gitter.im/linkedin-Burrow/Lobby.svg)](https://gitter.im/linkedin-Burrow/Lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![Build Status](https://travis-ci.org/linkedin/kafka-tools.svg)](https://travis-ci.org/linkedin/kafka-tools)
[![go report card](https://goreportcard.com/badge/github.com/linkedin/Burrow)](https://goreportcard.com/report/github.com/linkedin/Burrow)
[![Coverage Status](https://coveralls.io/repos/github/linkedin/Burrow/badge.svg?branch=master)](https://coveralls.io/github/linkedin/Burrow?branch=master)
[![GoDoc](https://godoc.org/github.com/linkedin/Burrow?status.svg)](https://godoc.org/github.com/linkedin/Burrow)

# Burrow - Kafka Consumer Lag Checking


Burrow is a monitoring companion for [Apache Kafka](http://kafka.apache.org) that provides consumer lag checking as a service without the need for specifying thresholds. It monitors committed offsets for all consumers and calculates the status of those consumers on demand. An HTTP endpoint is provided to request status on demand, as well as provide other Kafka cluster information. There are also configurable notifiers that can send status out via email or HTTP calls to another service.

## Features
* NO THRESHOLDS! Groups are evaluated over a sliding window.
* Multiple Kafka Cluster support
* Automatically monitors all consumers using Kafka-committed offsets
* Configurable support for Zookeeper-committed offsets
* Configurable support for Storm-committed offsets
* HTTP endpoint for consumer group status, as well as broker and consumer information
* Configurable emailer for sending alerts for specific groups
* Configurable HTTP client for sending alerts to another system for all groups

## Getting Started
### Prerequisites
Burrow is written in Go, so before you get started, you should [install and set up Go](https://golang.org/doc/install).

If you have not yet installed the [Go Dependency Management Tool](https://github.com/golang/dep), please go over there and follow their short installation instructions. dep is used to automatically pull in the dependencies for Burrow so you don't have to chase them all down.

### Build and Install
```
$ go get github.com/linkedin/Burrow
$ cd $GOPATH/src/github.com/linkedin/Burrow
$ dep ensure
$ go install
```

### Running Burrow
```
$ $GOPATH/bin/Burrow --config-dir /path/containing/config
```

### Using Docker
A Docker file is available which builds this project on top of an Alpine Linux image.
To use it, build your docker container, mount your Burrow configuration into `/etc/burrow` and run docker.

A [Docker Compose](https://docs.docker.com/compose/) is also available for quick and easy development.

Install Docker Compose and then:

1. Build the docker container:
   ```
   docker-compose build
   ```

2. Run the docker compose stack which includes kafka and zookeeper:
   ```
   docker-compose down; docker-compose up
   ```

3. Some test topics have already been created by default and Burrow can be accessed on port 8000 of your docker-machine. e.g. `http://192.168.99.100:8000/v3/kafka`


### Configuration
For information on how to write your configuration file, check out the [detailed wiki](https://github.com/linkedin/Burrow/wiki)

## License
Copyright 2017 LinkedIn Corp. Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License.
You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR
CONDITIONS OF ANY KIND, either express or implied.

