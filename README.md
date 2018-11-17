# drone-tutorial

Drone Continuous Delivery Documentation

## Run drone in Single Machine

The goal of this document is to give you enough technical specifics to configure and run the Drone server in single-machine mode. The Drone server will use an embedded sqlite database and will execute pipelines on the same machine as the server.

```yml
version: '2'

services:
  drone-server:
    image: drone/drone:1.0.0-rc.1
    ports:
      - 8081:80
    volumes:
      - ./:/data
      - /var/run/docker.sock:/var/run/docker.sock
    restart: always
    environment:
      - DRONE_SERVER_HOST=${DRONE_SERVER_HOST}
      - DRONE_SERVER_PROTO=${DRONE_SERVER_PROTO}
      - DRONE_TLS_AUTOCERT=false
      - DRONE_RPC_SECRET=${DRONE_RPC_SECRET}
      - DRONE_RUNNER_CAPACITY=3
      # GitHub Config
      - DRONE_GITHUB_SERVER=https://github.com
      - DRONE_GITHUB_CLIENT_ID=${DRONE_GITHUB_CLIENT_ID}
      - DRONE_GITHUB_CLIENT_SECRET=${DRONE_GITHUB_CLIENT_SECRET}
```

## Run drone in Multi-Machine

The goal of this document is to give you enough technical specifics to configure and run the Drone in multi-machine mode. Once you complete this guide you will need to install one or many agents.

```yml
version: '2'

services:
  drone-server:
    image: drone/drone:1.0.0-rc.1
    ports:
      - 8081:80
    volumes:
      - ./:/data
    restart: always
    environment:
      - DRONE_SERVER_HOST=${DRONE_SERVER_HOST}
      - DRONE_SERVER_PROTO=${DRONE_SERVER_PROTO}
      - DRONE_TLS_AUTOCERT=false
      - DRONE_RPC_SECRET=${DRONE_RPC_SECRET}
      # GitHub Config
      - DRONE_GITHUB_SERVER=https://github.com
      - DRONE_GITHUB_CLIENT_ID=${DRONE_GITHUB_CLIENT_ID}
      - DRONE_GITHUB_CLIENT_SECRET=${DRONE_GITHUB_CLIENT_SECRET}

  drone-agent:
    image: drone/agent:1.0.0-rc.1
    restart: always
    depends_on:
      - drone-server
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
    environment:
      - DRONE_RPC_SERVER=http://drone-server
      - DRONE_RPC_SECRET=${DRONE_RPC_SECRET}
      - DRONE_RUNNER_CAPACITY=3
```

## Git Service Configutation

* [Configutation with GitHub][1]
* [Configutation with GitLab][2]
* [Configutation with BitBucket][3]
* [Drone on Kubernetes on AWS][4]

[1]:./installation/install-with-github.md
[2]:./installation/install-with-gitlab.md
[3]:./installation/install-with-bitbucket.md
[4]:https://github.com/appleboy/drone-on-kubernetes/tree/master/aws
