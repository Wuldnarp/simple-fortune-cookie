# First stage: Build the Go application
FROM golang:1.19 AS builder
WORKDIR /app
COPY . .
# Download dependencies
RUN go mod download

# Build the Go application
RUN CGO_ENABLED=0 GOOS=linux go build -o main
ENTRYPOINT [ "./main" ]


#Below is the mutli-stage dockerfile we initially used


# build stage
#FROM golang:1.16 as builder

#WORKDIR /app

#COPY . /app

#RUN go mod download && go mod verify &&\
#    cd /app && go build -ldflags "-linkmode 'external' -extldflags '-static'" frontend

# final stage
#FROM alpine

#WORKDIR /app

#COPY --from=builder /app/frontend /app/

#CMD ["./frontend"]