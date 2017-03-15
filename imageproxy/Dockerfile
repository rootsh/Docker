FROM amazonlinux:latest

ENV GOPATH=/opt/imageproxy

RUN yum update -y; yum clean all
RUN yum install golang -y; yum clean all

RUN curl http://curl.haxx.se/ca/cacert.pem -o /etc/pki/tls/certs/ca-bundle.crt; update-ca-trust force-enable

RUN mkdir -p $GOPATH && \
    cd $GOPATH && \
    go get willnorris.com/go/imageproxy/cmd/imageproxy

CMD /opt/imageproxy/bin/imageproxy -cache /tmp/imageproxy -addr 0.0.0.0:8080

EXPOSE 8080
