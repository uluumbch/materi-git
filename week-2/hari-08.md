# Hari 08: Menghubungkan Lokal ke Remote (`remote` & `push`)

## Materi

Selamat datang di Minggu ke-2! Sekarang kita akan menghubungkan hasil kerja keras kita di komputer (lokal) ke internet (remote) menggunakan GitHub.

- **Konsep `remote`**: Sebuah `remote` adalah sebutan untuk repositori Git yang sama, tetapi lokasinya ada di tempat lain (biasanya di server online seperti GitHub). Repositori di komputer Anda disebut **`local`**, sedangkan yang di GitHub disebut **`remote`**.

- **Perintah `git remote add`**: Perintah ini digunakan untuk "memberi tahu" repositori lokal Anda tentang alamat repositori remote. Kita biasanya menamai remote utama kita **`origin`**. Jadi, `git remote add origin <URL>` berarti: "Hai Git, tambahkan sebuah remote bernama `origin` yang alamatnya ada di `<URL>` ini."

- **Perintah `git push`**: Setelah lokal dan remote terhubung, `git push` adalah perintah untuk **mengunggah (upload)** semua *commit* yang sudah Anda buat di lokal ke remote. Flag `-u origin main` digunakan pada push pertama untuk mengatur agar branch `main` lokal Anda terhubung secara otomatis dengan branch `main` di `origin`.

## Praktik

1.  **Buat Repositori di GitHub**: Buka situs [GitHub](https://github.com), login, dan buat sebuah repositori baru. Beri nama yang sama dengan folder lokal Anda (`30-hari-git-github-NAMA_ANDA`). **Penting**: Jangan centang opsi untuk menambahkan `README`, `.gitignore`, atau `license` saat membuat repo. Kita ingin membuat repositori kosong.

2.  **Hubungkan Lokal ke Remote**: GitHub akan memberikan Anda beberapa perintah setelah repositori dibuat. Kita akan menggunakan opsi "...or push an existing repository from the command line".
    - Salin perintah `git remote add origin ...` yang diberikan oleh GitHub. URL di dalamnya akan menunjuk ke repositori baru Anda.
    - Jalankan perintah tersebut di terminal, di dalam folder proyek lokal Anda.
    ```bash
    git remote add origin https://github.com/USERNAME_ANDA/NAMA_REPO_ANDA.git
    ```

3.  **Push Commit Anda**: Sekarang, unggah semua pekerjaan dari Minggu 1 ke GitHub dengan perintah berikut.
    > Catatan: Nama branch utama default bisa `main` atau `master` tergantung konfigurasi Git Anda. Cek nama branch Anda dengan perintah `git branch`. Sesuaikan perintah di bawah jika nama branch Anda adalah `master`.
    ```bash
    git push -u origin main
    ```

4.  **Verifikasi**: Buka kembali halaman repositori Anda di GitHub dan segarkan (refresh). Semua file (`hari-01.txt`, `resep_nasi_goreng.txt`, dll.) dan riwayat commit Anda dari Minggu 1 sekarang seharusnya sudah muncul di sana. Ini adalah momen pembuktian! 🎉

---
*Kerja bagus! Repositori Anda sekarang online. Besok kita akan belajar cara mengambil proyek dari remote.*