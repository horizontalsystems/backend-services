FROM node:10

WORKDIR /app/bcoin

RUN apt-get update && apt-get install -y --no-install-recommends software-properties-common
RUN apt-get update && apt-get install -y --no-install-recommends \
        build-essential \
        libpng-dev \
        libzmq3-dev \
        && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

ADD https://github.com/bcoin-org/bcoin/archive/v2.1.2.tar.gz /tmp/

RUN tar -xzf /tmp/v2.1.2.tar.gz -C .
RUN mv bcoin-2.1.2/* .
RUN rm -Rf bcoin-2.1.2
#RUN npm install bindings --save
#RUN npm install --save bcrypt-nodejs && npm uninstall --save bcrypt
#RUN npm install
RUN npm rebuild

COPY ./bcoin/conf/*  ./conf/

EXPOSE 8332