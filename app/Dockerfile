FROM ubuntu:latest
MAINTAINER Roman Nesterov <me@rhrn.ru>

RUN apt-get -qy update && apt-get -y install \
 curl \
 g++ \
 make \
 pkg-config

#git \
#python-software-properties 
#software-properties-common

# sharp libs
RUN curl -s https://raw.githubusercontent.com/lovell/sharp/master/preinstall.sh | bash -

# nodejs 
RUN curl -sL https://deb.nodesource.com/setup_4.x | sudo bash - && \
 apt-get install -y nodejs

RUN mkdir -p /app/data

COPY src /app
WORKDIR /app

RUN npm config set registry https://registry.npmjs.org/ && npm install --production --verbose

EXPOSE 3000
