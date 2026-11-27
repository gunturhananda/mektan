# Perhitungan Anggota Kelompok 7 — Praktikum Mekanika Tanah UNJA

Aplikasi web statis untuk perhitungan otomatis **Praktikum Mekanika Tanah Kelompok 7** (Teknik Sipil, Universitas Jambi) yang disusun 1:1 mengikuti format laporan resmi Kelompok 7.

🌐 **Live Web:** https://gunturhananda.github.io/mektan/

## Fitur Utama

- **Input NIM Dinamis (`Δ NIM`)**
  - Menghitung penambahan nilai `Δ NIM` otomatis dari nomor NIM (mis. `62` / `F1G225062` → `+0,62`, `100` → `+0,10`, atau input desimal langsung seperti `0,62`).
  - Tombol **NIM = 0 (Verifikasi)** untuk menampilkan nilai dasar 1:1 laporan Kelompok 7.
  - Opsi **CBR: +Δ NIM ke Beban (kN)** untuk mengaktifkan/menonaktifkan penambahan `Δ NIM` pada beban penetrasi CBR.
- **Langkah Perhitungan 1:1 & Form Laboratorium**
  - Menampilkan langkah perhitungan terstruktur sesuai urutan laporan Kelompok 7 lengkap dengan tombol **Salin Langkah 1:1**.
  - Menampilkan form laboratorium UNJA dengan penandaan sel biru untuk nilai input yang mendapat penambahan `Δ NIM`.
- **Grafik Pengujian Interaktif**
  - Visualisasi grafik di browser menggunakan **Chart.js** untuk pengujian Sondir, Atterberg, Analisis Saringan, Hidrometer, Pemadatan, CBR, Konsolidasi, UCS, dan Direct Shear.
- **Export Excel (`.xlsx`) & Cetak PDF**
  - Export per tab (**Export Form Ini**) maupun keseluruhan workbook (**Export Excel + Grafik (.xlsx)**) langsung dari browser menggunakan **JSZip** dan template `.xlsx` resmi berlogo UNJA yang tertanam (`19` sheet form + `9` sheet grafik native Excel = `28` sheet).
  - Tombol **Cetak / PDF** dengan styling cetak (`@media print`).

## Daftar Modul Pengujian (14 Tab)

1. `2.1.5 Sondir (CPT)` (`+Δ PK,JP` — 55 titik data kedalaman `0,00–10,80 m`)
2. `2.4.5 Sand Cone` (`Tetap`)
3. `Kadar Air` (`+Δ W1,W2` — Tanah Tak Terganggu & Tanah Terganggu)
4. `Berat Spesifik (Gs)` (`+Δ W2,W3` — Piknometer A & B)
5. `Atterberg (LL & PL)` (`+Δ W1,W2`)
6. `Analisis Saringan` (`+Δ Tertahan`)
7. `Hidrometer (k=-0,5)` (`+Δ W,Rh`)
8. `3.5.5 Pemadatan` (`+Δ Cawan`)
9. `3.6.5 CBR (3 Cetakan)` (`+Δ CBR` — 3x10, 3x30, 3x65 tumbukan)
10. `3.7.5 Konsolidasi` (`+Δ Arloji`)
11. `3.8.5 Kuat Tekan (UCS)` (`+Δ Dial`)
12. `3.9.5 Kuat Geser` (`+Δ Dial`)
13. `3.11.5 Permeabilitas` (`+Δ Vol`)
14. `Ringkasan & Verifikasi` (`AUDIT` — perbandingan hasil `NIM = 0` vs NIM aktif)

## Teknologi & Dependensi

- Single-file web app (`index.html`, murni HTML/CSS/JavaScript di sisi klien tanpa backend)
- [Tailwind CSS CDN](https://cdn.tailwindcss.com/) (`3.4.17`)
- [Chart.js](https://www.chartjs.org/) (`4.4.1`)
- [JSZip](https://stuk.github.io/jszip/) (`3.10.1`)
- Font `Inter` & `JetBrains Mono` (Google Fonts)

## Struktur Repositori

- `index.html` — Seluruh antarmuka, logika perhitungan 13 pengujian, grafik Chart.js, dan template `.xlsx` base64 tertanam
- `.nojekyll` — File penanda agar GitHub Pages langsung menyajikan file statis tanpa proses build Jekyll
- `README.md` — Dokumentasi proyek

> **Catatan Kontribusi:** Karena `index.html` memuat baris template base64 berukuran besar (~850 KB dalam satu baris), hindari mengeditnya langsung melalui editor web GitHub agar tidak terpotong; lakukan perubahan dan push melalui `git` secara lokal.
