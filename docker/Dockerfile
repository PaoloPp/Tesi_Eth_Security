FROM ubuntu:20.04

RUN echo 'root:admin' | chpasswd
RUN apt-get update
RUN apt-get -y install software-properties-common
RUN apt -y install git
RUN add-apt-repository -y ppa:ethereum/ethereum
RUN apt-get -y install ethereum
RUN git clone https://github.com/cubedro/eth-netstats.git
RUN git clone https://github.com/cubedro/eth-net-intelligence-api.git
RUN apt install -y nodejs npm
RUN npm install
RUN npm install -g grunt-cli
RUN mkdir ethereum
RUN mkdir ethereum/genesys
RUN mkdir ethereum/data
RUN mkdir ethereum/data/node
COPY ./Eth/genesys.json ethereum/genesys/ 
RUN geth init --datadir ethereum/data/node ethereum/genesys/genesys.json
CMD /bin/bash