FROM golang:1.13.11-alpine

RUN apk update \
    && apk add git openssl nss-tools \
    && rm -rf /var/cache/apk/*


RUN cd /go && \
    git clone https://github.com/FiloSottile/mkcert && cd mkcert && \
    go build -ldflags "-X main.Version=$(git describe --tags)" && \
    ./mkcert -install && \
    cp /root/.local/share/mkcert/rootCA*.pem ./ && \
    ./mkcert -key-file https-api.key -cert-file https-api.pem rostoreapi 192.168.1.2 localhost 127.0.0.1 ::1 && \
    openssl pkcs12 -export -out https-api.pfx -inkey https-api.key -in https-api.pem -certfile rootCA.pem -passout pass:https-api

