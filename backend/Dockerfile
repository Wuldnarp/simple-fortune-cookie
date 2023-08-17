# First stage: Build the Go application
FROM golang:1.19 AS builder
WORKDIR /app
COPY . .
# Download dependencies
RUN go mod download
EXPOSE 9000
# Build the Go application
RUN CGO_ENABLED=0 GOOS=linux go build -o main
ENTRYPOINT [ "./main" ]
