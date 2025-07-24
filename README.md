# 🚀 Kali Linux Win-KeX Setup on WSL2 (Windows Subsystem for Linux)

Panduan ini membantu kamu untuk mengaktifkan **Win-KeX (GUI Desktop Kali)** di dalam **WSL2** secara optimal. Cocok untuk pengguna yang ingin mengakses tampilan desktop Kali langsung dari Windows tanpa VM berat.

<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/42fafee9-df30-4cee-8c5c-47dc9dd73daa" />

---

## 🧱 Prasyarat

- Windows 10/11 dengan WSL2 aktif.
- Sudah menginstal Kali Linux dari Microsoft Store atau melalui CLI.

---

## 🔧 Instalasi Win-KeX

```bash
sudo apt update && sudo apt install -y kali-win-kex
````

---

## 🚀 Jalankan Win-KeX (mode window)

```bash
kex --win -s
```

Jika berhasil, maka akan muncul GUI Kali dalam window terpisah.

---

## ⚙️ Autostart KeX saat buka terminal

Edit file `.profile`:

```bash
nano ~/.profile
```

Tambahkan baris berikut di paling bawah:

```bash
kex --win -s
```

> Ini akan otomatis membuka Win-KeX setiap kali kamu masuk ke sesi WSL.

---

## 🧠 Optimasi Performa WSL

Edit konfigurasi `.wslconfig` di Windows:

```ini
# File: C:\Users\<namamu>\.wslconfig
[wsl2]
memory=4GB
processors=2
swap=0
localhostForwarding=true
```

> Sesuaikan `memory` dan `processors` dengan spesifikasi komputermu, jangan sampai melebihi.

Setelah itu, jalankan:

```powershell
wsl --shutdown
```

Untuk menerapkan konfigurasi baru.

---

## 🧪 (Opsional) Install Driver GUI dan Tes OpenGL

Install driver dan tools OpenGL:

```bash
sudo apt install -y mesa-utils
```

Cek apakah driver aktif:

```bash
glxinfo | grep "OpenGL renderer"
```

Jika muncul info renderer (bukan "llvmpipe"), maka GPU rendering sudah aktif.

---

## ✅ Selesai

Sekarang kamu bisa menikmati desktop environment Kali Linux langsung dari WSL2 dengan performa lebih ringan dan cepat 🚀.

---

## 📎 Catatan Tambahan

* Untuk mode fullscreen gunakan: `kex --sl --wtstart -s`
* Jika terjadi error saat jalankan `kex`, coba jalankan: `kex --stop` lalu ulangi `kex --win -s`

