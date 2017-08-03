FROM node:7
ENV http_proxy=http://webproxy.comp.db.de:8080
ENV https_proxy=http://webproxy.comp.db.de:8080
RUN git clone https://github.com/cubedro/eth-netstats
RUN cd /eth-netstats && npm install
RUN cd /eth-netstats && npm install -g grunt-cli
RUN cd /eth-netstats && grunt

WORKDIR /eth-netstats

EXPOSE 3000

CMD ["npm", "start"]
