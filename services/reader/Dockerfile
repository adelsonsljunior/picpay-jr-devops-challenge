FROM golang:1.24-alpine AS builder

WORKDIR /app

COPY go.mod ./

COPY main.go ./

RUN go mod tidy

RUN CGO_ENABLED=0 GOOS=linux go build -o main .

FROM cgr.dev/chainguard/static:latest

COPY --from=builder /app/main /

USER nonroot

EXPOSE 8081

CMD ["/main"]