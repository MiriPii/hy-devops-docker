FROM ubuntu:16.04
RUN apt-get update && apt-get install -y curl --no-install-recommends

COPY my.script .
RUN chmod +x ./my.script
CMD [ "./my.script" ]