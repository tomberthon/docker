FROM tomberthon/go-1-4-arm

RUN pacman -S git --noconfirm

RUN mkdir -p /go/src/github.com/docker
RUN git clone https://github.com/docker/swarm.git /go/src/github.com/docker/swarm/

WORKDIR /go/src/github.com/docker/swarm

ENV GOPATH /go/src/github.com/docker/swarm/Godeps/_workspace:/go:$GOPATH
RUN CGO_ENABLED=0 go install -v -a -tags netgo -ldflags "-w -X github.com/docker/swarm/version.GITCOMMIT `git rev-parse --short HEAD`"

ENV SWARM_HOST :2375
EXPOSE 2375

ENTRYPOINT ["swarm"]
CMD ["--help"]
