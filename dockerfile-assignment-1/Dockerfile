# use this empty Dockerfile to build your assignment

# NOTE: The instructions are now in the README.md file in this directory.

# all images must have a FROM
# usually from a minimal Linux distribution like debian or (even better) alpine
# if you truly want to start with an empty container, use FROM scratch

FROM node:6-alpine

EXPOSE 3000

RUN apk add --update tini

RUN mkdir -p /usr/src/app

WORKDIR /usr/src/app

COPY package.json package.json

RUN npm install && npm cache clean

COPY . .

CMD [ "tini","--","node","./bin/www"]
