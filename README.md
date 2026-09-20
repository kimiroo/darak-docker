## Docker Cheat Sheet

### Setup `.env`
The ACME account email is not committed. On each node, copy the example next
to the root `docker-compose.yaml` and fill it in (`.env` is gitignored):
```bash
cp .env.example .env
```

### Reload Caddy
```bash
docker compose exec -w /etc/caddy caddy-proxy caddy reload
```