Tujuan: Menyiapkan Ubuntu agar siap digunakan untuk aktivitas harian, multimedia, coding, dan praktik Linux.

Buka Terminal dengan `Ctrl + Alt + T`.

## 1. Update dan upgrade sistem

Jalankan:

```
sudo apt update
sudo apt upgrade
```

Bedah syntax:

| Syntax    | Fungsi                                        |
| --------- | --------------------------------------------- |
| `sudo`    | Menjalankan perintah dengan hak administrator |
| `apt`     | Package manager Ubuntu                        |
| `update`  | Memperbarui daftar paket dari repository      |
| `upgrade` | Memperbarui aplikasi dan paket yang terpasang |

Bisa juga digabung:

```
sudo apt update && sudo apt upgrade
```

`&&` berarti perintah kedua hanya dijalankan jika perintah pertama berhasil.

Tambahan:

- `-y` = otomatis menjawab Yes saat konfirmasi.
- Untuk belajar, sebaiknya jangan pakai `-y` dulu supaya lu bisa melihat paket apa saja yang akan diperbarui.

## 2. Install driver tambahan

Driver berfungsi sebagai penghubung antara OS dengan hardware.

Contohnya:

- NVIDIA GPU → driver NVIDIA.
- Wi-Fi → driver wireless.
- Printer → driver printer.

Cara GUI:

1. Buka aplikasi Software & Updates jika tersedia.
2. Pilih tab Additional Drivers.
3. Pilih driver yang direkomendasikan.
4. Klik Apply Changes.
5. Restart.

Cara Terminal:

Cek driver yang tersedia:

```
sudo ubuntu-drivers list
```

Pasang driver yang direkomendasikan secara otomatis:

```
sudo ubuntu-drivers install
```

Restart setelah instalasi:

```
sudo reboot
```

Bedah syntax:

| Perintah         | Fungsi                                            |
| ---------------- | ------------------------------------------------- |
| `ubuntu-drivers` | Tool untuk mendeteksi dan mengelola driver Ubuntu |
| `list`           | Menampilkan pilihan driver                        |
| `install`        | Memasang driver yang direkomendasikan             |

Catatan: tidak semua hardware membutuhkan driver tambahan. GPU Intel dan AMD umumnya sudah menggunakan driver open-source bawaan. Jangan asal memasang driver proprietary.

Pada Ubuntu 26.04, aplikasi Software & Updates tidak disertakan secara default dan bisa dipasang dengan `sudo apt install software-properties-gtk`

## 3. Install multimedia codec

Codec dibutuhkan agar Ubuntu dapat memutar berbagai format audio dan video.

Contohnya MP3, beberapa format video, dan font tambahan.

Install:

```
sudo apt install ubuntu-restricted-extras
```

Bedah syntax:

- `apt install` = memasang aplikasi atau paket.
- `ubuntu-restricted-extras` = paket kumpulan codec, font, dan komponen multimedia tambahan.

Perhatian

Saat instalasi mungkin muncul persetujuan lisensi Microsoft Fonts (EULA). Baca dan setujui jika memang ingin memasangnya.

Paket ini bersifat opsional. Pasang ketika memang membutuhkan dukungan multimedia tambahan.



## 4. Install Flatpak dan hubungkan Flathub

Apa itu Flatpak?

Flatpak adalah sistem distribusi aplikasi Linux. Aplikasi bisa dipasang terpisah dari repository APT Ubuntu.

Analogi:

- APT = toko aplikasi Ubuntu.
- Flathub = toko aplikasi yang menyediakan banyak aplikasi Flatpak.
- Flatpak = teknologi untuk memasang dan menjalankan aplikasi tersebut.

Langkah 1 — Install Flatpak

```
sudo apt install flatpak
```

Langkah 2 — Tambahkan Flathub

```
sudo flatpak remote-add --system --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo
```

Penjelasan syntax:

| Syntax            | Fungsi                                    |
| ----------------- | ----------------------------------------- |
| `remote-add`      | Menambahkan sumber aplikasi               |
| `--system`        | Menambahkan sumber untuk seluruh pengguna |
| `--if-not-exists` | Tidak menambahkan ulang jika sudah ada    |
| `flathub`         | Nama repository                           |
| URL               | Alamat repository Flathub                 |

Langkah 3 — Cek repository

```
flatpak remotes
```

Langkah 4 — Contoh install GIMP

```
flatpak install flathub org.gimp.GIMP
```

Langkah 5 — Cek aplikasi yang terpasang

```
flatpak list --app
```

Langkah 6 — Update aplikasi Flatpak

```
flatpak update
```

Kalau ingin GUI khusus untuk mencari dan memasang aplikasi Flatpak, bisa memasang Bazaar:

```
flatpak install flathub io.github.kolunmi.Bazaar
```

Restart setelah konfigurasi awal Flatpak selesai.


## 5. Install aplikasi sehari-hari

Tidak perlu memasang semuanya. Pilih sesuai kebutuhan.

| Kategori       | Aplikasi        | Fungsi                     |
| -------------- | --------------- | -------------------------- |
| Browser        | Firefox, Chrome | Browsing internet          |
| Multimedia     | VLC             | Memutar audio dan video    |
| Office         | LibreOffice     | Word, Excel, PowerPoint    |
| Desain         | GIMP            | Edit gambar                |
| Desain vektor  | Inkscape        | Membuat logo dan ilustrasi |
| Coding         | VS Code         | Editor kode                |
| File Manager   | Nautilus        | Mengelola file dan folder  |
| System monitor | htop            | Memantau CPU, RAM, proses  |

### Install melalui APT

Contoh memasang beberapa aplikasi sekaligus:

```
sudo apt install vlc libreoffice gimp inkscape git curl wget unzip htop tree nautilus
```

Penjelasan:

- `vlc` = multimedia player.
- `libreoffice` = aplikasi perkantoran.
- `gimp` = editor gambar.
- `inkscape` = desain vektor.
- `git` = version control.
- `curl`, `wget` = mengambil data atau file dari internet.
- `unzip` = ekstrak file ZIP.
- `htop` = monitoring resource.
- `tree` = melihat struktur folder.
- `nautilus` = file manager.

Kenapa bisa banyak nama setelah `apt install`?

Karena APT bisa memasang beberapa paket sekaligus dengan memisahkan nama paket menggunakan spasi.

### Install Google Chrome

Chrome tidak tersedia di repository Ubuntu default. Gunakan paket resmi Google.

1. Buka situs [Google Chrome](https://www.google.com/chrome/?utm_source=chatgpt.com).
2. Download paket `.deb` sesuai arsitektur CPU.
3. Buka Terminal di folder Downloads.

```
cd ~/Downloads
ls *.deb
```

4\. Install paketnya:

```
sudo apt install ./google-chrome-stable_current_amd64.deb
```

Ganti nama file apabila berbeda.

Kenapa ada `./`?

Karena kita memberi tahu APT bahwa file `.deb` berada di direktori saat ini, bukan meminta APT mencari nama paket di repository.

### Install Visual Studio Code

1. Buka [Website resmi VS Code](https://code.visualstudio.com/?utm_source=chatgpt.com).
2. Download paket `.deb`.
3. Buka folder Downloads.

```
cd ~/Downloads
ls *.deb
```

4\. Pasang:

```
sudo apt install ./nama-file-vscode.deb
```

Ganti `nama-file-vscode.deb` dengan nama file yang benar.

Paket resmi VS Code dapat menambahkan repository dan signing key Microsoft agar pembaruan selanjutnya bisa dikelola melalui package manager.



## 6. Cek hasil instalasi dan kondisi sistem

Setelah selesai, cek beberapa informasi penting:

```
# Identitas Ubuntu
hostnamectl

# Versi kernel
uname -r

# IP address
ip -br addr

# Kapasitas storage
df -h

# Penggunaan RAM
free -h

# Aplikasi yang punya pembaruan
apt list --upgradable

# Service yang gagal
systemctl --failed
```

