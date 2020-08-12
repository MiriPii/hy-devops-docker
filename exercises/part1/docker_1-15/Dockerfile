FROM ubuntu:18.04

WORKDIR /mpw/cli
RUN apt-get update -y &&\
    apt-get install -y --no-install-recommends\
    build-essential cmake curl ca-certificates\
    libsodium-dev libxml2-dev\
    libncurses-dev libjson-c-dev

RUN curl https://masterpassword.app/masterpassword-cli.tar.gz --output mpw.tar.gz
RUN tar -xzf mpw.tar.gz && rm mpw.tar.gz
RUN cmake -DBUILD_MPW_TESTS=ON . && make && make install
RUN ./mpw_tests
RUN cp mpw /usr/local/bin/

ENTRYPOINT [ "mpw" ]