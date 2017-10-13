FROM ubuntu:14.04

MAINTAINER joemzhao <mengjie.zhao@outlook.com>

USER root

RUN echo 'debconf debconf/frontend select Noninteractive' | debconf-set-selections

RUN apt-get update && \
        apt-get install -yq --no-install-recommends \
	      pkg-config \
    build-essential \
    ca-certificates \
    gcc \
    make

RUN apt-get install -y \
    git \
    vim \
    wget \
    curl \
    htop \
    bzip2 \
    unzip \
    libsm6 \
    && apt-get clean

RUN echo "en_US.UTF-8 UTF-8" > /etc/locale.gen && \
    locale-gen

RUN apt-get -qq install language-pack-en
ENV SHELL /bin/zsh
ENV LC_ALL en_US.UTF-8
ENV LANG en_US.UTF-8
ENV LANGUAGE en_US.UTF-8
ENV PYTHONIOENCODING UTF-8
