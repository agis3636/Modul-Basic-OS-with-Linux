BIOS (Basic Input/Output System) adalah firmware pada motherboard yang bertugas menginisialisasi perangkat keras dan memulai proses booting komputer sebelum sistem operasi seperti Windows atau Linux berjalan.

## Fungsi BIOS

![BIOS Firmware: How it works with CMOS, MBR, VBR & Bootloader | by Meerthika SR | Medium](https://images.openai.com/static-rsc-4/mDM40LxNYygXM2P7ZJdOKUl6aarQo2y969YXwSDCBrU0Uxt2aFPX9sw_Q6588ZSlJqKd9ALakezvnbSTB3gBMt50off6ttf1cNNQl-vRCk3_1_3Z_Ie9GdsuhYGlLQNQgjCPB-vOB6bWOhXyjPjpUwFYqaShhBo3pfH_t2XDEfc?purpose=inline)

1\. Mendeteksi perangkat keras

Memeriksa CPU, RAM, keyboard, storage (HDD/SSD), dan perangkat lain ketika komputer dinyalakan.

![Как запустить установку Windows с флешки через BIOS и Boot Menu - Интернет-магазин Softnet.Su](https://images.openai.com/static-rsc-4/-tivtRL3gCwVhB_a6qKZAqnxCHwhXAqAhyB_YSr78C-RZT-bENEXa59v6rT7OQlfvNJPs0zk9TpYIAgwPfigyV3HMnqfyY8oPkRBM7vuHLV-5946c6ZwTI55JM3xoM-3rvAF53byzaFSeieW_OmnZ8MT-CwmpuAMyJKuxC5xUXY?purpose=inline)

2\. Mengatur konfigurasi komputer

Mengatur urutan boot, tanggal dan waktu, serta konfigurasi perangkat keras. Pada BIOS/UEFI tertentu, tersedia juga pengaturan virtualisasi seperti Intel VT-x atau AMD-V.

![\[SOLVED\] - BIOS identifies DRAM, but does not use it | Tom's Hardware Forum](https://images.openai.com/static-rsc-4/rxstG8CF538hGfxkp__2FgdWfPCgxBkdWVIIjUqmwOi5WgnreDEbMOofj_vwXDyucmRHzGEDNWxwqoQOVx0hKn4l36mqP_ZMBCPOzY9ebKg31AGPVF_UdH5DYcl_GOuOCsRB9SQIn8zZF5-T2H6e0rJMr_nEh4oHH7feCDyrWvs?purpose=inline)

3\. Menjalankan POST

POST (Power-On Self-Test) adalah pemeriksaan awal untuk mengetahui apakah komponen penting berfungsi.

![Windows Boot Process: From Power On to Desktop | Hamza Ishaq posted on the topic | LinkedIn](https://images.openai.com/static-rsc-4/EJMqkHSHbhRatm4Sx9C70_3rUCGTYQWuxZGw6okMTGuUOsYUpGLenGrTNPTO8DzRsCvzK8ngR314Os_F58c46nG3MlKndTh5c7KnUAEpRJT4BWpvLn3TXM5zL3qhHpGHI4kWYSBiljFrQ_Tyx0uE1F7wrIA_lMr0EVgGxk6GZDc?purpose=inline)

4\. Memulai sistem operasi

BIOS mencari perangkat boot dan menjalankan proses untuk memuat sistem operasi.

## Bagaimana BIOS bekerja?

Urutannya seperti ini:

<img width="931" height="557" alt="Image" src="https://github.com/user-attachments/assets/0474b980-e452-424d-aa4e-a6886fd447c8" />

Analogi sederhananya: BIOS seperti petugas yang memeriksa kesiapan sebuah gedung sebelum gedung dibuka. Kalau perangkat penting tidak siap, proses booting bisa gagal.

## Perbedaan BIOS dan UEFI

| Aspek               | BIOS Legacy                                    | UEFI                                          |
| ------------------- | ---------------------------------------------- | --------------------------------------------- |
| Generasi            | Lebih lama                                     | Lebih modern                                  |
| Kapasitas boot disk | Umumnya menggunakan MBR, terbatas sekitar 2 TB | Mendukung GPT dan disk berkapasitas besar     |
| Antarmuka           | Umumnya berbasis teks                          | Bisa berbasis grafis dan mendukung mouse      |
| Secure Boot         | Tidak tersedia secara standar                  | Mendukung Secure Boot                         |
| Kecepatan boot      | Bergantung perangkat dan konfigurasi           | Umumnya lebih fleksibel dan dapat lebih cepat |

Komputer modern umumnya menggunakan UEFI. Istilah “masuk BIOS” tetap sering dipakai meskipun sebenarnya yang dibuka adalah menu UEFI.

## Kapan BIOS penting untuk IT?

- Instalasi Ubuntu Server: menentukan boot dari USB atau ISO.
- Virtualisasi Proxmox/VirtualBox: mengaktifkan Intel VT-x atau AMD-V jika diperlukan.
- Troubleshooting: memeriksa apakah RAM atau SSD terdeteksi.
- Konfigurasi server: menentukan boot order, Secure Boot, dan pengaturan perangkat keras.

Intinya: BIOS/UEFI adalah firmware dasar yang mempersiapkan perangkat keras dan memulai sistem operasi. Tanpanya, komputer modern pada umumnya tidak dapat menjalankan proses boot normal.
