# Hari 22: Merapikan Sejarah (`rebase -i`)

## Materi

Selamat datang di minggu terakhir! Kita akan mempelajari teknik-teknik canggih untuk membuat alur kerja Anda lebih bersih dan profesional.

- **Mengapa Merapikan Sejarah?**: Saat mengerjakan sebuah fitur, Anda mungkin membuat banyak sekali commit kecil seperti "coba perbaiki bug", "typo fix", "lupa koma", dll. Riwayat commit seperti ini terlihat "berantakan". Sebelum menggabungkan fitur Anda ke branch `main`, alangkah baiknya jika semua commit kecil itu digabungkan menjadi satu commit yang rapi dan deskriptif. Proses ini disebut **Squash**.

- **`git rebase -i` (Interactive Rebase)**: Ini adalah perintah sakti untuk menulis ulang sejarah commit. Salah satu kegunaan utamanya adalah untuk melakukan *squash*. Anda memberitahu Git, "Saya ingin mengedit beberapa commit terakhir saya". Git lalu akan membuka editor teks yang memungkinkan Anda memilih tindakan untuk setiap commit (menggabungkannya, mengedit pesannya, menghapusnya, dll).

> **Peringatan Keras**: Jangan pernah menggunakan `rebase` pada branch yang sudah di-`push` dan digunakan oleh orang lain (seperti `main`). `Rebase` menulis ulang sejarah, yang bisa menyebabkan masalah besar bagi kolaborator Anda. Gunakan hanya pada branch fitur lokal Anda **sebelum** di-merge.

## Praktik

1.  **Buat Branch Baru**: Dari `main`, buat branch baru.
    ```bash
    git switch -c fitur-cerita
    ```

2.  **Buat Beberapa Commit "Berantakan"**:
    - Buat file `cerita.txt` dan tulis paragraf pertama.
    - Lakukan `add` dan `commit` dengan pesan: `"feat: Menulis paragraf 1"`
    - Sadari ada typo, perbaiki, lalu `add` dan `commit` lagi dengan pesan: `"fix: Typo fix paragraf 1"`
    - Tambahkan paragraf kedua, lalu `add` dan `commit` lagi dengan pesan: `"feat: Menambahkan paragraf 2"`

3.  **Lihat Riwayat**: Jalankan `git log --oneline`. Anda akan melihat 3 commit terpisah.

4.  **Jalankan Interactive Rebase**: Kita ingin menggabungkan 3 commit terakhir. Jalankan:
    ```bash
    git rebase -i HEAD~3
    ```

5.  **Edit Instruksi Rebase**: Sebuah editor teks akan terbuka. Anda akan melihat daftar 3 commit Anda, diawali dengan kata `pick`.
    ```
    pick 1a2b3c feat: Menulis paragraf 1
    pick 4d5e6f fix: Typo fix paragraf 1
    pick 7g8h9i feat: Menambahkan paragraf 2
    ```
    - Biarkan baris pertama tetap `pick`.
    - Ubah `pick` pada baris kedua dan ketiga menjadi `s` (artinya `squash`).
      ```
      pick 1a2b3c feat: Menulis paragraf 1
      s 4d5e6f fix: Typo fix paragraf 1
      s 7g8h9i feat: Menambahkan paragraf 2
      ```
    - Simpan dan tutup editor.

6.  **Tulis Pesan Commit Baru**: Editor lain akan terbuka. Git meminta Anda menulis satu pesan commit baru untuk menggantikan ketiga commit tadi. Hapus semua teks yang ada dan tulis pesan yang bersih:
    ```
    feat: Menyelesaikan fitur cerita dengan dua paragraf
    ```
    - Simpan dan tutup editor.

7.  **Verifikasi**: Jalankan `git log --oneline` lagi. Ketiga commit tadi sekarang sudah menjadi satu commit yang rapi.

8.  **Gabungkan ke `main`**: Ikuti alur kerja standar: `switch` ke `main`, `merge`, `delete branch`, dan `push`.

---
*Sekarang riwayat commit Anda terlihat jauh lebih profesional! Besok kita akan belajar cara "mencuri" commit dari branch lain.*