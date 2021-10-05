FROM node:alpine

COPY package*.json /tmp/
RUN cd /tmp && npm install

RUN mkdir -p /opt/app && cp -a /tmp/node_modules /opt/app

WORKDIR /opt/app
COPY . /opt/app
ENV PORT=5000
EXPOSE 5000
#ENV API_URL=http://localhost:8000/
ENTRYPOINT [ "npm" ]
CMD [ "start" ]