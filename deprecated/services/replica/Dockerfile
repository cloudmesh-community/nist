FROM ubuntu:18.04
MAINTAINER Gregor von Laszewski <laszewski@gmail.com>


RUN apt-get update -q && apt-get install -qy \
    build-essential \
    python-dev \
    python-pip \
    libssl-dev \
    zlib1g-dev \
    libbz2-dev \
    libreadline-dev \
    libsqlite3-dev \
    wget \
    curl \
    emacs \
    git-core \
    software-properties-common


RUN add-apt-repository universe

#RUN curl -L https://raw.githubusercontent.com/pyenv/pyenv-installer/main/bin/pyenv-installer | bash

RUN git clone git://github.com/yyuu/pyenv.git .pyenv
RUN git clone https://github.com/yyuu/pyenv-virtualenv.git ~/.pyenv/plugins/pyenv-virtualenv

ENV HOME  /
ENV PYENV_ROOT /.pyenv
ENV PATH $PYENV_ROOT/shims:$PYENV_ROOT/bin:$PATH

RUN pyenv install 3.6.4
RUN pyenv global 3.6.4
RUN python -m ensurepip


WORKDIR /cloudmesh

RUN git clone https://github.com/cloudmesh-community/nist.git

#VOLUME ["/cloudmesh"]
