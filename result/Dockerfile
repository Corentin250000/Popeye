FROM node:20.0.0-alpine

WORKDIR /result

COPY . .

RUN npm install

EXPOSE 80

CMD ["node", "server.js"]

