# build stage
FROM golang:1.16 as builder

WORKDIR /app

COPY . /app

RUN go mod download && go mod verify &&\
    cd /app && go build -o backend

# final stage
FROM alpine

WORKDIR /app

COPY --from=builder /app/backend /app/

ENTRYPOINT ["./backend"] 
