# Instalasi Sistem Operasi Ubuntu Linux

Langkah Awal

<img width="208" height="96" alt="Image" src="https://github.com/user-attachments/assets/82b42da6-69f3-47cc-a25a-8d3bb96e9a1c" />


Pilih **Try or Install Ubuntu** jika Anda ingin masuk ke sistem untuk mencoba atau menginstal OS secara normal.

Berikut adalah penjelasan fungsi untuk masing-masing opsi:

| Opsi Boot | Fungsi |
| --- | --- |
| **Try or Install Ubuntu** | Pilihan standar. Memuat sistem untuk mencoba Ubuntu tanpa *install* (Live USB) atau untuk memulai instalasi normal. |
| **Ubuntu (safe graphics)** | Mode aman. Hanya pilih opsi ini jika menu pertama gagal atau menyebabkan layar hitam akibat kendala kompatibilitas *driver* kartu grafis (VGA). |
| **Boot from next volume** | Batal *booting* dari media instalasi ini dan mencoba memuat OS dari urutan penyimpanan berikutnya (misalnya Windows di *hard disk* internal). |
| **UEFI Firmware Settings** | Jalan pintas untuk *restart* dan langsung masuk ke menu pengaturan BIOS/UEFI komputer tanpa perlu repot menekan tombol *keyboard*. |

---

Tunggu Proses Bootingnya

<img width="250" height="260" alt="Image" src="https://github.com/user-attachments/assets/8bb6b840-e89d-4d99-95c6-a54b905528ec" />


---

Pilih Bahasa

<img width="749" height="493" alt="Image" src="https://github.com/user-attachments/assets/59771a96-5fc0-4cde-935e-74d894854307" />


---

Next

<img width="810" height="487" alt="Image" src="https://github.com/user-attachments/assets/46a7a72c-bee9-4adb-baa9-8e237585beae" />


---

Pilih Bahasa Keyboard

<img width="812" height="525" alt="Image" src="https://github.com/user-attachments/assets/0451a703-ef5b-4f4d-9fbf-14c1a3ee13af" />


---

Pilih Internet LAN atau WLAN

<img width="810" height="445" alt="Image" src="https://github.com/user-attachments/assets/d78c2efd-c9af-44f3-a1ff-6e32cdcd637b" />


---

Skip Update

<img width="501" height="403" alt="image" src="https://github.com/user-attachments/assets/a8a36a9e-704c-47f7-8462-3b6b57ded30e" />


---

### 1. Pemilihan Mode Penggunaan (Try vs. Install)

Layar pertama akan meminta Anda menentukan tujuan penggunaan sistem operasi.

<img width="816" height="457" alt="image" src="https://github.com/user-attachments/assets/e39d0107-8688-4318-ae77-dbabd34ff300" />


| Pilihan | Fungsi Utama |
| --- | --- |
| **Install Ubuntu** | Memasang sistem operasi Ubuntu secara permanen ke dalam *hard disk* (atau virtual disk). Data dan sistem akan tersimpan permanen. |
| **Try Ubuntu** | Menjalankan sistem operasi melalui media instalasi (Live CD/USB) untuk sekadar dicoba. Semua file, pengaturan, dan perubahan akan hilang setelah komputer di-*restart*. |

**Instruksi Praktikum:** Pilih **Install Ubuntu** agar sistem operasi terpasang sepenuhnya dan bisa dikonfigurasi lebih lanjut pada pertemuan berikutnya.

---

### 2. Penentuan Metode Instalasi

Langkah ini menentukan bagaimana proses *setup* akan berjalan.

<img width="814" height="483" alt="image" src="https://github.com/user-attachments/assets/aea8dec8-9ff4-4b05-846f-c23754d900a7" />


Pilih **Interactive installation**. Ini adalah pilihan standar untuk dipandu langkah demi langkah secara manual.

Berikut penjelasan untuk ketiga opsi tersebut:

| Opsi | Penjelasan |
| --- | --- |
| **Interactive installation** | Instalasi normal di mana Anda akan mengatur semuanya (bahasa, jaringan, partisi *disk*) secara manual langkah demi langkah. |
| **Automated with autoinstall file** | Instalasi otomatis menggunakan file konfigurasi khusus (`autoinstall.yaml`). Opsi ini dipakai oleh *sysadmin* tingkat lanjut yang ingin menyalin pengaturan instalasi yang sama ke puluhan server agar cepat. |
| **Automated with Landscape** | Instalasi otomatis yang dikendalikan dari jarak jauh melalui Landscape (sistem manajemen server dari Canonical/Ubuntu). Opsi ini khusus untuk lingkungan perusahaan/organisasi berskala besar. |

---

### 3. Pemilihan Paket Aplikasi Bawaan

Menentukan seberapa banyak perangkat lunak yang langsung tersedia setelah instalasi selesai.

<img width="816" height="448" alt="image" src="https://github.com/user-attachments/assets/30d9d70e-2951-4a13-a00e-c0371e6a1755" />


| Pilihan | Isi Paket | Dampak pada Sistem |
| --- | --- | --- |
| **Default selection** | Minimalis (Hanya *web browser* dan utilitas dasar). | Proses instalasi sangat cepat, hemat kapasitas *storage*, dan membebani RAM lebih sedikit. |
| **Extended selection** | Lengkap (*Office tools*, pemutar media, utilitas tambahan). | Waktu instalasi lebih lama dan butuh kapasitas *storage* yang jauh lebih besar. Didesain untuk penggunaan *offline*. |

**Instruksi Praktikum:** Pilih **Default selection**. Opsi ini paling ideal untuk mesin virtual karena sangat ringan dan mempercepat waktu tunggu saat demonstrasi.

---

### 4. Perangkat Lunak Pihak Ketiga & Format Media

Bagian ini menangani *driver* perangkat keras tertutup (*proprietary*) dan *codec* multimedia berlisensi. Terdapat perbedaan perlakuan tergantung pada media instalasinya.

<img width="811" height="467" alt="image" src="https://github.com/user-attachments/assets/58a8f96c-a3e5-4a1e-9ae4-5e7e20417d18" />


| Pilihan | Jika Diinstal di Fisik (*Baremetal*) | Jika Diinstal di Mesin Virtual |
| --- | --- | --- |
| **Install third-party software for graphics and Wi-Fi hardware** | **Wajib dicentang** agar modul Wi-Fi (Broadcom/Realtek) dan kartu grafis (NVIDIA/AMD) dapat berfungsi optimal dan tidak *lag*. | **Dikosongkan**. VirtualBox menggunakan *hardware* virtual standar yang langsung didukung oleh Ubuntu. |
| **Download and install support for additional media formats** | **Wajib dicentang** agar sistem bisa memutar format video/audio populer berlisensi (MP3, MP4, MOV, AAC). | **Dikosongkan** (Opsional). Untuk menghemat waktu instalasi saat demo, ini bisa dilewati. |

**Instruksi Praktikum:** Biarkan **kedua kotak tidak dicentang** karena instalasi dilakukan di dalam VirtualBox.

---

### 5. Pengaturan Partisi Hard Disk

Menentukan bagaimana ruang penyimpanan akan dialokasikan untuk sistem operasi.

<img width="810" height="446" alt="image" src="https://github.com/user-attachments/assets/0ec9e4dc-f196-4d16-9dd0-4a68e0226cb3" />


| Pilihan | Fungsi & Cara Kerja |
| --- | --- |
| **Erase disk and install Ubuntu** | Sistem akan memformat seluruh isi disk dan membuat struktur partisi dasar Linux (seperti `/root` dan `/boot/efi`) secara otomatis. |
| **Manual installation** | Pengguna harus membuat, membagi, dan menentukan ukuran serta jenis format partisi secara manual (memisahkan `/`, `/home`, dan `swap`). |

**Instruksi Praktikum:** Pilih **Erase disk and install Ubuntu**. Karena menggunakan *virtual hard disk* kosong, opsi ini 100% aman (tidak menghapus data OS utama laptop) dan efisien.

---

### 6. Encryption and file system

<img width="815" height="571" alt="image" src="https://github.com/user-attachments/assets/7dd11830-2bb3-40ba-90e8-c640209e7f47" />


Gambar di atas menunjukkan layar pengaturan **Encryption and file system** (Enkripsi dan sistem file) saat menginstal sistem operasi berbasis Linux (kemungkinan besar Ubuntu versi terbaru berdasarkan desain antarmukanya).

Langkah ini meminta Anda untuk menentukan tingkat keamanan dan struktur partisi *hard drive/SSD*.

Berikut penjelasan untuk masing-masing opsi:

**1. No encryption (Paling direkomendasikan untuk penggunaan standar)**

* **Penjelasan:** Data di dalam *disk* tidak dikunci (*encrypt*). Sistem akan menggunakan partisi standar (biasanya ext4).
* **Kapan digunakan:** Pilih opsi ini jika ini adalah instalasi komputer rumahan, *server* latihan, atau jika *disk* Anda tidak menyimpan data rahasia/sensitif tingkat tinggi. Instalasi dan proses memuat (*booting*) akan sedikit lebih cepat.

**2. Encrypt with a passphrase (Aman, tapi butuh *password* tiap menyala)**

* **Penjelasan:** Menggunakan teknologi LUKS. Seluruh isi *disk* akan dikunci.
* **Kapan digunakan:** Wajib dipilih jika ini adalah laptop kantor, laptop yang sering dibawa bepergian, atau server yang menyimpan data klien.
* **Peringatan:** Anda **harus** memasukkan *password* (passphrase) setiap kali komputer baru dinyalakan, sebelum masuk ke menu *login* pengguna. Jika lupa *password* ini, seluruh data Anda hilang permanen dan tidak bisa dikembalikan.

**3. Use hardware-backed encryption (Sangat Aman, otomatis)**

* **Penjelasan:** Menggunakan *chip* keamanan bawaan komputer (seperti TPM). *Disk* akan terkunci, tetapi komputer akan membuka kuncinya secara otomatis di belakang layar saat proses *startup*.
* **Kapan digunakan:** Sangat bagus jika perangkat keras Anda mendukung fitur ini. Keamanannya setara dengan nomor 2, namun jauh lebih praktis karena tidak perlu mengetik *password* tambahan setiap kali komputer menyala.

**Advanced options (Pilihan Lanjutan):**

* **Use LVM without encryption:** Menggunakan *Logical Volume Manager* tanpa dikunci. Berguna untuk *server* jika di masa depan Anda berencana menggabungkan kapasitas dari beberapa *hard drive* baru menjadi satu penyimpanan besar, atau ingin membuat *snapshot* sistem.
* **Use ZFS without encryption (Experimental):** ZFS adalah sistem *file* yang sangat canggih dengan fitur pemulihan data mandiri (*self-healing*) bawaan dan kompresi yang bagus. Berguna untuk *server* penyimpanan data rahasia skala besar, namun membutuhkan memori (RAM) yang tinggi.
* **Encrypt with a passphrase using ZFS (Experimental):** Sama seperti ZFS, namun ditambahkan sistem penguncian *password*.

**Pilih yang mana?**
Jika Anda ragu atau hanya melakukan instalasi biasa, biarkan pilihan tetap di **No encryption** (titik oranye), lalu klik tombol **Next**.

---

### 7. Pembuatan Akun Pengguna (User Details)

Tahap pengisian identitas administrator lokal pada sistem.

<img width="820" height="507" alt="image" src="https://github.com/user-attachments/assets/64b059e0-7edc-448b-a621-976b453fc594" />


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

### 8. Pengaturan Zona Waktu (Timezone)

Sistem akan menampilkan peta dunia untuk sinkronisasi jam komputer. Titik *pin* akan otomatis mendeteksi lokasi geografis jika perangkat terhubung ke internet.

<img width="818" height="578" alt="image" src="https://github.com/user-attachments/assets/c0fea8d4-6ddb-412a-9a8c-9d8235eb7506" />


* **Pita Biru & Area Hijau:** Menunjukkan wilayah yang beroperasi pada zona waktu yang sama dengan titik *pin*.
* **Instruksi Praktikum:** Pastikan *pin* berada di wilayah Indonesia (seperti **Asia/Jakarta** untuk UTC+7). Klik "Continue" untuk memulai proses instalasi akhir.

---

**Terakhir**

<img width="817" height="577" alt="image" src="https://github.com/user-attachments/assets/ada73543-2f92-47b8-b48d-c1c6a1e79913" />


Klik Install
