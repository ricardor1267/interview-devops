FROM node:12.14.0 AS base


WORKDIR /usr/src/app

COPY package*.json ./

RUN npm install

COPY . .

#puerto de trabajo
EXPOSE 4100


# This command starts up the app
CMD npm run start