FROM ubuntu:20.04

RUN apt-get update && \
  DEBIAN_FRONTEND=noninteractive \
  apt-get install -y --no-install-recommends \
  wget \
  curl \
  vim \
  iputils-ping \
  dnsutils \
  iproute2 \
  net-tools \
  pciutils \
  openssh-client \
  jq && \
  rm -rf /var/lib/apt/lists/*

RUN wget --no-check-certificate --quiet -O /usr/bin/yq https://github.com/mikefarah/yq/releases/download/v4.42.1/yq_linux_amd64 && chmod +x /usr/bin/yq
