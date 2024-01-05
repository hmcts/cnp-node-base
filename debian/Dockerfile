ARG NODE_VERSION=20
FROM hmctspublic.azurecr.io/imported/library/node:$NODE_VERSION-bookworm-slim

ENV APP_USER=hmcts \
    WORKDIR=/opt/.yarn

WORKDIR ${WORKDIR}

RUN userdel node \
    && addgroup --system --gid 1000 $APP_USER \
    && adduser --system --gid 1000 -uid 1000 --disabled-password --disabled-login $APP_USER \
    && chown -R $APP_USER:$APP_USER $WORKDIR \
    && yarn set version 3.0.0

USER hmcts
CMD ["yarn", "start"]
