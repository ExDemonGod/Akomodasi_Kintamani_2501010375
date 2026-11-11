# Catatan Hari 4: Pemeriksaan Kualitas Data

## Ringkasan
- Jumlah baris: 32 (dari 32 elemen mentah: 31 node, 1 way)
- Berkas sumber: data/raw/osm_akomodasi_kintamani_20261111_085108.json
- Jumlah per jenis: hotel 16, guest_house 9, hostel 4, chalet 2, motel 1, apartment 0

## Hasil pemeriksaan
- Duplikat (osm_type + osm_id): 0
- Akomodasi tanpa nama: 1 dari 32 (96,9% terisi)
- Koordinat kosong: 0
- Rentang koordinat: lat -8,2838 s.d. -8,2189; lon 115,2546 s.d. 115,4129
- Koordinat di luar kotak kasar (lat -8,40 s.d. -8,10; lon 115,20 s.d. 115,50): 0
- Persen terisi per kolom:
  - desa: 0% (kosong seluruhnya)
  - bintang: 3,1% (sekitar 1 dari 32)
  - jumlah_kamar: 6,2% (sekitar 2 dari 32)
  - website: 6,2% (sekitar 2 dari 32)
  - kolom lain (osm_type, osm_id, jenis, lat, lon, url_osm): 100%

## Keputusan
- Tidak ada baris yang dihapus.
- Akomodasi tanpa nama tetap dipertahankan dan jumlahnya dicatat (1).
- Kolom desa tetap disimpan walaupun kosong, karena termasuk struktur dataset
  yang diwajibkan. Ringkasan per desa tidak dapat disusun dari tag addr:village.
- bintang dan jumlah_kamar dibiarkan bertipe teks (cleaning di Pertemuan 8-9).
- Telepon, email, media sosial tidak diambil (minimisasi data).

## Temuan khusus
- Seluruh data tidak memiliki tag addr:village.
- Atribut opsional (bintang, jumlah_kamar, website) hampir selalu kosong.
- Tag apartment termasuk dalam query tetapi tidak menghasilkan data.
- Satu-satunya elemen bertipe way (way/1181397894) adalah motel tanpa nama,
  di lat -8,223372 lon 115,254582 (titik paling barat, dekat Catur).
  Hasil verifikasi di OSM: Di sisi utara Jalan Raya Pelaga, tepat di samping SPBU Pertamina
