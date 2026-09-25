# Instalasi Sistem Operasi Ubuntu Linux


<img width="208" height="96" alt="Image" src="https://github.com/user-attachments/assets/82b42da6-69f3-47cc-a25a-8d3bb96e9a1c" />

Pilih **Try or Install Ubuntu** jika Anda ingin masuk ke sistem untuk mencoba atau menginstal OS secara normal.

Berikut adalah penjelasan fungsi untuk masing-masing opsi:

| Opsi Boot | Fungsi |
| --- | --- |
| **Try or Install Ubuntu** | Pilihan standar. Memuat sistem untuk mencoba Ubuntu tanpa *install* (Live USB) atau untuk memulai instalasi normal. |
| **Ubuntu (safe graphics)** | Mode aman. Hanya pilih opsi ini jika menu pertama gagal atau menyebabkan layar hitam akibat kendala kompatibilitas *driver* kartu grafis (VGA). |
| **Boot from next volume** | Batal *booting* dari media instalasi ini dan mencoba memuat OS dari urutan penyimpanan berikutnya (misalnya Windows di *hard disk* internal). |
| **UEFI Firmware Settings** | Jalan pintas untuk *restart* dan langsung masuk ke menu pengaturan BIOS/UEFI komputer tanpa perlu repot menekan tombol *keyboard*. |

<img width="250" height="260" alt="Image" src="https://github.com/user-attachments/assets/8bb6b840-e89d-4d99-95c6-a54b905528ec" />

Tunggu Proses Bootingnya

### 1. Pemilihan Mode Penggunaan (Try vs. Install)

Layar pertama akan meminta Anda menentukan tujuan penggunaan sistem operasi.

| Pilihan | Fungsi Utama |
| --- | --- |
| **Install Ubuntu** | Memasang sistem operasi Ubuntu secara permanen ke dalam *hard disk* (atau virtual disk). Data dan sistem akan tersimpan permanen. |
| **Try Ubuntu** | Menjalankan sistem operasi melalui media instalasi (Live CD/USB) untuk sekadar dicoba. Semua file, pengaturan, dan perubahan akan hilang setelah komputer di-*restart*. |

**Instruksi Praktikum:** Pilih **Install Ubuntu** agar sistem operasi terpasang sepenuhnya dan bisa dikonfigurasi lebih lanjut pada pertemuan berikutnya.

---

### 2. Penentuan Metode Instalasi

Langkah ini menentukan bagaimana proses *setup* akan berjalan.

| Pilihan | Cara Kerja |
| --- | --- |
| **Interactive installation** | Instalasi manual. Pengguna akan dipandu secara visual langkah demi langkah untuk mengatur bahasa, partisi disk, hingga pembuatan akun. |
| **Automated installation** | Instalasi otomatis tanpa campur tangan pengguna. Menggunakan file *script* (`autoinstall.yaml`) untuk mempercepat instalasi massal dengan konfigurasi yang seragam. |

**Instruksi Praktikum:** Pilih **Interactive installation** agar setiap tahapan konfigurasi dapat dipelajari dan dipraktikkan secara langsung.

---

### 3. Pemilihan Paket Aplikasi Bawaan

Menentukan seberapa banyak perangkat lunak yang langsung tersedia setelah instalasi selesai.

| Pilihan | Isi Paket | Dampak pada Sistem |
| --- | --- | --- |
| **Default selection** | Minimalis (Hanya *web browser* dan utilitas dasar). | Proses instalasi sangat cepat, hemat kapasitas *storage*, dan membebani RAM lebih sedikit. |
| **Extended selection** | Lengkap (*Office tools*, pemutar media, utilitas tambahan). | Waktu instalasi lebih lama dan butuh kapasitas *storage* yang jauh lebih besar. Didesain untuk penggunaan *offline*. |

**Instruksi Praktikum:** Pilih **Default selection**. Opsi ini paling ideal untuk mesin virtual karena sangat ringan dan mempercepat waktu tunggu saat demonstrasi.

---

### 4. Perangkat Lunak Pihak Ketiga & Format Media

Bagian ini menangani *driver* perangkat keras tertutup (*proprietary*) dan *codec* multimedia berlisensi. Terdapat perbedaan perlakuan tergantung pada media instalasinya.

| Pilihan | Jika Diinstal di Fisik (*Baremetal*) | Jika Diinstal di Mesin Virtual |
| --- | --- | --- |
| **Install third-party software for graphics and Wi-Fi hardware** | **Wajib dicentang** agar modul Wi-Fi (Broadcom/Realtek) dan kartu grafis (NVIDIA/AMD) dapat berfungsi optimal dan tidak *lag*. | **Dikosongkan**. VirtualBox menggunakan *hardware* virtual standar yang langsung didukung oleh Ubuntu. |
| **Download and install support for additional media formats** | **Wajib dicentang** agar sistem bisa memutar format video/audio populer berlisensi (MP3, MP4, MOV, AAC). | **Dikosongkan** (Opsional). Untuk menghemat waktu instalasi saat demo, ini bisa dilewati. |

**Instruksi Praktikum:** Biarkan **kedua kotak tidak dicentang** karena instalasi dilakukan di dalam VirtualBox.

---

### 5. Pengaturan Partisi Hard Disk

Menentukan bagaimana ruang penyimpanan akan dialokasikan untuk sistem operasi.

| Pilihan | Fungsi & Cara Kerja |
| --- | --- |
| **Erase disk and install Ubuntu** | Sistem akan memformat seluruh isi disk dan membuat struktur partisi dasar Linux (seperti `/root` dan `/boot/efi`) secara otomatis. |
| **Manual installation** | Pengguna harus membuat, membagi, dan menentukan ukuran serta jenis format partisi secara manual (memisahkan `/`, `/home`, dan `swap`). |

**Instruksi Praktikum:** Pilih **Erase disk and install Ubuntu**. Karena menggunakan *virtual hard disk* kosong, opsi ini 100% aman (tidak menghapus data OS utama laptop) dan efisien.

---

### 6. Pembuatan Akun Pengguna (User Details)

Tahap pengisian identitas administrator lokal pada sistem.

**A. Pengisian Data Kolom Teks**

| Kolom | Deskripsi | Aturan Penulisan |
| --- | --- | --- |
| **Your name** | Nama tampilan (*Display Name*) di layar *login*. | Bebas (Boleh huruf besar, spasi, nama lengkap). |
| **Your computer's name** | Nama perangkat (*Hostname*) yang terlihat di jaringan. | Tanpa spasi, tanpa simbol khusus. (Contoh: `siswa-virtualbox`). |
| **Your username** | Nama sistem (*User ID*) untuk direktori `/home` dan identitas Terminal. | **Wajib huruf kecil semua**, tanpa spasi, tanpa simbol. |
| **Password** & **Confirm** | Sandi akses *login* dan hak *root/sudo*. | Harus identik di kedua kolom. |

**B. Pengaturan Opsi Login**

| Pilihan | Jika Dicentang | Jika Tidak Dicentang |
| --- | --- | --- |
| **Require my password to log in** | Wajib memasukkan sandi setiap kali komputer dinyalakan. | *Auto-login* langsung masuk ke *desktop* tanpa hambatan keamanan. |
| **Use Active Directory** | Komputer tergabung dalam sistem server manajemen terpusat sekolah/perusahaan. | Akun bersifat lokal mandiri (*standalone*). |

**Instruksi Praktikum:** Isi data akun sesuai instruksi, centang opsi **Require my password to log in**, dan biarkan opsi **Use Active Directory** kosong.

---

### 7. Pengaturan Zona Waktu (Timezone)

Sistem akan menampilkan peta dunia untuk sinkronisasi jam komputer. Titik *pin* akan otomatis mendeteksi lokasi geografis jika perangkat terhubung ke internet.

* **Pita Biru & Area Hijau:** Menunjukkan wilayah yang beroperasi pada zona waktu yang sama dengan titik *pin*.
* **Instruksi Praktikum:** Pastikan *pin* berada di wilayah Indonesia (seperti **Asia/Jakarta** untuk UTC+7). Klik "Continue" untuk memulai proses instalasi akhir.
