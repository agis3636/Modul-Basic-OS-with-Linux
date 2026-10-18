# Troubleshooting Keyboard Internal Axioo MyBook Hype 5 AMD di Linux

## 1. Gejala masalah

- Keyboard internal berfungsi di BIOS dan GRUB, tetapi tidak berfungsi setelah Linux berjalan.
- Masalah terjadi pada beberapa distro/kernel Linux.
- Keyboard USB eksternal tetap berfungsi.
- Log kernel menunjukkan kegagalan pada driver `i8042` dan `atkbd`.

## 2. Diagnosis awal

Periksa pesan error keyboard:

```
sudo journalctl -k -b | grep -Ei 'i8042|atkbd|serio|keyboard'
```

Fungsi perintah: menampilkan log kernel terkait keyboard untuk mengetahui apakah ada kegagalan inisialisasi perangkat.

## 3. Solusi yang berhasil

Kasus Axioo MyBook Hype 5 AMD: menambahkan parameter `pnpacpi=off` membuat keyboard internal kembali berfungsi.

### Langkah 1 — Edit konfigurasi GRUB

```
sudo nano /etc/default/grub
```

Cari baris:

```
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"
```

Ubah menjadi:

```
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash i8042.reset i8042.nomux=1 i8042.nopnp=1 atkbd.reset pnpacpi=off"
```

Catatan: jika baris awal memiliki parameter tambahan, pertahankan parameter tersebut dan tambahkan parameter di atas.

### Langkah 2 — Simpan konfigurasi

Di Nano:

- `Ctrl + O` → simpan.
- `Enter` → konfirmasi nama file.
- `Ctrl + X` → keluar.

### Langkah 3 — Terapkan konfigurasi dan restart

```
sudo update-grub
sudo reboot
```

Fungsi:

- `update-grub`: membuat ulang konfigurasi GRUB berdasarkan pengaturan yang tersimpan.
- `reboot`: memulai ulang laptop agar parameter diterapkan saat boot.

### Langkah 4 — Verifikasi

```
cat /proc/cmdline
```

Pastikan parameter `pnpacpi=off` dan parameter lainnya tercantum.

Kemudian tes keyboard internal.

## 4. Fungsi parameter

| Parameter       | Tujuan                                                               |
| --------------- | -------------------------------------------------------------------- |
| `i8042.reset`   | Meminta reset controller i8042.                                      |
| `i8042.nomux=1` | Menonaktifkan deteksi multiplexing pada controller i8042.            |
| `i8042.nopnp=1` | Menonaktifkan deteksi PNP untuk controller i8042.                    |
| `atkbd.reset`   | Meminta reset perangkat keyboard AT.                                 |
| `pnpacpi=off`   | Menonaktifkan dukungan ACPI untuk enumerasi perangkat Plug and Play. |

## 5. Catatan penting

- Konfigurasi ini permanen sampai diubah kembali.
- Parameter akan diterapkan ke kernel baru selama tetap tercantum dalam konfigurasi GRUB.
- Setelah update kernel, uji kembali keyboard, touchpad, brightness, Wi-Fi, audio, dan suspend.
- `pnpacpi=off` dapat memengaruhi perangkat lain. Jika timbul masalah, hapus parameter tersebut dari konfigurasi GRUB, jalankan `sudo update-grub`, lalu restart.

Hasil kasus: keyboard internal Axioo MyBook Hype 5 AMD berfungsi setelah parameter `pnpacpi=off` ditambahkan bersama parameter i8042 dan atkbd di atas.
