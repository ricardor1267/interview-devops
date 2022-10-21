FROM golang:1.12.14 AS builder



RUN apt-get update
ENV GO111MODULE=on \
    CGO_ENABLED=1 \
    GOOS=linux \
    GOARCH=amd64

    
WORKDIR /usr/src/app
COPY go.mod .
RUN go mod download
COPY . .
RUN go install 
CMD ["./main"]
# pre-copy/cache go.mod for pre-downloading dependencies and only redownloading them in subsequent builds if they change
#COPY go.mod go.sum ./
#RUN go mod download && go mod verify

#COPY . .

