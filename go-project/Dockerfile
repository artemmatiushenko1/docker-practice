FROM golang:1.17.7-alpine

WORKDIR /usr/src/app

COPY go.mod go.sum ./

RUN go mod download && go mod verify

COPY . .

RUN go build -v -o ./build/fizzbuzz .

EXPOSE 8080

ENTRYPOINT [ "./build/fizzbuzz" ]
