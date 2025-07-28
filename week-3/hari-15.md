# Hari 15: Konsep & Membuat Branch (`branch` & `switch`)

## Materi

Selamat datang di Minggu ke-3! Kita akan mempelajari salah satu fitur Git yang paling kuat: **Branching**.

- **Apa itu `branch`?**: Bayangkan `branch` (cabang) sebagai sebuah "dunia paralel" dari proyek Anda. Branch utama bernama `main` (atau `master`) adalah dunia utama yang berisi kode stabil. Ketika Anda ingin mengerjakan fitur baru atau mencoba ide eksperimental, Anda membuat `branch` baru. Di dalam `branch` ini, Anda bisa bebas membuat perubahan, `commit`, bahkan membuat kesalahan, tanpa memengaruhi `branch` `main` yang stabil.

- **Kenapa Sangat Berguna?**: Branching memungkinkan banyak orang bekerja pada fitur yang berbeda secara bersamaan tanpa mengganggu pekerjaan satu sama lain. Ini adalah fondasi dari alur kerja pengembangan modern.

- **`HEAD`**: `HEAD` adalah penunjuk (pointer) yang menandakan di mana Anda berada saat ini di dalam repositori. Biasanya, `HEAD` menunjuk ke `branch` tempat Anda sedang bekerja (misalnya `main` atau `fitur-profil`).

- **Perintah Dasar**:
    - `git branch <nama-branch>`: Membuat sebuah branch baru.
    - `git switch <nama-branch>`: Berpindah (masuk) ke branch yang sudah ada.
    - `git switch -c <nama-branch>`: *Shortcut* untuk membuat branch baru dan langsung berpindah ke dalamnya.

## Praktik

1.  **Pastikan di Branch `main`**: Buka terminal di repositori pribadi Anda dan pastikan Anda berada di branch `main` dengan menjalankan `git status` atau `git branch`.

2.  **Buat Branch Baru**: Buat sebuah branch baru untuk mengerjakan fitur profil.
    ```bash
    git branch fitur-profil
    ```
    Jalankan `git branch` lagi untuk melihat daftar semua branch. Anda akan melihat `fitur-profil` ada di daftar, dan tanda `*` masih ada di `main`.

3.  **Pindah ke Branch Baru**: Masuk ke dalam branch `fitur-profil`.
    ```bash
    git switch fitur-profil
    ```
    Jalankan `git branch` lagi. Tanda `*` sekarang seharusnya berpindah ke `fitur-profil`, menandakan `HEAD` sudah menunjuk ke sana.

4.  **Kerjakan Fitur di Branch**:
    - Buat file baru bernama `profil.txt`.
    - Isi file tersebut dengan nama dan hobi Anda, misalnya: `Nama: Budi, Hobi: Membaca Buku`.
    - Lakukan `add` dan `commit` untuk perubahan ini. Pastikan Anda melakukannya **di dalam branch `fitur-profil`**.
      ```bash
      git add profil.txt
      git commit -m "feat: Menambahkan file profil dengan nama dan hobi"
      ```

5.  **Buktikan Isolasi Branch**: Sekarang, kembali ke branch utama.
    ```bash
    git switch main
    ```
    Gunakan perintah `ls` (Mac/Linux) atau `dir` (Windows) untuk melihat daftar file. Perhatikan bahwa file `profil.txt` **tidak ada** di branch `main`. Ini membuktikan bahwa pekerjaan Anda di `fitur-profil` terisolasi dan aman.

---
*Konsep yang luar biasa, bukan? Besok kita akan belajar cara menggabungkan pekerjaan dari branch fitur kembali ke branch utama.*