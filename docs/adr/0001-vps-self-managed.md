# ADR-0001: Single VPS self-managed (IDCloudHost)

**Status:** Diterima

**Tanggal:** 09-11-2026

## Konteks
Website manajemen affiliate multi-platform perlu dijalankan di cloud
dengan biaya rendah, dan data pengguna dikendalikan sendiri.

## Keputusan
Memakai satu VPS Ubuntu 24.04 self-managed dari IDCloudHost
(alternatif A2), bukan managed platform (A3).

## Alasan
- Skor tertinggi pada analisis alternatif (Bagian 6.1 studi kelayakan)
- Biaya bulanan lebih rendah dibanding managed platform
- Kendali penuh atas server dan data
- Sesuai tujuan mata kuliah Cloud Computing

## Konsekuensi
- Keamanan, backup, dan pemantauan dikelola sendiri
- Satu VPS menjadi single point of failure
- Kapasitas terbatas pada spesifikasi VPS yang disewa
