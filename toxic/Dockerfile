#
# Builds a docker image to use for tox runs.
#
FROM ubuntu:20.04

VOLUME /repo

WORKDIR /repo

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get -y install apt-utils && apt-get -y install locales
RUN locale-gen en_US.UTF-8

ENV SONAR_SCANNER_VERSION 4.2.0.1873
ENV LANG=en_US.UTF-8
ENV LANGUAGE=en_US:en
ENV LC_ALL=en_US.UTF-8
ENV SONAR_SCANNER_HOME=/sonar-scanner-${SONAR_SCANNER_VERSION}-linux
ENV SONAR_SCANNER_OPTS="-server"

ENV PATH="${SONAR_SCANNER_HOME}/sonar-scanner-${SONAR_SCANNER_VERSION}-linux/bin:${PATH}"

COPY provision.sh /

RUN /provision.sh
