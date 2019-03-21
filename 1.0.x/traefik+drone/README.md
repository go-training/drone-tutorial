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

## Setup the single server of Drone

1. copy `drone` folder to `/home/`

```sh
$ cp -r traefik /home/
```

2. update the drone setting in `.env`

```
DRONE_SERVER_HOST=example.com
DRONE_SERVER_PROTO=http
DRONE_GITHUB_CLIENT_ID=xxxx
DRONE_GITHUB_CLIENT_SECRET=xxxx
```

3 start the drone service.

```sh
$ cd /home/drone/ && docker-compose up -d
```

4. open the drone link in your browser
