# Traefik + Drone CI/CD Server

## Setup the traefik service

1. copy the `traefik` folder to `/opt/`

```sh
$ cp -r traefik /opt/
```

2. change the permission of `acme.json` to `600`

```sh
$ chmod 600 /opt/traefik/acme.json
```

3. Start the traefik service using Docker

```sh
$ cd /opt/traefik/ && docker-compose up -d
```
