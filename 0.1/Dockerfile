FROM ubuntu:16.04

MAINTAINER dotlinux dotlinux@hotmail.com

RUN apt-get -y update
RUN apt-get -y apt-get install git redis-server libboost1.58-all-dev nodejs-dev nodejs-legacy npm cmake libssl-dev

COPY install.sh /data/install/

RUN sh /data/install/install.sh
