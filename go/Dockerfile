FROM golang:1.17-alpine AS builder

WORKDIR /go/src/app

COPY . .

RUN go mod init
RUN go build -o /go/bin/hello-fullcycle

FROM scratch
COPY --from=builder /go/bin/hello-fullcycle /go/bin/hello-fullcycle
ENTRYPOINT [ "/go/bin/hello-fullcycle" ]
