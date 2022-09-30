# docker-compose-rustdesk
docker-compose runtime environment for [RustDesk self-host server](https://rustdesk.com/docs/en/self-host/install/#docker-example).

## Usage

1. Install `docker` and `docker-compose` if you haven' t.

2. Clone this repository.

3. Copy the `.env.example` to `.env`. Update the IP part with your RustDesk server's IP.

4. Run `docker compose up -d` to start the server.

```
shell> git clone https://github.com/jichangfeng/docker-compose-rustdesk.git
shell> cd docker-compose-rustdesk
shell> cp .env.example .env
# Update the IP part with your RustDesk server's IP.
shell> docker-compose up -d
```

## Set `ID/Relay Server` on client-side

1. Enter the RustDesk server's IP Address in the `ID Server` input box (local side + remote side).

2. The other two addresses can be left blank, RustDesk will automatically deduce (if not specially set), and the relay server refers to hbbr (21116 port).
