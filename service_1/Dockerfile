FROM golang:1.11 AS builder
WORKDIR /app
COPY . .
RUN go build -o main .
EXPOSE 8001
CMD ["./main"]
