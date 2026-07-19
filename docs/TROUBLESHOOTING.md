# 🛠 JawaBridge Troubleshooting Guide

Panduan ini membantu mengatasi masalah umum saat menggunakan JawaBridge.

---

# Wine Not Found

## Error

Jika muncul:

```text
wine: command not found
```

atau:

```text
Wine is not installed
```

berarti Wine belum terpasang di sistem kamu.

JawaBridge membutuhkan Wine untuk menjalankan aplikasi Windows (.exe).

---

# Install Wine Berdasarkan Distro

## Debian / Ubuntu / Linux Mint / Pop!_OS

Update repository:

```bash
sudo apt update
```

Install Wine:

```bash
sudo apt install wine wine64 wine32
```

Cek instalasi:

```bash
wine --version
```

---

## Arch Linux / Manjaro / EndeavourOS

Aktifkan repository multilib terlebih dahulu.

Edit file:

```bash
sudo nano /etc/pacman.conf
```

Cari:

```ini
#[multilib]
#Include = /etc/pacman.d/mirrorlist
```

Ubah menjadi:

```ini
[multilib]
Include = /etc/pacman.d/mirrorlist
```

Update sistem:

```bash
sudo pacman -Syu
```

Install Wine:

```bash
sudo pacman -S wine wine-mono wine-gecko winetricks
```

Cek:

```bash
wine --version
```

---

## Fedora

Install Wine:

```bash
sudo dnf install wine
```

Cek:

```bash
wine --version
```

---

## openSUSE

Install Wine:

```bash
sudo zypper install wine
```

Cek:

```bash
wine --version
```

---

## Gentoo

Install Wine:

```bash
sudo emerge wine
```

Cek:

```bash
wine --version
```

---

# Setup Wine Pertama Kali

Setelah Wine berhasil diinstall, jalankan:

```bash
winecfg
```

Tunggu sampai konfigurasi selesai.

Tes Wine:

```bash
wine notepad
```

Jika Windows Notepad muncul, Wine sudah berhasil.

---

# EXE Tidak Bisa Dibuka

Jika aplikasi Windows tidak berjalan:

Coba jalankan manual:

```bash
wine nama-aplikasi.exe
```

Periksa:

- File `.exe` tidak rusak
- Wine sudah terinstall
- Aplikasi kompatibel dengan Wine

---

# Shortcut Desktop Tidak Bisa Dibuka

Jika shortcut yang dibuat JawaBridge tidak berjalan:

Berikan izin:

```bash
chmod +x ~/Desktop/NamaAplikasi.desktop
```

Kemudian klik kanan shortcut:

```text
Allow Launching
```

---

# AppImage Tidak Bisa Dibuka

Jika muncul:

```text
Permission denied
```

Berikan izin:

```bash
chmod +x JawaBridge-x86_64.AppImage
```

Jalankan:

```bash
./JawaBridge-x86_64.AppImage
```

---

# EXE Architecture Tidak Terdeteksi

Pastikan file yang dipilih adalah:

```text
.exe
```

Bukan:

```text
.zip
.rar
.msi
```

Gunakan file EXE asli.

---

# JawaBridge Tidak Bisa Start

Jalankan melalui terminal untuk melihat error:

```bash
./JawaBridge
```

atau:

```bash
python3 main.py
```

Simpan pesan error yang muncul.

---

# Bug Report

Sebelum membuat laporan bug, siapkan informasi berikut:

## Informasi Sistem

Linux Distribution:

Contoh:
- Debian 13
- Arch Linux
- Ubuntu 24.04

Desktop Environment:

Contoh:
- KDE Plasma
- GNOME
- XFCE

JawaBridge Version:

```text
v1.0.0
```

Wine Version:

```bash
wine --version
```

---

# Cara Membuat Bug Report

Sertakan:

1. Deskripsi masalah
2. Langkah untuk membuat error terjadi
3. Pesan error dari terminal
4. Screenshot jika tersedia

---

# Masih Mengalami Masalah?

Jangan menghapus pesan error.

Log error membantu developer memperbaiki JawaBridge dan meningkatkan kompatibilitas aplikasi.

Terima kasih telah membantu pengembangan JawaBridge.
