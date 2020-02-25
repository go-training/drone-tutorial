# drone-tutorial

Drone Continuous Delivery Documentation

## Install Drone with GitHub

```yaml
version: '2'

services:
  drone-server:
    image: drone/drone:1
    ports:
      - 8081:80
    volumes:
      - ./:/data
    restart: always
    environment:
      - DRONE_SERVER_HOST=${DRONE_SERVER_HOST}
      - DRONE_SERVER_PROTO=${DRONE_SERVER_PROTO}
      - DRONE_RPC_SECRET=${DRONE_RPC_SECRET}

      # GitHub Config
      - DRONE_GITHUB_SERVER=https://github.com
      - DRONE_GITHUB_CLIENT_ID=${DRONE_GITHUB_CLIENT_ID}
      - DRONE_GITHUB_CLIENT_SECRET=${DRONE_GITHUB_CLIENT_SECRET}

      - DRONE_LOGS_PRETTY=true
      - DRONE_LOGS_COLOR=true

  # runner for docker version
  drone-runner:
    image: drone/drone-runner-docker:1
    restart: always
    depends_on:
      - drone-server
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
    environment:
      - DRONE_RPC_HOST=${DRONE_RPC_HOST}
      - DRONE_RPC_PROTO=${DRONE_RPC_PROTO}
      - DRONE_RPC_SECRET=${DRONE_RPC_SECRET}
      - DRONE_RUNNER_CAPACITY=3
```

## Install Drone with GitLab

```yaml
version: '2'

services:
  drone-server:
    image: drone/drone:1
    ports:
      - 8081:80
    volumes:
      - ./:/data
    restart: always
    environment:
      - DRONE_SERVER_HOST=${DRONE_SERVER_HOST}
      - DRONE_SERVER_PROTO=${DRONE_SERVER_PROTO}
      - DRONE_RPC_SECRET=${DRONE_RPC_SECRET}
      # Gitlab Config
      - DRONE_GITLAB_SERVER=https://gitlab.com
      - DRONE_GITLAB_CLIENT_ID=${DRONE_GITLAB_CLIENT_ID}
      - DRONE_GITLAB_CLIENT_SECRET=${DRONE_GITLAB_CLIENT_SECRET}
      - DRONE_LOGS_PRETTY=true
      - DRONE_LOGS_COLOR=true

  # runner for docker version
  drone-runner:
    image: drone/drone-runner-docker:1
    restart: always
    depends_on:
      - drone-server
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
    environment:
      - DRONE_RPC_HOST=${DRONE_RPC_HOST}
      - DRONE_RPC_PROTO=${DRONE_RPC_PROTO}
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
