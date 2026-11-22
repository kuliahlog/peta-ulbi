# Preview Peta Kampus ULBI

Buka **index.html** dengan klik dua kali di Chrome, Firefox, atau Edge. Tidak perlu npm, build, atau server lokal. Koneksi internet diperlukan untuk memuat jscroot, Leaflet, dan peta dasar OpenStreetMap.

Tampilan sederhana berupa peta dengan sidebar berisi nama kampus, jumlah poligon/garis, dan tombol untuk melihat seluruh peta. Tersedia zoom/geser dan popup properti asli saat objek diklik. Peta otomatis mencakup seluruh kampus.

## Data

Sumber: `untitled (1).geojson`, berisi 50 objek (38 Polygon dan 12 LineString). Nama tampilan diambil dari kunci properti pertama, misalnya `gedung-vokasi`. Objek tanpa properti menggunakan tipe geometri sebagai judul popup. Label geometri tidak menyimpulkan fungsi objek.

Data GeoJSON ditanam sebagai JSON di elemen `campus-data` dalam HTML agar pembukaan melalui `file://` tidak membutuhkan fetch file lokal. File GeoJSON asli tidak diubah. Jika sumber diperbarui, ganti isi elemen tersebut dengan GeoJSON terbaru.

## Pustaka

- [jscroot/lib](https://github.com/jscroot/lib), versi 0.2.8: import ES module dari jsDelivr; fungsi `container`, `setInnerText`, dan `onClick` mengelola elemen, teks, serta tombol sidebar.
- [Leaflet](https://leafletjs.com/), versi 1.9.4: geometri GeoJSON, navigasi peta, dan popup.
- [OpenStreetMap](https://www.openstreetmap.org/copyright): peta dasar dengan atribusi pada peta.

Jika CDN tidak dapat diakses, halaman menampilkan pesan kesalahan. Jika hanya tile peta dasar yang gagal dimuat, geometri kampus tetap dapat digunakan setelah pustaka berhasil dimuat.
