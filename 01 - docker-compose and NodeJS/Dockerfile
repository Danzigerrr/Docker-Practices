FROM node:6.9.1
RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app
COPY ./package.json ./
COPY ./package-lock.json ./
RUN npm install
COPY ./server.js ./src
CMD ["npm", "start"]
