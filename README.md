## Dockerfile for Concourse pipelines


This repository contains **Dockerfile** of JDK8 official release, Maven 3.5.2, and a settings file for Spring Milestone repositories. The image built from this repository is aimed to be used in Concourse pipelines.

### Base Docker Image

* [dockerfile/ubuntu](http://dockerfile.github.io/#/ubuntu)


### Docker Tags

`dockerfile/java` provides only one tagged image:

* `oracle-java8`: Oracle Java 8 JDK

For example, you can run a `Oracle Java 8 with Maven 3.5.2` container with the following command:

    docker run -it --rm dmrlvnt/jdk8-maven3.5.2:latest


### Installation

1. Install [Docker](https://www.docker.com/).

2. Build an image from Dockerfile: `docker build -t="dmrlvnt/jdk8-maven3.5.2" github.com/dmrlvnt/jdk8-maven3.5.2`)


### Usage

    docker run -it --rm dmrlvnt/jdk8-maven3.5.2:latest

#### Run `javac`

    docker run -it --rm dmrlvnt/jdk8-maven3.5.2:latest javac -version

#### Run `mvn`

    docker run -it --rm dmrlvnt/jdk8-maven3.5.2:latest mvn --version

#### Run `mvn` to get a dependency from Spring Milestone repositories

    docker run -it --rm dmrlvnt/jdk8-maven3.5.2:latest mvn dependency:get -Dartifact=org.springframework.boot:spring-boot-starter-test:LATEST:jar

