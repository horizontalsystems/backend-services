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

ADD https://github.com/bcoin-org/bcoin/archive/v2.0.0.tar.gz /tmp/

RUN tar -xzf /tmp/v1.0.2.tar.gz -C .
RUN mv bcoin-1.0.2/* .
RUN rm -Rf bcoin-1.0.2
RUN npm install

COPY ./bcoin/conf/*  ./conf/

EXPOSE 8332