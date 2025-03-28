# Dokumentasi Keluarga Visualizer

## Daftar Isi
1. [Pengenalan](#1-pengenalan)
2. [Antarmuka Aplikasi](#2-antarmuka-aplikasi)
3. [Mengelola Data Keluarga](#3-mengelola-data-keluarga)
4. [Pencarian dan Filter](#4-pencarian-dan-filter)
5. [Ekspor dan Impor Data](#5-ekspor-dan-impor-data)
6. [Pemecahan Masalah](#6-pemecahan-masalah)
7. [Tips dan Trik](#7-tips-dan-trik)

## 1. Pengenalan

Keluarga Visualizer adalah aplikasi web untuk membuat dan mengelola pohon silsilah keluarga. Aplikasi ini dirancang untuk mempermudah pengguna dalam mendokumentasikan hubungan antar anggota keluarga dan memvisualisasikannya dalam bentuk struktur pohon yang intuitif.

### 1.1 Fitur Utama

- Pengelolaan data keluarga (tambah, edit, hapus)
- Visualisasi pohon keluarga
- Pencarian dan filter anggota keluarga
- Ekspor dan impor data
- Penyimpanan otomatis di browser
- Validasi data untuk memastikan struktur pohon yang benar

### 1.2 Tujuan Aplikasi

Aplikasi ini bertujuan untuk:
- Mempermudah dokumentasi silsilah keluarga
- Menyediakan visualisasi yang jelas tentang hubungan keluarga
- Membantu melestarikan sejarah keluarga untuk generasi mendatang

## 2. Antarmuka Aplikasi

Aplikasi terbagi menjadi beberapa bagian utama:

### 2.1 Panel Instruksi

Panel ini memberikan petunjuk singkat tentang cara menggunakan aplikasi. Petunjuk meliputi:
- Cara menambahkan generasi awal
- Cara menambahkan anak
- Informasi tentang ID dan generasi
- Informasi tentang penyimpanan data

### 2.2 Form Data Manager

Form ini digunakan untuk menambah atau mengedit data anggota keluarga dengan field:
- **Nama**: Nama anggota keluarga
- **Generasi**: Level generasi (0-5)
- **Status**: Checkbox untuk menandai almarhum/ah
- **Pasangan**: Nama pasangan dan status
- **Parent ID**: ID orang tua (kosong untuk generasi awal)

Tombol-tombol pada form:
- **Tambah Data**: Menambahkan data baru
- **Generate CompleteData**: Membuat struktur data lengkap
- **Clear Data**: Menghapus semua data
- **Import Data**: Mengimpor data dari file JSON
- **Export Data**: Mengekspor data ke file JSON

### 2.3 Data Tree

Panel ini menampilkan visualisasi pohon keluarga dengan fitur:
- Struktur bertingkat berdasarkan hubungan orang tua-anak
- Indentasi untuk menunjukkan level generasi
- Detail anggota keluarga (nama, status, generasi, pasangan)
- Tombol aksi untuk setiap anggota (tambah anak, edit, hapus)

Di bagian atas terdapat:
- Field pencarian untuk mencari anggota berdasarkan nama
- Dropdown filter untuk menyaring berdasarkan generasi

### 2.4 Generated CompleteData

Panel ini menampilkan struktur data dalam format JavaScript yang bisa digunakan untuk keperluan lain dengan tombol:
- **Copy Code**: Menyalin kode ke clipboard
- **Validate Data**: Memvalidasi struktur data

## 3. Mengelola Data Keluarga

### 3.1 Menambahkan Generasi Awal (0)

1. Kosongkan field "Parent ID"
2. Pilih "0 (Generasi Awal)" pada dropdown Generasi
3. Isi nama anggota keluarga
4. Jika sudah meninggal, centang "Almarhum/ah"
5. Jika memiliki pasangan, isi nama pasangan
6. Jika pasangan sudah meninggal, centang "Pasangan Almarhum/ah"
7. Klik tombol "Tambah Data"

### 3.2 Menambahkan Anak

**Cara 1: Melalui tombol "+ Tambah Anak"**
1. Cari anggota keluarga yang akan ditambahkan anaknya di Data Tree
2. Klik tombol "+ Tambah Anak" (icon plus) di sebelah nama
3. Form akan otomatis diisi dengan Parent ID dan generasi yang sesuai
4. Lengkapi data anak
5. Klik tombol "Tambah Data"

**Cara 2: Melalui form manual**
1. Isi field "Parent ID" dengan ID orang tua
   (ID dapat dilihat di sebelah nama setiap anggota dalam format "[ID: person_X]")
2. Pilih generasi yang sesuai (biasanya satu tingkat di atas orang tua)
3. Lengkapi data lainnya
4. Klik tombol "Tambah Data"

### 3.3 Mengedit Data

1. Cari anggota keluarga yang ingin diedit di Data Tree
2. Klik tombol "Edit" (icon pensil)
3. Form akan otomatis diisi dengan data anggota tersebut
4. Ubah data yang perlu diperbarui
5. Klik tombol "Update Data" (tombol "Tambah Data" akan berubah menjadi "Update Data")

### 3.4 Menghapus Anggota

1. Cari anggota keluarga yang ingin dihapus di Data Tree
2. Klik tombol "Hapus" (icon tempat sampah)
3. Konfirmasi penghapusan pada dialog yang muncul
   - Jika anggota memiliki anak, semua anaknya juga akan ikut terhapus
   - Pastikan Anda yakin sebelum melanjutkan

### 3.5 Menggunakan Undo dan Redo

Aplikasi mendukung fitur undo/redo untuk perubahan data:
- Tekan **Ctrl+Z** untuk membatalkan perubahan terakhir (undo)
- Tekan **Ctrl+Y** untuk mengulangi perubahan yang dibatalkan (redo)

## 4. Pencarian dan Filter

### 4.1 Mencari Anggota Keluarga

1. Gunakan field pencarian di bagian atas Data Tree
2. Ketikkan nama atau bagian nama yang ingin dicari
3. Hasil pencarian akan langsung ditampilkan:
   - Anggota keluarga yang cocok dengan kriteria pencarian akan tetap ditampilkan
   - Anggota yang tidak cocok akan disembunyikan
   - Anggota yang cocok akan di-highlight dengan latar belakang biru muda

### 4.2 Memfilter Berdasarkan Generasi

1. Gunakan dropdown filter di samping field pencarian
2. Pilih generasi yang ingin ditampilkan (0-5) atau "Semua Generasi"
3. Data Tree akan menampilkan hanya anggota keluarga pada generasi yang dipilih

## 5. Ekspor dan Impor Data

### 5.1 Mengekspor Data

1. Klik tombol "Export Data" di bawah form
2. File JSON akan otomatis diunduh dengan format nama `family-data-YYYY-MM-DD.json`
3. Simpan file tersebut di lokasi yang aman sebagai backup

### 5.2 Mengimpor Data

1. Klik tombol "Import Data" di bawah form
2. Pilih file JSON yang berisi data keluarga
   - File harus dalam format yang sama dengan file ekspor dari aplikasi ini
3. Konfirmasi impor pada dialog yang muncul
   - Perhatikan bahwa impor akan menggantikan semua data yang ada saat ini
4. Data akan dimuat dan ditampilkan di Data Tree

### 5.3 Generate CompleteData

1. Klik tombol "Generate CompleteData"
2. Struktur data JavaScript akan diperbarui di panel Generated CompleteData
3. Klik tombol "Copy Code" untuk menyalin kode ke clipboard
   - Kode ini bisa digunakan dalam project JavaScript lain

## 6. Pemecahan Masalah

### 6.1 Data Tidak Tersimpan

Jika data tidak tersimpan secara otomatis:
- Pastikan browser Anda mengizinkan localStorage
- Cobalah mengekspor data secara manual sebagai langkah pengamanan
- Periksa apakah mode penyamaran (incognito/private browsing) diaktifkan, karena mode ini biasanya tidak menyimpan localStorage

### 6.2 Validasi Gagal

Jika validasi data gagal:
- Periksa pesan error yang ditampilkan
- Pastikan semua anggota keluarga memiliki nama yang valid
- Pastikan hubungan generasi sudah benar (anak selalu memiliki generasi yang lebih tinggi dari orang tua)
- Periksa apakah ada data duplikat atau rusak

### 6.3 Impor Data Gagal

Jika terjadi kesalahan saat mengimpor data:
- Pastikan format file JSON sudah benar
- Periksa apakah file tersebut memang file ekspor dari aplikasi ini
- Coba buka file dengan text editor untuk memastikan isinya tidak rusak

## 7. Tips dan Trik

### 7.1 Penggunaan Keyboard

- **Ctrl+Z**: Undo (membatalkan perubahan terakhir)
- **Ctrl+Y**: Redo (mengulangi perubahan yang dibatalkan)
- **Ctrl+S**: Menyimpan data secara manual ke localStorage

### 7.2 Organisasi Data yang Efektif

- Mulailah dengan generasi tertua (0) dan bekerja ke bawah
- Gunakan nama lengkap untuk menghindari kebingungan dengan anggota keluarga yang memiliki nama sama
- Tambahkan informasi pasangan untuk memperjelas hubungan keluarga

### 7.3 Backup Berkala

- Ekspor data secara berkala sebagai backup
- Simpan file ekspor di beberapa lokasi (komputer lokal, cloud storage, dll.)
- Pertimbangkan untuk membuat beberapa versi file ekspor dengan tanggal yang berbeda

### 7.4 Mengoptimalkan untuk Keluarga Besar

- Gunakan fitur pencarian dan filter untuk menavigasi keluarga besar
- Validasi data secara berkala untuk memastikan konsistensi
- Pertimbangkan untuk membagi keluarga sangat besar menjadi beberapa file terpisah berdasarkan cabang keluarga

---

Terima kasih telah menggunakan Keluarga Visualizer! Jika Anda memiliki pertanyaan atau mengalami masalah yang tidak tercakup dalam dokumentasi ini, silakan buka Issue di repository GitHub kami.
