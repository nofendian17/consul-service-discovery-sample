FROM golang:1.17.0-alpine

RUN apk update && apk upgrade && apk add --no-cache bash git openssh
RUN go get github.com/hashicorp/consul/api

WORKDIR /app

COPY . .

RUN cd product-service && go mod download

RUN cd product-service && CGO_ENABLED=0 go build -o product-service .

CMD ["./product-service/product-service"]
EXPOSE 8100