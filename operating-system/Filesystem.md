# Semua Jenis Filesystem pada Flashdisk, HDD, SSD, Windows dan Linux

Saat memformat flashdisk, biasanya muncul pilihan filesystem seperti FAT32, exFAT, NTFS, dan terkadang pilihan lain. Di Linux, kita juga akan menemukan ext4, Btrfs, XFS, dan banyak filesystem lainnya.

Walaupun semuanya disebut filesystem, fungsi, kompatibilitas, dan keunggulannya berbeda.

## 1. Apa itu filesystem?

Filesystem adalah sistem yang mengatur bagaimana file disimpan, diberi nama, dikelompokkan dalam folder, dan ditemukan kembali oleh sistem operasi.

Analogi sederhana:

- Flashdisk, HDD, atau SSD: gudang penyimpanan.
- Partisi: pembagian ruangan di dalam gudang.
- Filesystem: sistem rak dan katalog yang mengatur barang di setiap ruangan.
- File dan folder: barang yang disimpan di rak.

Saat memilih Format di Windows, kalian biasanya memilih filesystem yang akan dibuat pada partisi atau volume flashdisk tersebut.

<img width="472" height="311" alt="Image" src="https://github.com/user-attachments/assets/6da59216-e875-44bc-a700-ed9c90e8375a" />

Penting: filesystem bukan kapasitas penyimpanan dan bukan jenis konektor. Flashdisk USB 64 GB tetap berkapasitas fisik yang sama, baik diformat dengan FAT32, exFAT, maupun NTFS, meskipun ruang yang dapat digunakan dan overhead filesystem bisa sedikit berbeda.

## 2. Semua filesystem yang umum ditemui

Filesystem bisa dikelompokkan berdasarkan tujuan penggunaannya. Tidak semua filesystem cocok untuk flashdisk, dan tidak semua filesystem bisa dipilih melalui menu Format Windows.

### A. Filesystem untuk flashdisk dan penyimpanan eksternal

<img width="700" height="442" alt="Image" src="https://github.com/user-attachments/assets/1f795f77-b721-476d-8012-1059ac9eccf4" />

1\. FAT32 (File Allocation Table 32)

Kompatibilitas luas

Filesystem lama yang masih sangat banyak digunakan pada flashdisk, kartu memori, dan perangkat elektronik.

- Bisa dibaca oleh Windows, Linux, dan macOS.
- Kompatibel dengan banyak TV, konsol, kamera, dan perangkat lain.
- Batas ukuran satu file adalah 4 GiB dikurangi 1 byte.
- Tidak mempunyai fitur journaling seperti NTFS atau ext4.

Cocok untuk: flashdisk kecil, perangkat yang mensyaratkan FAT32, dan file berukuran di bawah batasnya.

<img width="1288" height="856" alt="Image" src="https://github.com/user-attachments/assets/f82f815e-d90f-4f9d-be63-a746d02608a6" />

2\. exFAT (Extended File Allocation Table)

Pilihan umum flashdisk modern

Dikembangkan untuk media penyimpanan eksternal dan file berukuran besar.

- Mendukung file lebih dari 4 GB.
- Didukung Windows, macOS, dan Linux modern dengan dukungan yang sesuai.
- Tidak menggunakan journaling seperti NTFS atau ext4.
- Tidak menyediakan fitur permission dan pengelolaan data setingkat filesystem desktop/server modern.

Cocok untuk: flashdisk 64 GB, 128 GB, atau lebih; video besar; pemindahan file antara Windows, macOS, dan Linux.

<img width="937" height="933" alt="Image" src="https://github.com/user-attachments/assets/4e68e05b-cd2c-4e72-8e3d-0c43cf1f98cc" />

3\. NTFS (New Technology File System)

Filesystem utama yang umum digunakan pada partisi Windows.

- Mendukung file berukuran besar.
- Mendukung journaling metadata.
- Mendukung permission, ACL, kompresi, enkripsi melalui fitur tertentu, dan fitur Windows lainnya.
- Linux modern umumnya dapat membaca dan menulis NTFS melalui driver yang sesuai.
- Dukungan penulisan NTFS pada perangkat elektronik tertentu tidak selalu tersedia.

Cocok untuk: HDD/SSD eksternal yang terutama digunakan di Windows, backup Windows, dan file berukuran besar.

<img width="958" height="760" alt="Image" src="https://github.com/user-attachments/assets/054457eb-2736-42cd-a804-e82a57bb2c9d" />

4\. FAT12 dan FAT16

Generasi FAT yang lebih tua, dahulu banyak digunakan pada floppy disk, kartu memori lama, dan media berkapasitas kecil.

Cocok untuk: perangkat lama yang secara khusus mensyaratkannya. Bukan pilihan umum untuk flashdisk modern.

### B. Filesystem untuk Linux

<img width="801" height="566" alt="Image" src="https://github.com/user-attachments/assets/4ec66e37-0f14-4869-a216-80d053073a2f" />

5\. ext2

Filesystem Linux generasi lama yang tidak menggunakan journaling.

- Relatif sederhana.
- Masih dapat ditemukan pada sistem lama atau perangkat khusus.
- Pemulihan setelah mati listrik atau crash dapat membutuhkan pemeriksaan filesystem.

Penggunaan: perangkat lama dan kebutuhan khusus.

<img width="833" height="587" alt="Image" src="https://github.com/user-attachments/assets/d625963a-96e2-4984-b261-32cf9e5b93b9" />

6\. ext3

Pengembangan dari ext2 yang menambahkan journaling.

Journaling membantu menjaga konsistensi metadata setelah sistem mengalami crash, meskipun tidak menjamin semua data yang belum ditulis akan terselamatkan.

Penggunaan: sistem Linux lama dan perangkat yang masih menggunakannya.

<img width="833" height="742" alt="Image" src="https://github.com/user-attachments/assets/6de65742-0e22-472b-809f-20c9290816e4" />

7\. ext4

Filesystem Linux yang matang dan sangat umum digunakan.

- Mendukung journaling.
- Stabil dan relatif sederhana untuk dikelola.
- Cocok untuk sistem operasi, aplikasi, dan data pengguna.
- Tidak memiliki snapshot bawaan seperti Btrfs.

Penggunaan: partisi `/`, `/home`, dan partisi data Linux.

<img width="996" height="729" alt="Image" src="https://github.com/user-attachments/assets/631c4baf-0527-4587-a016-5ee731cada09" />

8\. Btrfs

Filesystem Linux dengan fitur manajemen data yang lebih lanjut.

- Copy-on-write (CoW).
- Checksum untuk data dan metadata.
- Snapshot dan subvolume.
- Kompresi.
- Mendukung fitur RAID tertentu, tetapi konfigurasi dan tingkat kematangannya berbeda-beda.

Penggunaan: desktop atau server Linux yang membutuhkan snapshot dan fitur pengelolaan data.

<img width="1140" height="852" alt="Image" src="https://github.com/user-attachments/assets/1a41d40c-5c53-4030-b8a5-175a52b49c68" />

9\. XFS

Filesystem Linux yang banyak digunakan pada server dan lingkungan enterprise.

- Dirancang untuk menangani filesystem dan file berukuran besar.
- Mendukung journaling metadata.
- Memiliki kemampuan skalabilitas yang baik.
- Umumnya tidak dapat diperkecil secara langsung (shrink) menggunakan fasilitas filesystem standar.

Penggunaan: server, storage data, dan workload besar.

<img width="602" height="602" alt="Image" src="https://github.com/user-attachments/assets/dcc5e21f-e9fd-45ca-b408-85df42aba245" />

10\. ZFS

Sistem penyimpanan yang menggabungkan pengelolaan volume dan filesystem.

- Checksum untuk mendeteksi kerusakan data.
- Snapshot dan cloning.
- Pool penyimpanan yang menggabungkan beberapa perangkat.
- Mendukung redundansi melalui konfigurasi yang sesuai.

Penggunaan: NAS, server, backup, dan storage enterprise. ZFS bukan pilihan umum untuk memformat flashdisk.

<img width="1065" height="780" alt="Image" src="https://github.com/user-attachments/assets/a36e4538-5a6d-4d55-a655-9cae15998a65" />

11\. F2FS (Flash-Friendly File System)

Filesystem yang dirancang dengan karakteristik media berbasis flash sebagai pertimbangan.

Penggunaan: sebagian perangkat embedded, Android, dan sistem Linux tertentu. Tidak lazim dipilih untuk flashdisk umum melalui menu Format Windows.

### C. Filesystem untuk macOS, media optik, dan penggunaan khusus

| Filesystem | Penjelasan                                                                           | Penggunaan umum                                        |
| ---------- | ------------------------------------------------------------------------------------ | ------------------------------------------------------ |
| APFS       | Apple File System; mendukung fitur seperti snapshot dan enkripsi                     | SSD, Mac modern, dan perangkat Apple yang mendukungnya |
| HFS+       | Filesystem Apple generasi sebelumnya                                                 | Mac lama dan media kompatibel                          |
| ISO 9660   | Standar filesystem untuk media optik                                                 | CD-ROM dan sebagian image disk                         |
| UDF        | Filesystem yang digunakan pada berbagai media optik dan skenario penyimpanan lain    | DVD, Blu-ray, dan media tertentu                       |
| ReFS       | Resilient File System milik Microsoft, dengan dukungan yang bergantung edisi Windows | Lingkungan Windows tertentu dan storage khusus         |
| SquashFS   | Filesystem terkompresi yang umumnya hanya dibaca                                     | Live Linux, image sistem, perangkat embedded           |
| tmpfs      | Filesystem sementara yang menggunakan RAM dan dapat memakai swap                     | `/tmp` atau data sementara tertentu di Linux           |
| OverlayFS  | Menggabungkan beberapa lapisan direktori menjadi satu tampilan filesystem            | Container, image sistem, dan sistem Linux tertentu     |

Perlu dibedakan bahwa tmpfs, OverlayFS, dan SquashFS memiliki tujuan khusus. Mereka bukan pilihan format flashdisk biasa.

## 3. Perbandingan FAT32, exFAT, dan NTFS

Ketiganya merupakan pilihan yang paling sering membingungkan ketika memformat flashdisk di Windows.

| Aspek                         | FAT32                                | exFAT                                          | NTFS                                            |
| ----------------------------- | ------------------------------------ | ---------------------------------------------- | ----------------------------------------------- |
| Kompatibilitas perangkat      | Sangat luas                          | Luas pada perangkat modern                     | Baik di Windows, bervariasi pada perangkat lain |
| Batas satu file               | Kurang dari 4 GiB                    | Jauh lebih besar dari kebutuhan flashdisk umum | Jauh lebih besar dari kebutuhan flashdisk umum  |
| Journaling                    | Tidak                                | Tidak                                          | Ya, untuk metadata                              |
| Permission dan ACL            | Tidak seperti NTFS                   | Tidak seperti NTFS                             | Ya                                              |
| File video besar              | Tidak bisa jika file mencapai 4 GiB  | Bisa                                           | Bisa                                            |
| Flashdisk lintas perangkat    | Cocok jika perangkat mendukung FAT32 | Umumnya cocok                                  | Bergantung perangkat                            |
| Disk eksternal khusus Windows | Bisa                                 | Bisa                                           | Umumnya cocok                                   |

Kesimpulan: untuk flashdisk modern yang dipakai memindahkan file antara Windows, macOS, dan Linux, exFAT sering menjadi pilihan praktis. Namun, jika flashdisk digunakan untuk perangkat lama, FAT32 bisa lebih kompatibel.

## 4. Apa yang terjadi saat kita memformat flashdisk?

Misalnya flashdisk 64 GB ingin diformat menjadi exFAT.

Secara sederhana, prosesnya seperti ini:

1. Sistem memilih volume atau partisi target.
2. Filesystem baru dibuat pada volume tersebut.
3. Struktur metadata filesystem disiapkan.
4. Sistem operasi kemudian dapat menyimpan file menggunakan struktur baru itu.

Format biasa tidak selalu menghapus setiap sektor secara fisik. Karena itu, format bukan metode yang dapat diandalkan untuk menghapus data secara aman.

Jika data penting masih ada di flashdisk, cadangkan dahulu sebelum memformat.

## 5. Apa itu Allocation Unit Size?

Selain filesystem, Windows terkadang menampilkan pilihan Allocation Unit Size atau ukuran unit alokasi.

Ini adalah ukuran blok yang digunakan filesystem untuk mengalokasikan ruang bagi file.

Contohnya:

- 4 KiB
- 8 KiB
- 16 KiB
- 32 KiB
- 64 KiB

Ukuran yang lebih besar dapat meningkatkan efisiensi pada pola file besar tertentu, tetapi bisa membuang lebih banyak ruang untuk banyak file kecil. Ukuran yang lebih kecil dapat mengurangi pemborosan ruang pada file kecil, tetapi hasil akhirnya bergantung pada workload.

Untuk flashdisk biasa, pilihan Default allocation size umumnya merupakan pilihan yang aman.

## 6. Filesystem bukan partition scheme

Ini juga penting karena keduanya sering muncul saat membuat USB bootable.

| Istilah          | Contoh                   | Fungsi                                          |
| ---------------- | ------------------------ | ----------------------------------------------- |
| Filesystem       | FAT32, exFAT, NTFS, ext4 | Mengatur file di dalam volume                   |
| Partition scheme | GPT, MBR                 | Menentukan bagaimana partisi dicatat pada disk  |
| Boot mode        | UEFI, Legacy BIOS        | Menentukan cara firmware memulai sistem operasi |

Misalnya, sebuah flashdisk bootable dapat menggunakan tabel partisi GPT dan mempunyai partisi FAT32 untuk file boot. GPT bukan pengganti FAT32 karena fungsinya berbeda.


## 8. Ringkasan atau catatan tambahan dari saya

- FAT32: kompatibilitas luas, tetapi satu file dibatasi kurang dari 4 GiB.
- exFAT: pilihan praktis untuk flashdisk modern dan file besar lintas perangkat.
- NTFS: filesystem utama Windows dengan fitur pengelolaan data lebih lengkap.
- ext4: pilihan umum untuk Linux.
- Btrfs: filesystem Linux dengan snapshot, checksum, dan fitur lanjutan.
- XFS: banyak digunakan pada server dan storage besar.
- ZFS: pengelolaan pool storage dengan fitur integritas dan snapshot.
- APFS: filesystem modern untuk ekosistem Apple.
- FAT12/FAT16, HFS+, ISO 9660, UDF, ReFS, SquashFS, F2FS, tmpfs, dan OverlayFS: digunakan untuk kebutuhan khusus atau generasi sistem tertentu.

