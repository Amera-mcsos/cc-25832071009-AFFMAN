# ADR-0003: SQLite, backup, dan tanpa unggah berkas

**Status:** Rencana (M05)

**Tanggal:** 09-11-2026

## Konteks
Beban pilot kecil (sekitar 5 pengguna) dengan data berupa teks
dan tautan.

## Keputusan
- SQLite sebagai penyimpanan data
- Backup berkala ke lokasi eksternal dan uji restore, retensi 3 versi terakhir
- Bukti konten disimpan sebagai tautan, tanpa unggah berkas

## Alasan
- SQLite cukup untuk beban pilot dan ringan untuk VPS
- Database terkelola (A3) lebih mahal dan tidak diperlukan untuk skala ini
- Tanpa unggah berkas, kapasitas disk dan permukaan serangan lebih terkendali

## Konsekuensi
- Bukti hilang bila tautan asli dihapus pemiliknya
- SQLite kurang cocok untuk beban tulis yang tinggi; dievaluasi bila pengguna bertambah
