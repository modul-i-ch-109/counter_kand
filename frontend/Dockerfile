FROM node:19.3.0-alpine

############################################
# General Docker image configuration
############################################
WORKDIR /srv/app
EXPOSE 3000
CMD ["npm", "run", "start"]
ENTRYPOINT [ "./entrypoint.sh" ]

############################################
# System Dependencies
############################################
RUN apk update && apk add --no-cache gettext dos2unix

############################################
# None root user
############################################
RUN chown -R node:node /srv/app
USER node
COPY --chown=node:node [ "package.json", "package-lock.json",  "./"]
COPY --chown=node:node [ "./entrypoint.sh", "./entrypoint.sh"]
COPY --chown=node:node [ "public", "public"]
COPY --chown=node:node [ "src", "src"]

############################################
# Building Application
############################################
RUN npm install
RUN npm run build
RUN dos2unix entrypoint.sh

USER root
RUN chgrp -R 0 /srv/app && \
    chmod -R g=u /srv/app
USER node
