FROM amazonlinux:latest

ENV GOPATH=/opt/imageproxy

RUN yum update -y
RUN yum install golang -y

RUN curl http://curl.haxx.se/ca/cacert.pem -o /etc/pki/tls/certs/ca-bundle.crt 
RUN update-ca-trust force-enable


RUN mkdir -p /opt/imageproxy
RUN cd $GOPATH 
RUN go get willnorris.com/go/imageproxy/cmd/imageproxy

EXPOSE 8080

CMD /opt/imageproxy/bin/imageproxy -cache /tmp/imageproxy -addr 0.0.0.0:8080
