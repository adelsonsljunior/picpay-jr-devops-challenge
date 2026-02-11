FROM node:24-alpine

WORKDIR /app

ADD . .

RUN npm install -g serve

EXPOSE 3000

CMD "serve"