# Akuisisi Data Akomodasi di Kecamatan Kintamani

Tugas praktik BIFP-243 Akuisisi dan Manajemen Data (INSTIKI).

- Nama: Si Ngurah Rai Krisna Pranajaya
- NIM: 2501010375

## Tujuan
Mengakuisisi data akomodasi (hotel, guest house, hostel, motel, chalet, apartment) di
Kecamatan Kintamani dari OpenStreetMap secara etis, menyimpan respons mentah, membentuk
dataset tabular terdokumentasi, dan menilai kelengkapannya terhadap data resmi BPS.

## Sumber data
- OpenStreetMap melalui Overpass API (https://overpass-api.de/api/interpreter)
- BPS Kabupaten Bangli sebagai pembanding: BPS Kabupaten Bangli, Kecamatan Kintamani Dalam Angka 2024, Tabel 6.1.1 (https://banglikab.bps.go.id/id/publication/2024/09/26/3313f5ac27a3df4ff0ecbd03/kecamatan-kintamani-dalam-angka-2024.html)

## Tanggal akses
11 November 2026 (UTC 08:51:08). Rincian di `docs/provenance.json`.

## Metode akuisisi
1. Batas wilayah: relation OSM 20447233 (`admin_level=6`, Kecamatan Kintamani). Relation
   20447879 (`admin_level=7`) adalah Desa Kintamani dan tidak dipakai.
2. Query dijalankan satu kali dari Python dengan retry, jeda bertahap, timeout 120 detik,
   dan User-Agent berisi identitas pengambil. Query final: `docs/query_overpass.txt`.
3. Respons mentah disimpan tanpa diubah di `data/raw/`.
4. Respons diratakan menjadi `data/interim/akomodasi_kintamani.csv` (32 baris, 11 kolom).
5. Pemeriksaan kualitas dan keputusan dicatat di `docs/catatan_hari4.md`.

## Ringkasan hasil
| Jenis | Jumlah |
|---|---|
| hotel | 16 |
| guest_house | 9 |
| hostel | 4 |
| chalet | 2 |
| motel | 1 |

Jumlah OSM: 32. Jumlah BPS: 118 (tahun 2023).
Kelengkapan: 27.1.

## Batasan etika
- Hanya sumber yang diizinkan; tidak ada scraping OTA atau Google Maps.
- Telepon, email, dan media sosial tidak diambil dan tidak dicantumkan.
- Berkas di `data/raw/` tidak diubah setelah disimpan.
- Tidak ada baris yang dihapus tanpa dicatat.
- Data OSM diisi relawan sehingga tidak lengkap; hasil tidak boleh dianggap data resmi.

## Atribusi dan lisensi
© OpenStreetMap contributors. Data tersedia di bawah lisensi ODbL
(https://opendatacommons.org/licenses/odbl/).

## Struktur repository
