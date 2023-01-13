# docker-compose-rustdesk
docker-compose runtime environment for [RustDesk self-host server](https://rustdesk.com/docs/en/self-host/install/#docker-example).

## Usage

1. Install `docker` and `docker-compose` if you haven' t.

2. Clone this repository.

3. Copy the `.env.example` to `.env`. Update the IP part with your RustDesk server's IP.

4. Run `docker-compose up -d` to start the server.

```
shell> git clone https://github.com/jichangfeng/docker-compose-rustdesk.git
shell> cd docker-compose-rustdesk
shell> cp .env.example .env
# Update the IP part with your RustDesk server's IP.
shell> docker-compose up -d
```

5. By default, `hbbs` listens on 21115 (TCP) and 21116 (TCP/UDP), 21118 (TCP), and `hbbr` listens on 21117 (TCP), 21119 (TCP). Be sure to open these ports in the firewall. **Please note that 21116 should be enabled both for TCP and UDP.** 21115 is used for the NAT type test, 21116/UDP is used for the ID registration and heartbeat service, 21116/TCP is used for TCP hole punching and connection service, 21117 is used for the Relay services, and 21118 and 21119 are used to support web clients. If you do not need web client (21118, 21119) support, the corresponding ports can be disabled.
 - TCP (**21115, 21116, 21117, 21118, 21119**)
 - UDP (**21116**)

## Set `ID/Relay Server` on client-side

1. Enter the RustDesk server's IP Address in the `ID Server` input box (local side + remote side).

2. The other two addresses can be left blank, RustDesk will automatically deduce (if not specially set), and the relay server refers to hbbr (21116 port).
