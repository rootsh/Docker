FROM alpine

ENV GOPATH=/opt/imageproxy

RUN apk add --no-cache go git libc-dev

RUN mkdir -p $GOPATH; cd $GOPATH; go get willnorris.com/go/imageproxy/cmd/imageproxy

CMD /opt/imageproxy/bin/imageproxy -cache /tmp/imageproxy -addr 0.0.0.0:8080

EXPOSE 8080
