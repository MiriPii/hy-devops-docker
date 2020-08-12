FROM ubuntu:18.04

# Setup env for tzdata etc.
#RUN ln -fs /usr/share/zoneinfo/Europe/Helsinki /etc/localtime &&\
#    DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends tzdata
#RUN dpkg-reconfigure --frontend noninteractive tzdata
ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update -y && apt-get install -y --no-install-recommends\
    build-essential libssl-dev zlib1g-dev libbz2-dev\
    libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev\
    xz-utils tk-dev libffi-dev liblzma-dev python-openssl git

RUN curl https://pyenv.run | bash && exec $SHELL
