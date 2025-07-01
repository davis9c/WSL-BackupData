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
```

Contoh output:

```
  NAME            STATE           VERSION
* Ubuntu-22.04    Running         2
  Debian          Stopped         2
```

---

## 📦 Langkah Backup WSL

### 1. Tentukan Nama Distribusi

Lihat nama distribusi dari perintah sebelumnya, misalnya `Ubuntu-22.04`.

### 2. Jalankan Perintah Export

Gunakan perintah berikut di PowerShell sebagai Administrator:

```powershell
wsl --export <Nama-Distribusi> <Path\Tujuan\Backup.tar>
```

Contoh:

```powershell
wsl --export Ubuntu-22.04 D:\Backup\ubuntu-backup.tar
```

---

## 🔁 Restore Distribusi WSL

### 1. (Opsional) Hapus Distribusi Lama

Jika ingin menghapus distribusi lama:

```powershell
wsl --unregister <Nama-Distribusi>
```

> ⚠️ Semua data akan hilang jika unregister.

### 2. Import dari File Backup

```powershell
wsl --import <Nama-Baru> <Folder\Tujuan> <Path\Backup.tar>
```

Contoh:

```powershell
wsl --import Ubuntu-Restore D:\WSL\UbuntuRestored D:\Backup\ubuntu-backup.tar
```

---

## 📁 Backup File Pengguna Saja

Jika hanya ingin backup file di folder `home`, lakukan di dalam WSL:

```bash
cd ~
tar -czvf backup-home.tar.gz .
cp backup-home.tar.gz /mnt/c/Users/<NamaUserWindows>/Documents/
```

---

## ⏱️ Rekomendasi Jadwal Backup

- 🔄 Backup penuh: seminggu sekali
- 💾 Backup file penting: harian atau otomatis (dengan script)

---

## 💡 Tips Tambahan

- Pastikan selalu punya ruang cukup di drive tujuan backup.
- Gunakan nama backup yang mencantumkan tanggal untuk versiing, misalnya: `ubuntu-backup-2025-07-01.tar`

---

📝 Dibuat oleh: [Nama Anda]  
📅 Terakhir diperbarui: 1 Juli 2025
