FROM tomberthon/archlinux

ADD go1.4.linux-arm~armv7-1.tar.gz /usr/local

ENV PATH=$PATH:/usr/local/go/bin:/go/bin
ENV GOPATH=/go:$GOPATH

ADD hello.go /root/
