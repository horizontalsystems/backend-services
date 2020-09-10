FROM ubuntu:xenial

WORKDIR /app/dashcore

RUN apt-get update && apt-get install -y --no-install-recommends software-properties-common
RUN apt-get update && apt-get install -y --no-install-recommends \
        build-essential \
        libpng-dev \
        libzmq3-dev \
        && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

ADD https://github.com/dashpay/dash/releases/download/v0.15.0.0/dashcore-0.15.0.0-x86_64-linux-gnu.tar.gz /tmp/
RUN tar -xzf /tmp/dashcore-0.15.0.0-x86_64-linux-gnu.tar.gz -C .
RUN mv dashcore-0.15.0/* .
RUN rm -Rf dashcore-0.15.0

COPY ./dashcore/conf ./conf

EXPOSE 9998 28332