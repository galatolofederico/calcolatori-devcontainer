FROM mcr.microsoft.com/devcontainers/base:noble

ARG LIBCE_VERSION="3.0.5"
ENV HOME=/home/vscode/

RUN apt update && apt install -y build-essential gcc-multilib g++-multilib

WORKDIR /dist

RUN wget https://calcolatori.iet.unipi.it/resources/libce-${LIBCE_VERSION}.tar.gz
RUN tar xvzf libce-${LIBCE_VERSION}.tar.gz

WORKDIR /dist/libce-${LIBCE_VERSION}
RUN make && make install
RUN echo 'PATH=$HOME/CE/bin:$PATH' >> $HOME/.bashrc