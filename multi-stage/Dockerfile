FROM golang:1.13 as multistage
WORKDIR /tmp
COPY helloworld.go .
RUN GOOS=linux go build -a -installsuffix cgo -o helloworld .
CMD ["./helloworld"]

FROM alpine:3
WORKDIR /root
COPY --from=multistage /tmp/helloworld .
CMD ["./helloworld"]
