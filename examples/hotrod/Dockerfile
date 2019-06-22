FROM golang:alpine
EXPOSE 8080 8081 8082 8083
RUN apk add --update git
RUN go get -u github.com/golang/dep/cmd/dep
COPY . /go/src/github.com/jaegertracing/jaeger
RUN (cd /go/src/github.com/jaegertracing/jaeger && dep ensure)
RUN go install github.com/jaegertracing/jaeger/examples/hotrod
ENTRYPOINT ["/go/bin/hotrod"]
CMD ["all"]
