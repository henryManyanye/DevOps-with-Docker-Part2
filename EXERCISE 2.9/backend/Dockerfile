FROM ubuntu:latest

EXPOSE 8080

WORKDIR /usr/src/app

COPY . .
COPY go1.16.linux-amd64.tar.gz .

ENV REQUEST_ORIGIN=http://localhost:5000

RUN <<EOF 
apt-get update && apt-get install -y ca-certificates openssl
rm -rf /usr/local/go && tar -C /usr/local -xzf go1.16.linux-amd64.tar.gz
export PATH=$PATH:/usr/local/go/bin && go build
EOF
 
CMD ./server
 



