FROM ubuntu:18.04

ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update -y && apt-get install -y --no-install-recommends\
    build-essential libssl-dev zlib1g-dev libbz2-dev\
    libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev\
    xz-utils tk-dev libffi-dev liblzma-dev python-openssl git

RUN useradd -ms /bin/bash developer
USER developer
WORKDIR /usr/local/app
RUN curl https://pyenv.run | bash && exec $SHELL
