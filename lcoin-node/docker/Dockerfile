FROM node:8

WORKDIR /app/lcoin
# RUN apk add --no-cache --virtual .gyp \
#         bash \
#         python \
#         make \
#         g++ \
#     && apk del .gyp

# Install app dependencies
COPY package*.json ./
RUN npm install

COPY . .

EXPOSE 9332

# CMD ["/app/lcoin/bin/lcoin", "--config /app/lcoin/conf/lcoin.conf"]