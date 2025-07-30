# Hari 17: Alur Kerja Fitur Lengkap

## Materi

Hari ini kita akan menyatukan semua yang telah kita pelajari tentang branching ke dalam satu siklus kerja yang lengkap dan rapi. Ini adalah alur kerja yang sangat umum digunakan di industri.

**Siklus Lengkap Alur Kerja Fitur (Feature Branch Workflow):**

1.  Mulai dari branch `main` yang bersih dan ter-update (`git pull`).
2.  Buat branch baru untuk fitur yang akan dikerjakan (`git switch -c nama-fitur-baru`).
3.  Kerjakan fitur tersebut. Lakukan `add` dan `commit` sebanyak yang diperlukan di dalam branch fitur.
4.  Setelah fitur selesai, kembali ke branch `main` (`git switch main`).
5.  Pastikan `main` masih up-to-date (`git pull`).
6.  Gabungkan branch fitur ke `main` (`git merge nama-fitur-baru`).
7.  Hapus branch fitur yang sudah tidak diperlukan lagi untuk menjaga kebersihan repositori (`git branch -d nama-fitur-baru`).
8.  Push branch `main` yang sudah diperbarui ke remote (`git push`).

## Praktik

Mari kita terapkan alur kerja ini untuk menambahkan halaman portofolio sederhana.

1.  **Buat Branch Fitur**: Dari branch `main`, buat dan langsung pindah ke branch baru.
    ```bash
    git switch -c fitur-portofolio
    ```

2.  **Kerjakan Fitur**:
    - Buat file baru bernama `portofolio.html`.
    - Isi dengan struktur HTML dasar, misalnya:
      ```html
      <!DOCTYPE html>
      <html>
      <head>
          <title>Portofolio Saya</title>
      </head>
      <body>
          <h1>Selamat Datang di Portofolio Saya</h1>
          <p>Proyek-proyek saya akan ditampilkan di sini.</p>
      </body>
      </html>
      ```
    - Lakukan `add` dan `commit` untuk file ini di branch `fitur-portofolio`.
      ```bash
      git add portofolio.html
      git commit -m "feat: Menambahkan halaman portofolio dasar"
      ```

3.  **Kembali dan Merge**: Kembali ke `main` dan gabungkan pekerjaan Anda.
    ```bash
    git switch main
    git merge fitur-portofolio
    ```

4.  **Hapus Branch Fitur**: Branch `fitur-portofolio` sudah tidak diperlukan lagi karena pekerjaannya sudah masuk ke `main`. Hapus branch tersebut.
    ```bash
    git branch -d fitur-portofolio
    ```
    Flag `-d` (delete) aman digunakan karena hanya akan menghapus branch yang sudah di-merge.

5.  **Push ke GitHub**: Kirim hasilnya ke remote.
    ```bash
    git push origin main
    ```

---
*Alur kerja yang sangat rapi! Tapi, bagaimana jika saat me-merge terjadi masalah? Kita akan bahas itu besok.*