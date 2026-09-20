## Required secret files
Make sure `SECRETS_DIR` in `.env` points to the directory containing these files.

### file-node-01
- cf_api_token
- gts_eab_key_id
- gts_eab_hmac_key
- watchtower_notification_url

### rocky-docker-01
- cf_api_token
- gts_eab_key_id
- gts_eab_hmac_key
- watchtower_notification_url

## Set up nodes

### Set up `.env`
Set `ACME_EMAIL` and, optionally, `SECRETS_DIR`.
```bash
cp .env.example .env
```

### Network
`caddy-bridge` is pinned to `172.31.0.0/24` (gateway `172.31.0.1`) for firewall rules. Keep the root `docker-compose.yaml` and `caddy/docker-compose.yaml` (`extra_hosts`) in sync.

## Docker Cheat Sheet

### Reload Caddy
```bash
sudo docker compose exec -w /etc/caddy caddy caddy reload
# or
docker exec -w /etc/caddy caddy caddy reload
```
