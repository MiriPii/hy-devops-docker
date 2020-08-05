FROM node:alpine

COPY package*.json /tmp/
RUN cd /tmp && npm install

RUN mkdir -p /opt/app && cp -a /tmp/node_modules /opt/app

WORKDIR /opt/app
COPY . /opt/app

RUN touch /opt/app/logs.txt
EXPOSE 8000
ENV FRONT_URL=http://localhost:5000
CMD [ "npm", "start" ]