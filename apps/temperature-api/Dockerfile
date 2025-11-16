FROM golang:1.22-alpine AS builder

WORKDIR /app

COPY go.mod .
RUN go mod download

COPY main.go .

RUN CGO_ENABLED=0 GOOS=linux go build -o temperature-api main.go

FROM alpine:latest

RUN apk --no-cache add ca-certificates

WORKDIR /root/

COPY --from=builder /app/temperature-api .

EXPOSE 8081

CMD ["./temperature-api"]

