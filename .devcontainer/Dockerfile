FROM mcr.microsoft.com/devcontainers/base:noble

ARG LIBCE_VERSION="3.0.5"
ARG QEMU_VERSION="8.2.1-1"

ENV HOME=/home/vscode/

RUN apt update && apt install -y build-essential gcc-multilib g++-multilib
RUN apt update && apt install -y python3 zlib1g-dev libsdl2-dev libpixman-1-dev libjson-xs-perl ninja-build ncurses-dev python3-pip

WORKDIR /dist
RUN wget https://calcolatori.iet.unipi.it/resources/libce-${LIBCE_VERSION}.tar.gz
RUN wget https://calcolatori.iet.unipi.it/resources/qemu-ce-${QEMU_VERSION}.tar.gz

RUN tar -xzvf libce-${LIBCE_VERSION}.tar.gz
RUN tar -xzvf qemu-ce-${QEMU_VERSION}.tar.gz

WORKDIR /dist/libce-${LIBCE_VERSION}
RUN make && make install
RUN echo 'PATH=$HOME/CE/bin:$PATH' >> $HOME/.bashrc

WORKDIR /dist/qemu-ce-${QEMU_VERSION}
RUN sh /dist/qemu-ce-${QEMU_VERSION}/install