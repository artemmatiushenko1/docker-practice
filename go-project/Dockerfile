# stage 1
FROM golang:1.17.7-alpine as build

WORKDIR /usr/src/app

COPY go.mod go.sum ./

RUN go mod download && go mod verify

COPY . .

RUN CGO_ENABLED=0 go build -v -o ./build/fizzbuzz .

# stage 2
FROM scratch

COPY --from=build /usr/src/app/build/fizzbuzz /app/fizzbuzz

EXPOSE 8080

ENTRYPOINT [ "/app/fizzbuzz" ]
