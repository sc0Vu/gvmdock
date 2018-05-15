FROM debian:jessie-slim

MAINTAINER Peter Lai <alk03073135@gmail.com>

# See https://github.com/eromoe/docker/commit/7dccc72bb24c715f176e4980ab59fd7aeb149a5f
RUN rm /bin/sh && ln -s /bin/bash /bin/sh

RUN apt-get -y update && \
    apt-get -y install curl git mercurial make binutils bison gcc build-essential

# Install gvm
# bash < <(curl -s -S -L https://raw.githubusercontent.com/moovweb/gvm/master/binscripts/gvm-installer)
RUN curl -s -S -L https://raw.githubusercontent.com/moovweb/gvm/master/binscripts/gvm-installer | bash

# Clean up
USER root
RUN apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Set default work directory
WORKDIR /usr/share/app
