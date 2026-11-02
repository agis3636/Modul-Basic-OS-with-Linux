Kalau mahasiswa menggunakan **Ubuntu Server 22.04 atau 24.04**, keduanya bisa dipasangi GNOME tanpa instal ulang OS. Ubuntu menyediakan paket desktop yang dapat dipasang melalui APT. ![Ubuntu Wiki](https://wiki.ubuntu.com/Install_a_desktop_environment_on_Ubuntu_Server?utm_source=chatgpt.com)

## Ubuntu Server 22.04 dan 24.04

Gunakan langkah yang sama untuk kedua versi.

**1. Perbarui daftar paket**

```bash
sudo apt update
```

**2. Install GNOME Desktop Ubuntu**

```bash
sudo apt install ubuntu-desktop
```

Paket `ubuntu-desktop` memasang lingkungan desktop Ubuntu berbasis GNOME beserta komponen yang diperlukan.

**3. Tunggu instalasi selesai**

Jika muncul pilihan display manager, pilih `gdm3` agar menggunakan display manager GNOME.

**4. Restart**

```bash
sudo reboot
```

Setelah restart, seharusnya muncul layar login grafis, lalu mahasiswa bisa masuk ke desktop GNOME.

### Perbandingan

| | Ubuntu Server 22.04 | Ubuntu Server 24.04 |
|---|---|---|
| Perintah instalasi | `sudo apt install ubuntu-desktop` | `sudo apt install ubuntu-desktop` |
| Desktop | GNOME | GNOME |
| Perlu instal ulang? | Tidak | Tidak |
| Kebutuhan storage | Bertambah | Bertambah |

Ubuntu 22.04 menggunakan GNOME 42, sedangkan Ubuntu 24.04 menggunakan GNOME 46. Jadi tampilannya tidak sepenuhnya identik, tetapi keduanya menggunakan lingkungan desktop GNOME. ![Ubuntu Documentation](https://documentation.ubuntu.com/release-notes/22.04/?utm_source=chatgpt.com)

**Catatan:** Sebaiknya cek ruang penyimpanan sebelum instalasi karena `ubuntu-desktop` akan memasang cukup banyak paket tambahan.

```bash
df -h /
```

Kalau laptop mahasiswa tersebut hanya dipakai untuk belajar Linux dan praktikum, instalasi ini memungkinkan dia tetap menggunakan OS yang sudah ada sambil mendapatkan GUI.
