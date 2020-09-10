FROM node:8

WORKDIR /app/lcoin
COPY package*.json ./
RUN npm install

COPY . .

EXPOSE 9332
