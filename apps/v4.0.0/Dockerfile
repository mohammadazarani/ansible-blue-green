FROM golang:1.14

RUN mkdir -p /app

WORKDIR /app

COPY . .

RUN  go build  ./main.go

CMD ["./main"]

