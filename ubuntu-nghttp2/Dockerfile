FROM ubuntu:latest
MAINTAINER Erez Arbell <https://github.com/ErezArbell/docker-ubuntu-nghttp2>

ARG nghttp2_version=1.42.0

RUN apt-get update && \
\
DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends \
  g++ make binutils autoconf automake autotools-dev libtool \
  pkg-config zlib1g-dev libcunit1-dev libssl-dev \
  libxml2-dev libev-dev libevent-dev \
  libjansson-dev libc-ares-dev libjemalloc-dev libsystemd-dev \
  cython python3-dev python-setuptools python3-pip wget && \
rm -rf /var/lib/apt/lists/* && \
pip3 install setuptools && \
\
mkdir -p /workspace && cd /workspace && \
wget -c https://github.com/nghttp2/nghttp2/releases/download/v${nghttp2_version}/nghttp2-${nghttp2_version}.tar.gz -O - | tar -xz && \
cd /workspace/nghttp2-${nghttp2_version} && \
\
./configure && \
make && \
make install && \
\
apt-get remove --purge -y \
  g++ make binutils autoconf automake autotools-dev libtool \
  pkg-config zlib1g-dev libcunit1-dev libssl-dev \
  libxml2-dev libevent-dev \
  libjansson-dev libc-ares-dev libsystemd-dev \
  cython python3-dev python-setuptools python3-pip wget && \
apt-get autoremove --purge -y

RUN ldconfig
WORKDIR /workspace/nghttp2-${nghttp2_version}
