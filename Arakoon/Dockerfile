FROM ubuntu:14.04
MAINTAINER Jonas Libbrecht <jonas.libbrecht@yahoo.com>

# Installation
RUN apt-get update && apt-get install -y wget sudo vim libev4 libsnappy1
RUN wget https://github.com/openvstorage/arakoon/releases/download/1.9.9/arakoon_1.9.9_amd64.deb && \
    dpkg -i arakoon_1.9.9_amd64.deb; \
    rm arakoon_1.9.9_amd64.deb

# Configuration
RUN mkdir /etc/arakoon; \
    mkdir -p /var/lib/arakoon/arakoon_0

COPY arakoon.ini /etc/arakoon/arakoon.ini
CMD arakoon --node arakoon_0 -config /etc/arakoon/arakoon.ini -autofix -start 
