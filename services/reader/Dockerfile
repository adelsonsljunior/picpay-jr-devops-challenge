FROM golang:1.24-alpine as builder

WORKDIR /app

COPY go.mod ./

COPY main.go ./

RUN go mod tidy

RUN CGO_ENABLED=0 GOOS=linux go build -o main .

EXPOSE 8081

CMD ["go","run","main.go"]