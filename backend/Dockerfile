FROM node:19.3.0-alpine3.16

############################################
# General Docker image configuration
############################################
WORKDIR /srv/app
EXPOSE 8080
ENTRYPOINT [ "entrypoints/production.sh" ]
CMD [ "npm", "start" ]

############################################
# System Dependencies
############################################
RUN apk update && apk add --no-cache dos2unix

############################################
# None root user
############################################
COPY [ "package.json", "package-lock.json",  "./"]
COPY [ "config", "config"]
COPY [ "src", "src"]
COPY [ "entrypoints", "entrypoints"]
RUN chown -R node:node /srv/app
USER node

############################################
# Building Application
############################################
RUN npm install
RUN dos2unix entrypoints/*

USER root
RUN chgrp -R 0 /srv/app && \
    chmod -R g=u /srv/app
USER node
