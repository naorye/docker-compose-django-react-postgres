FROM node:12.2.0-alpine

WORKDIR /app/frontend

ENV PATH /app/node_modules/.bin:$PATH

COPY package.json .

RUN npm install --silent

COPY src src

COPY public public

COPY .env .env

# RUN npm install react-scripts@3.0.1 -g --silent

EXPOSE 3000

CMD npm start