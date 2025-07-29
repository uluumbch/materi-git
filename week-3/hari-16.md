# Hari 16: Menggabungkan Branch (`merge`)

## Materi

Setelah selesai mengerjakan sebuah fitur di branch terpisah, langkah selanjutnya adalah menggabungkan (merge) pekerjaan tersebut kembali ke branch utama (`main`).

- **Konsep `git merge`**: Perintah ini mengambil perubahan dari satu branch dan mengintegrasikannya ke dalam branch lain. Anda harus berada di branch **tujuan** (misalnya `main`) saat menjalankan perintah `git merge <branch-sumber>`.

- **Jenis-jenis Merge**:
    - **Fast-forward**: Ini terjadi jika branch `main` tidak memiliki commit baru sejak `branch-fitur` dibuat. Git hanya perlu memindahkan penunjuk (pointer) `main` ke depan agar sama dengan `branch-fitur`. Ini adalah merge yang paling sederhana dan bersih.
    - **Three-way Merge**: Ini terjadi jika `main` juga memiliki commit baru. Git harus melihat tiga titik: commit terakhir di `main`, commit terakhir di `branch-fitur`, dan *commit leluhur bersama* (common ancestor) terakhir mereka. Git lalu membuat sebuah **"merge commit"** baru yang menggabungkan kedua riwayat tersebut.

## Praktik

1.  **Pastikan di Branch Tujuan**: Pindah ke branch `main`, karena kita ingin menggabungkan pekerjaan dari `fitur-profil` **ke dalam** `main`.
    ```bash
    git switch main
    ```

2.  **Jalankan Merge**: Sekarang, jalankan perintah `merge` dengan nama branch sumber sebagai argumen.
    ```bash
    git merge fitur-profil
    ```
    Anda kemungkinan besar akan melihat pesan yang menyebutkan "Fast-forward", karena `main` belum berubah sejak Anda membuat branch `fitur-profil`.

3.  **Verifikasi Hasil Merge**:
    - Jalankan `ls` (Mac/Linux) atau `dir` (Windows). File `profil.txt` sekarang seharusnya sudah ada di branch `main`.
    - Jalankan `git log`. Anda akan melihat commit dari branch `fitur-profil` sekarang menjadi bagian dari riwayat `main`.

4.  **Update Remote**: Repositori remote (GitHub) Anda belum tahu tentang perubahan ini. Push branch `main` yang sudah diperbarui.
    ```bash
    git push origin main
    ```

5.  **Cek di GitHub**: Buka halaman repositori Anda di GitHub. File `profil.txt` sekarang seharusnya sudah muncul di sana.

---
*Anda berhasil menggabungkan pekerjaan! Besok kita akan mempraktikkan alur kerja fitur lengkap dari awal hingga akhir.*