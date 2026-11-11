# Catatan Hari 2

## Batas wilayah
- Ada 2 batas bernama "Kintamani" di OSM:
  - Relation 20447233, admin_level=6 (Kecamatan Kintamani)
  - Relation 20447879, admin_level=7 (Desa Kintamani)
- Query memakai admin_level=6 karena itu batas kecamatan.
- Hasil query: 31 node, 1 way, 0 relation (total 32 elemen).
- Satu titik berada di barat (dekat Catur), masih di dalam batas kecamatan.
  Akan diperiksa lagi di hari 4.

## Jenis akomodasi yang dimasukkan
hotel, guest_house, hostel, motel, apartment, chalet

Alasan:
- Keenamnya adalah tag OSM yang lazim untuk penginapan berbayar.
- Villa di OSM tidak punya tag sendiri, sehingga ditangkap lewat
  guest_house, chalet, atau apartment.

## Jenis yang tidak dimasukkan
camp_site dan caravan_site: bukan akomodasi berbasis bangunan.

## Keterbatasan
- Villa yang tidak memakai tag di atas tidak akan terambil.
- Hasil bergantung pada kelengkapan data relawan OSM.

## Kendala
(isi bila ada)
