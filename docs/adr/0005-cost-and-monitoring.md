# ADR-0005: Pemantauan dan biaya; IaC dan pipeline direncanakan

**Status:** Sebagian berjalan (pemantauan manual); IaC dan pipeline rencana M07–M13

**Tanggal:** 09-11-2026

## Konteks
Sumber daya VPS terbatas dan biaya harus dijaga selama proyek.

## Keputusan
- Pemantauan RAM, CPU, dan disk secara manual dengan free -m,
  uptime, dan df -h
- Biaya dipantau lewat invoice dan saldo IDCloudHost
- IaC, pipeline, dan observability lanjutan dikerjakan pada M07–M13

## Alasan
- Pemantauan manual cukup untuk skala pilot dan tanpa biaya tambahan
- Alat lanjutan baru dipilih setelah kebutuhan terukur

## Konsekuensi
- Tidak ada peringatan otomatis sebelum pipeline dan observability jadi
- Pengecekan saldo dan sumber daya bergantung pada kedisiplinan manual
