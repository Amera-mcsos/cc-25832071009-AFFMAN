# ADR-0002: Caddy, UFW, dan HTTPS

**Status:** Sebagian berjalan (HTTP aktif); HTTPS direncanakan M04

**Tanggal:** 09-11-2026

## Konteks
Aplikasi perlu dapat diakses pengguna lewat internet, sementara VPS
harus dilindungi dari akses yang tidak perlu.

## Keputusan
- Caddy sebagai reverse proxy di depan aplikasi
- UFW membuka port 22 (SSH) dan 80; port 443 ditambahkan saat HTTPS aktif
- Gunicorn hanya mendengarkan di 127.0.0.1:8000, tidak terbuka ke internet
- HTTPS otomatis lewat Caddy setelah domain tersedia (rencana M04)

## Alasan
- Aplikasi tidak terekspos langsung ke internet
- Caddy mengelola sertifikat TLS secara otomatis
- Port yang terbuka dibatasi seminimal mungkin

## Konsekuensi
- HTTPS yang valid menunggu domain dari dosen
- Selama belum ada HTTPS, data hanya boleh berupa data uji
