FROM node:16-alpine

# Create app directory
WORKDIR /usr/src/clembot.site

ENV PROD=1

ARG DISCORD_CLIENT_ID_ARG
ENV DISCORD_CLIENT_ID ${DISCORD_CLIENT_ID_ARG}

ARG DISCORD_CLIENT_SECRET_ARG
ENV DISCORD_CLIENT_SECRET ${DISCORD_CLIENT_SECRET_ARG}

ARG OAUTH_PERMISSIONS_ARG
ENV OAUTH_PERMISSIONS ${OAUTH_PERMISSIONS_ARG}

ENV HOST 0.0.0.0

COPY package*.json ./

COPY . .

RUN yarn install && yarn build

CMD ["yarn", "start"]
