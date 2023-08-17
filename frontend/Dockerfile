# build stage
FROM golang:1.16 as builder

WORKDIR /app

COPY . /app

RUN go mod download && go mod verify &&\
    cd /app && go build -ldflags "-linkmode 'external' -extldflags '-static'" frontend

# final stage
FROM alpine

WORKDIR /app

COPY --from=builder /app/frontend /app/

CMD ["./frontend"]