FROM node:alpine

WORKDIR /usr/src/app
COPY backend-example-docker ./
RUN touch /usr/src/app/logs.txt
RUN npm install
EXPOSE 8000
CMD [ "npm", "start" ]