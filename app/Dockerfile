FROM node:13
LABEL version="1.0"
LABEL name="test-sre"
RUN mkdir -p /usr/src/app
ARG WEB_PORT

WORKDIR /usr/src/app

COPY package.json /usr/src/app
RUN npm install 
COPY . /usr/src/app

HEALTHCHECK --interval=15s --timeout=10s --retries=3 CMD curl -f http://localhost:${WEB_PORT}/health || exit 1

EXPOSE 8080

CMD [ "node", "index.js" ]