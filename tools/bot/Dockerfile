FROM golang:1.12.5-stretch

WORKDIR apps/iotex-bot

RUN apt-get install -y --no-install-recommends make
RUN git clone https://github.com/iotexproject/iotex-core
RUN cd iotex-core/tools/bot && \
    make build && \
    cp ./bot /usr/local/bin/bot  && \
    mkdir -p /etc/iotex/ && \
    rm -rf apps/iotex-bot

CMD [ "bot -config-path=/etc/iotex/config.yaml"]