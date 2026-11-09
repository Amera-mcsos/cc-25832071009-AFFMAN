# ADR-0004: Container, network & image policy (saat ini systemd + Gunicorn)

**Status:** Diterima untuk M03–M05; containerization dievaluasi pada M06

**Tanggal:** 09-11-2026

## Konteks
Aplikasi perlu berjalan persisten di VPS dan otomatis hidup kembali
setelah restart atau crash.

## Keputusan
- Aplikasi dijalankan sebagai service systemd (cc-m03) dengan Gunicorn
- Gunicorn hanya mendengarkan di 127.0.0.1:8000, diakses lewat Caddy
- Containerization dan kebijakan image/jaringan dievaluasi pada M06

## Alasan
- systemd menjaga proses tetap berjalan dan otomatis restart
- Konfigurasi sederhana dan ringan untuk VPS kecil
- Containerization menunggu materi dan implementasi M06

## Konsekuensi
- Pemasangan ulang di server lain masih manual sampai M06
- Keputusan container (image, jaringan) belum ditetapkan
