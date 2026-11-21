# Manual Deployment M03

## Application Path
`/srv/cc-m03`

## Service
`cc-m03.service` (systemd, menjalankan Gunicorn)

## Backend
`127.0.0.1:8000`

## Reverse Proxy
Caddy pada port 80, konfigurasi di `/etc/caddy/Caddyfile`:

```text
:80 {
    encode zstd gzip
    reverse_proxy 127.0.0.1:8000
}
```

## Public Endpoint
`http://103.171.85.139/`

## Access
- SSH dengan key sebagai user `irtup` (password dan login root dinonaktifkan)
- akses ke GitHub dari VPS memakai deploy key dengan alias SSH `github-m03`

## Update Procedure

```bash
cd /srv/cc-m03
git pull
source .venv/bin/activate
python -m pip install -r requirements.txt
sudo systemctl restart cc-m03
sudo systemctl status cc-m03 --no-pager
curl -fsS http://127.0.0.1:8000/health
curl -fsS http://127.0.0.1/health
```

Terakhir, uji dari klien eksternal: `http://103.171.85.139/health`.

## Verification
- `sudo systemctl is-active cc-m03 caddy` harus `active`
- `sudo ss -ltnp` harus menunjukkan Caddy di 0.0.0.0:80 dan Gunicorn di 127.0.0.1:8000
- `sudo ufw status verbose` hanya mengizinkan 22/tcp dan 80/tcp

## Logs
- aplikasi: `sudo journalctl -u cc-m03 -n 50 --no-pager`
- Caddy: `sudo journalctl -u caddy -n 50 --no-pager`

## Troubleshooting Order
1. aplikasi: `curl http://127.0.0.1:8000/health`
2. Caddy: `sudo caddy validate --config /etc/caddy/Caddyfile`
3. port: `sudo ss -ltnp`
4. firewall: `sudo ufw status verbose` dan firewall di panel provider
