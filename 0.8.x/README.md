## Install from Binary

Separate server and agent binaries and images for [0.8.x](http://docs.drone.io/release-0.8.0)

```sh
#
# install dependencies
#

go get -u github.com/drone/drone-ui/dist
go get -u golang.org/x/net/context
go get -u golang.org/x/net/context/ctxhttp
go get -u github.com/golang/protobuf/proto
go get -u github.com/golang/protobuf/protoc-gen-go

#
# install binaries to $GOPATH/bin
#

go install github.com/drone/drone/cmd/drone-agent
go install github.com/drone/drone/cmd/drone-server
```

## Install from Docker

Please make sure that you are already install [docker-compose](https://docs.docker.com/compose/install/) tool.

```yml
version: '2'

services:
  drone-server:
    image: drone/drone:0.8
    ports:
      - 80:8000
      - 9000:9000
    volumes:
      - /var/lib/drone:/var/lib/drone/
    restart: always
    environment:
      - DRONE_HOST=http://drone.example.com
      - DRONE_OPEN=true
      - DRONE_GITHUB=true
      - DRONE_GITHUB_CLIENT=${DRONE_GITHUB_CLIENT}
      - DRONE_GITHUB_SECRET=${DRONE_GITHUB_SECRET}
      - DRONE_SECRET=${DRONE_SECRET}

  drone-agent:
    image: drone/agent:0.8
    restart: always
    depends_on:
      - drone-server
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
    environment:
      - DRONE_SERVER=drone-server:9000
      - DRONE_SECRET=${DRONE_SECRET}
```

## Drone Installation

* [Installation with GitHub][1]
* [Installation with GitLab][2]
* [Installation with BitBucket][3]
* [Drone on Kubernetes on AWS][4]

[1]:./installation/install-with-github.md
[2]:./installation/install-with-gitlab.md
[3]:./installation/install-with-bitbucket.md
[4]:https://github.com/appleboy/drone-on-kubernetes/tree/master/aws
