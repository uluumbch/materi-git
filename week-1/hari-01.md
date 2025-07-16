# Hari 01: Instalasi & Konfigurasi Awal

## Materi

- **Apa itu Git?** Git adalah *Version Control System* (VCS) atau Sistem Pengontrol Versi. Bayangkan Git sebagai "mesin waktu" untuk folder proyek Anda. Ia merekam setiap perubahan yang Anda simpan (disebut *commit*), sehingga Anda bisa kembali ke versi mana pun di masa lalu. Ini sangat penting untuk melacak perkembangan, memperbaiki kesalahan, dan berkolaborasi dengan orang lain.

- **Instalasi:** Git perlu diinstal di komputer Anda. Prosesnya berbeda untuk setiap sistem operasi.
    - **Windows:** Unduh dari [git-scm.com](https://git-scm.com/download/win) dan ikuti proses instalasi. Pilih "Git Bash" saat instalasi.
    - **Mac:** Buka Terminal dan ketik `git --version`. Jika belum terinstal, akan muncul prompt untuk menginstalnya. Alternatif lain adalah menginstal via [Homebrew](https://brew.sh/) dengan `brew install git`.
    - **Linux:** Buka Terminal dan gunakan package manager distro Anda (misal: `sudo apt-get install git` untuk Debian/Ubuntu).

- **Konfigurasi Awal (`git config`):** Setelah instalasi, Anda harus "memperkenalkan diri" ke Git. Ini penting agar setiap perubahan yang Anda simpan memiliki identitas Anda. Dua konfigurasi paling penting adalah nama dan email.

## Praktik

1.  **Instal Git** di sistem operasi Anda sesuai panduan di atas.
2.  Buka **Terminal** (di Mac/Linux) atau **Git Bash** (di Windows).
3.  Lakukan konfigurasi dengan mengganti `"Nama Anda"` dan `"email@anda.com"` dengan data Anda. Jalankan dua perintah ini:
    ```bash
    git config --global user.name "Nama Anda"
    git config --global user.email "email@anda.com"
    ```
4.  Buat sebuah folder di komputer Anda dengan nama `30-hari-git-github-NAMA_ANDA`. Masuk ke folder tersebut melalui terminal.
5.  Buat file baru bernama `hari-01.txt`.
6.  Jalankan perintah berikut satu per satu di terminal, lalu salin (copy-paste) hasilnya ke dalam file `hari-01.txt`:
    ```bash
    git --version
    git config --list
    ```

> **Tantangan:** Saat ini, file `hari-01.txt` belum dilacak oleh Git (statusnya *untracked*). Biarkan seperti ini. Ini akan menjadi bahan pelajaran kita di Hari ke-3.

---
*Materi hari ini selesai. Sampai jumpa di materi Hari ke-2!*