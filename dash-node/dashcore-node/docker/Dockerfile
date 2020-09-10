FROM node:10

WORKDIR /app

RUN git clone https://github.com/dashevo/dashcore-node

WORKDIR /app/dashcore-node

RUN npm install

COPY ./dashcore-node/conf/*  ./

RUN ./bin/dashcore-node install @dashevo/insight-api
RUN ./bin/dashcore-node install @dashevo/insight-ui

EXPOSE 3001
