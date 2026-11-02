# Bedanya `update` dan `upgrade` di Linux

Pada Ubuntu/Debian yang menggunakan APT, keduanya berbeda fungsi.

| Perintah           | Fungsi                                                                  | Analogi                                             |
| ------------------ | ----------------------------------------------------------------------- | --------------------------------------------------- |
| `sudo apt update`  | Memperbarui daftar informasi paket dari repository                      | Mengecek katalog toko terbaru                       |
| `sudo apt upgrade` | Mengunduh dan memasang versi lebih baru dari paket yang sudah terinstal | Membeli dan mengganti barang lama dengan versi baru |

## Contoh nyata

Misalnya Node.js versi `18` sudah terpasang, sedangkan repository menyediakan versi paket `18.19.1`.

1\. Jalankan update

```
sudo apt update
```

APT memperbarui informasi repository. Versi Node.js yang terpasang belum berubah.

2\. Cek aplikasi yang punya update

```
apt list --upgradable
```

3\. Jalankan upgrade

```
sudo apt upgrade
```

APT akan memasang pembaruan paket yang bisa di-upgrade berdasarkan repository dan aturan dependensinya.

## Urutan yang benar

```
sudo apt update
sudo apt upgrade
```

Catatan penting:

- `apt upgrade` biasanya tidak menghapus paket yang sudah terpasang. Paket yang membutuhkan perubahan dependensi tertentu bisa ditahan.

- `sudo apt full-upgrade` dapat memasang atau menghapus paket untuk menyelesaikan perubahan dependensi, jadi periksa daftar perubahan sebelum menyetujuinya.&#x20;

- Kalau ingin berpindah versi besar Ubuntu, misalnya dari Ubuntu 22.04 ke 24.04, itu berbeda dari update paket biasa; gunakan mekanisme upgrade rilis seperti `do-release-upgrade`.&#x20;

Cara gampang mengingat: `update` = memperbarui katalog; `upgrade` = memperbarui aplikasi yang terpasang.
