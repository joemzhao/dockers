FROM ubuntu:20.04

LABEL org.opencontainers.image.authors="mengjie.zhao@outlook.com"

USER root

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
    emacs \
    zsh \
    wget \
    curl \
    htop \
    bzip2 \
    unzip \
    libsm6 \
    && apt-get clean 

# shell
RUN git clone git://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh \
    && cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc \
    && chsh -s /bin/zsh

# Configure locales
RUN echo "en_US.UTF-8 UTF-8" > /etc/locale.gen && \
    locale-gen

# Configure Environment
RUN apt-get -qq install language-pack-en
ENV SHELL /bin/zsh
ENV LC_ALL en_US.UTF-8
ENV LANG en_US.UTF-8
ENV LANGUAGE en_US.UTF-8
ENV PYTHONIOENCODING UTF-8