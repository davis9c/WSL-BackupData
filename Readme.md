# 📦 Panduan Backup dan Restore WSL (Windows Subsystem for Linux)

Panduan ini berisi langkah-langkah untuk membackup dan me-restore distribusi WSL (WSL 1 maupun WSL 2) di Windows.

---

## ✅ Tujuan Backup

Backup ini mencakup:
- File sistem Linux
- File pengguna (home directory)
- Aplikasi dan konfigurasi di dalam WSL

---

## 🧰 Prasyarat

- Windows 10 atau 11 dengan WSL sudah diinstal
- Terminal dengan akses Administrator (PowerShell atau CMD)
- Mengetahui nama distribusi WSL

---

## 🔍 Cek Distribusi WSL

Jalankan perintah berikut di PowerShell:

```powershell
wsl --list --verbose
