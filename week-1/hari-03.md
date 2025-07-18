# Hari 03: Siklus Kerja Inti (`add` & `commit`)

## Materi

Siklus kerja dasar di Git terdiri dari tiga area: *Working Directory*, *Staging Area*, dan *Repository*.

1.  **Working Directory**: Folder proyek Anda tempat Anda membuat, mengedit, dan menghapus file. Ini adalah area kerja Anda.
2.  **Staging Area**: Bayangkan ini sebagai "keranjang belanja". Sebelum Anda "membayar" (menyimpan perubahan secara permanen), Anda harus memasukkan file-file yang ingin Anda simpan ke dalam keranjang ini. Perintahnya adalah `git add`. Ini memungkinkan Anda memilih perubahan mana saja yang ingin disertakan dalam simpanan berikutnya.
3.  **Repository**: Ini adalah "gudang" tempat Git menyimpan semua versi proyek Anda secara permanen. Setelah Anda puas dengan isi "keranjang belanja", Anda "membayarnya" dengan perintah `git commit`.

Alurnya: **Modifikasi file -> `git add` (masuk ke Staging) -> `git commit` (simpan permanen ke Repository)**.

Pesan *commit* sangat penting; tulislah pesan yang jelas dan deskriptif agar Anda (dan orang lain) tahu perubahan apa yang terjadi di commit tersebut.

## Praktik

1.  Di dalam terminal, tambahkan semua file yang sudah Anda buat sejauh ini (`hari-01.txt` dari hari pertama dan `hari-02.txt` dari hari kedua) ke *Staging Area*. Anda bisa melakukannya dengan perintah:
    ```bash
    git add hari-01.txt hari-02.txt
    ```
    Atau, untuk menambahkan semua file yang berubah sekaligus (tanda titik `.` berarti "semua yang ada di folder ini"):
    ```bash
    git add .
    ```
2.  Sekarang, lakukan *commit* pertama Anda. Ini akan menyimpan semua file yang ada di Staging Area secara permanen ke dalam riwayat Git. Gunakan *flag* `-m` untuk menuliskan pesan commit langsung dari terminal. Jalankan perintah ini:
    ```bash
    git commit -m "Commit pertama: Inisialisasi proyek dan tugas hari 1 & 2"
    ```
Selamat! Anda baru saja menyelesaikan siklus kerja Git yang paling fundamental.

---
*Materi hari ini selesai. Besok kita akan belajar cara memeriksa status dan melihat riwayat pekerjaan kita.*