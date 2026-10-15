PARTISI DAN FILESYSTEM

<img width="1672" height="941" alt="Image" src="https://github.com/user-attachments/assets/16aef037-df61-4637-9b29-a4e4feff1464" />

## 1. Contoh Pembagian Partisi Linux

Partisi Linux memiliki fungsi berbeda-beda. Ada yang digunakan untuk booting, menjalankan sistem operasi, menyimpan file pengguna, dan menyediakan memori virtual.

| Partisi     | Fungsi                                                     | Filesystem umum                           |
| ----------- | ---------------------------------------------------------- | ----------------------------------------- |
| `/boot/efi` | Menyimpan file bootloader untuk UEFI                       | FAT32                                     |
| `/boot`     | Menyimpan kernel Linux dan file pendukung boot             | ext4, jika dipisah                        |
| `/` (root)  | Menyimpan sistem operasi, aplikasi, dan konfigurasi sistem | ext4, Btrfs                               |
| `/home`     | Menyimpan file pribadi dan konfigurasi pengguna            | ext4, Btrfs                               |
| `swap`      | Membantu mekanisme memori virtual                          | Swap, bukan ext4                          |
| `/var`      | Menyimpan log, cache, dan data yang sering berubah         | ext4, Btrfs                               |
| `/tmp`      | Menyimpan file sementara                                   | Biasanya bagian dari `/`, bisa juga tmpfs |
| `/usr`      | Menyimpan banyak program, pustaka, dan data sistem         | Biasanya bagian dari `/`                  |
| `/opt`      | Lokasi umum perangkat lunak tambahan                       | Biasanya bagian dari `/`                  |
| `/data`     | Menyimpan data tambahan sesuai kebutuhan                   | ext4, Btrfs                               |

Catatan: semua nama di atas merupakan direktori atau mount point, kecuali `swap` yang merupakan area khusus untuk memori virtual. Tidak semuanya harus dibuat sebagai partisi terpisah.



## 2. Contoh Pembagian Partisi Berdasarkan Kapasitas

Berikut contoh untuk komputer dengan SSD 1 TB yang menggunakan UEFI.

| Partisi              | Ukuran contoh    | Filesystem       | Mount point      | Fungsi                         |
| -------------------- | ---------------- | ---------------- | ---------------- | ------------------------------ |
| EFI System Partition | 512 MiB          | FAT32            | `/boot/efi`      | File boot UEFI                 |
| Root                 | 100 GiB          | ext4             | `/`              | Sistem operasi dan aplikasi    |
| Home                 | 700 GiB          | ext4             | `/home`          | Data pengguna                  |
| Swap                 | 8 GiB            | Swap             | Tidak ada        | Memori virtual                 |
| Sisa ruang           | Sesuai kebutuhan | Belum ditentukan | Belum ditentukan | Cadangan atau partisi tambahan |

Ukuran tersebut hanyalah contoh. Kapasitas partisi sebaiknya disesuaikan dengan kebutuhan aplikasi, data, RAM, dan hibernasi.

Konfigurasi yang lebih sederhana: EFI + root `/` + swapfile yang diatur distro jika didukung. `/home` tetap tersedia sebagai direktori di dalam `/`, sehingga tidak wajib dipisahkan.

## 3. Perbedaan Partisi dan Filesystem

| Istilah     | Pengertian                           | Contoh                     |
| ----------- | ------------------------------------ | -------------------------- |
| Disk        | Perangkat penyimpanan fisik          | SSD 1 TB                   |
| Partisi     | Pembagian logis pada disk            | `/dev/sda1`                |
| Filesystem  | Struktur untuk mengatur file         | ext4, Btrfs, FAT32         |
| Mount point | Direktori tempat filesystem dipasang | `/`, `/home`               |
| Swap        | Area untuk mekanisme memori virtual  | Partisi swap atau swapfile |

Contoh: partisi `/dev/sda2` dapat diformat dengan ext4, lalu dipasang pada mount point `/`. Dengan demikian, partisi tersebut menjadi filesystem utama Linux.
