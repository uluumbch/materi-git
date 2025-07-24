# Hari 10: Sinkronisasi Perubahan (`pull`)

## Materi

- **Alur Kerja Kolaborasi**: Saat bekerja dengan repositori remote (terutama dalam tim), alur kerja yang benar adalah **`PULL` sebelum `PUSH`**. Artinya, sebelum Anda mengunggah perubahan Anda, selalu unduh dulu perubahan terbaru dari remote.

- **Mengapa Ini Penting?**: Bayangkan seorang teman membuat perubahan di remote. Jika Anda tidak mengunduhnya terlebih dahulu (dengan `git pull`) dan langsung `push` pekerjaan Anda, Git akan menolak `push` Anda karena riwayat lokal dan remote Anda tidak sinkron. Ini adalah mekanisme keamanan Git untuk mencegah Anda menimpa pekerjaan orang lain secara tidak sengaja. `git pull` akan menggabungkan perubahan dari remote ke dalam versi lokal Anda.

## Praktik

Kita akan mensimulasikan perubahan yang dibuat oleh "orang lain" dengan mengedit file langsung di GitHub.

1.  **Buat Perubahan di GitHub**:
    - Buka halaman repositori Anda di GitHub.
    - Cari dan klik salah satu file, misalnya `resep_nasi_goreng.txt`.
    - Klik ikon pensil (Edit this file).
    - Tambahkan satu baris teks di mana saja, misalnya: `Catatan: Tambahkan irisan timun agar lebih segar.`
    - Scroll ke bawah, tulis pesan commit (misalnya "docs: Menambahkan catatan pada resep"), lalu klik tombol "Commit changes".

2.  **Kembali ke Folder Proyek Asli**: Buka terminal dan pastikan Anda berada di folder proyek **pertama** Anda (bukan yang hasil kloning kemarin).
    ```bash
    # Arahkan terminal ke folder 30-hari-git-github-NAMA_ANDA yang pertama
    ```

3.  **Tarik Perubahan dari Remote**: Jalankan perintah `git pull` untuk mengunduh perubahan yang baru saja Anda buat di web.
    ```bash
    git pull
    ```
    Anda akan melihat output yang memberitahu Anda bahwa file `resep_nasi_goreng.txt` telah diperbarui. Cek isi file tersebut di komputer Anda untuk memastikannya.

4.  **Buat File Konfirmasi**:
    - Buat file baru bernama `hari-10.txt`.
    - Isi dengan teks: `"Pull berhasil, perubahan dari web sudah masuk ke lokal."`

5.  **Simpan dan Unggah**: Lakukan siklus `add`, `commit`, dan `push` seperti biasa untuk menyimpan pekerjaan Anda.
    ```bash
    git add hari-10.txt
    git commit -m "feat: Menambahkan file konfirmasi pull"
    git push
    ```

---
*Sekarang Anda tahu cara menjaga repositori lokal Anda tetap sinkron. Besok kita akan belajar cara mengabaikan file tertentu.*