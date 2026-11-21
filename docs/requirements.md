# Requirements

## Problem Statement
Individu yang menjalankan aktivitas affiliate di beberapa platform dan bekerja sama dengan beberapa brand mengelola brief, ide dan naskah konten, jadwal publikasi, kewajiban kerja sama, dan fee secara terpisah. Ini hipotesis awal yang masih perlu divalidasi lewat wawancara pelaku affiliate.

## Target Users
Individu affiliate multi-platform yang bekerja sama dengan beberapa brand.

## Functional Requirements
- FR-01 (Must): pengguna dapat mendaftar, login, lalu mengelola kerja sama brand, pelacakan konten, serta pencatatan fee dan status pembayaran, dan melihat ringkasannya di dashboard. Uji: AT-01.
- FR-02 (Must): data akun, kerja sama, konten, dan fee tersimpan di database dan tetap ada setelah layanan di-restart. Uji: AT-02.
- FR-03 (Must): sistem menyediakan GET /health yang mengembalikan HTTP 200 saat layanan sehat. Uji: AT-03.
- FR-04 (Should): pengguna hanya dapat membaca, memperbarui, dan menghapus data miliknya sendiri. Uji: AT-04.
- FR-05 (Should): kesalahan input atau gangguan menampilkan pesan yang aman tanpa membocorkan detail internal. Uji: AT-05.

## Non-Functional Requirements
- NFR-01 Security: secret tidak tersimpan di Git, SSH memakai key, backend loopback-only.
- NFR-02 Privacy: data uji berupa data dummy atau data pengguna uji dengan persetujuan.
- NFR-03 Reliability: service restart otomatis (systemd); backup dan restore terbukti (M05, M12).
- NFR-04 Performance: waktu respons halaman < 2 detik (p95) pada 5 pengguna bersamaan.
- NFR-05 Capacity: CPU, RAM, dan disk dalam batas yang ditetapkan.
- NFR-06 Compatibility: fungsi kritis dapat diakses dari Windows, Linux, iOS, dan Android.
- NFR-07 Maintainability: README, ADR, runbook, dan riwayat commit jelas.
- NFR-09 Auditability: evidence tiap milestone tercatat di GitHub.
- NFR-10 Cost: tidak melebihi anggaran Rp 125.000 per bulan.

## Constraints
- batas desain praktikum: 1 vCPU, 1 GB RAM, 20 GB disk
- VM aktual: 2 vCPU, 1,9 GiB RAM, 19 GB disk
- Ubuntu Server 24.04.5 LTS
- public IPv4

## Acceptance Criteria M03
- [x] first deployment accessible (http://103.171.85.139/)
- [x] health endpoint works (GET /health menjawab HTTP 200)
- [x] backend loopback-only (127.0.0.1:8000)
- [x] SSH key-only, root login dinonaktifkan
- [x] UFW aktif (port 22 dan 80)
- [ ] evidence M03 dari VM baru tersimpan di docs/evidence/m03/
