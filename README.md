# MFHome

MFHome is the primary webpage linking to the other Mines Formula websites so the team does not have to memorize port numbers.

## Running with Docker

For normal local development, use the canonical Compose file:

```bash
docker compose up -d --build
```

On the `fsaelinux` server, run the base Compose file plus the server override:

```bash
docker compose \
  -f docker-compose.yml \
  -f docker-compose.server.yml \
  up -d
```

The server override keeps the service on host networking and clears the inherited `ports` mapping so the site is available directly on host port `80`. Keep server-only networking changes in `docker-compose.server.yml`; do not duplicate the full Compose service definition.
