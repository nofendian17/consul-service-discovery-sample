FROM golang:1.17.0-alpine

RUN apk update && apk upgrade && apk add --no-cache bash git openssh
RUN go get github.com/hashicorp/consul/api

WORKDIR /app

COPY . .

RUN cd user-service && go mod download

RUN cd user-service && CGO_ENABLED=0 go build -o user-service .

CMD ["./user-service/user-service"]
EXPOSE 8100