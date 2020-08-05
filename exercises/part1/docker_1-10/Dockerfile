FROM node:alpine

WORKDIR /usr/src/app
COPY frontend-example-docker .
EXPOSE 5000
RUN npm install
ENTRYPOINT [ "npm" ]
CMD [ "start" ]