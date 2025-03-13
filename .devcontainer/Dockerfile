FROM mcr.microsoft.com/devcontainers/base:noble

ARG LIBCE_VERSION="4.1"
ARG QEMU_VERSION="9.2.2-3"

ENV HOME=/home/vscode/

RUN apt update && apt install -y build-essential gcc-i686-linux-gnu g++-i686-linux-gnu
RUN apt update && apt install -y python3 python3-venv zlib1g-dev  \
		libgtk-3-dev libpulse-dev libpixman-1-dev libjson-xs-perl \
		ninja-build ncurses-dev git
RUN apt update && apt install -y gdb-multiarch

RUN mkdir /dist
RUN chown vscode:vscode -R /dist

USER vscode
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

COPY ./bin/scarica-esame $HOME/CE/bin
