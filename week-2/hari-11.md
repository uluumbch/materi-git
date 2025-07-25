# Hari 11: Mengabaikan File (`.gitignore`)

## Materi

- **Kenapa Mengabaikan File?**: Tidak semua file dalam folder proyek perlu disimpan dalam riwayat Git. Beberapa contoh file yang **HARUS DIABAIKAN** antara lain:
    - **File Rahasia**: File berisi password, API keys, atau informasi sensitif lainnya (`.env`, `secrets.yml`).
    - **File Log**: File log yang dibuat secara otomatis oleh aplikasi.
    - **File Sistem Operasi**: File-file sampah yang dibuat oleh sistem operasi (misalnya `.DS_Store` di Mac, `Thumbs.db` di Windows).
    - **Folder Dependensi**: Folder seperti `node_modules` atau `vendor` yang berisi ribuan file library. Folder ini bisa di-generate ulang, jadi tidak perlu disimpan di Git.

- **Cara Kerja `.gitignore`**: Git bisa diinstruksikan untuk mengabaikan file atau folder tertentu. Caranya adalah dengan membuat sebuah file bernama **`.gitignore`** (diawali dengan titik) di direktori utama proyek Anda. Tuliskan nama file atau pola folder yang ingin diabaikan di dalam file ini, satu per baris. Git akan berhenti melacaknya.

## Praktik

1.  **Buat File Rahasia**: Di folder proyek Anda, buat file baru bernama `rahasia.txt`. Isi dengan teks seperti: `"Ini adalah password database: 123456"`.

2.  **Cek Status**: Jalankan `git status`. Anda akan melihat `rahasia.txt` muncul sebagai *untracked file*. Ini berbahaya, karena jika Anda tidak sengaja melakukan `git add .`, file ini bisa ter-commit dan ter-push.

3.  **Buat File `.gitignore`**:
    - Buat file baru dengan nama **`.gitignore`**. Pastikan namanya tepat, dengan titik di depan.
    - Buka file `.gitignore` dan tuliskan nama file yang ingin diabaikan di dalamnya. Cukup tulis:
      ```
      rahasia.txt
      ```
    - Simpan file `.gitignore`.

4.  **Buktikan File Diabaikan**: Jalankan `git status` sekali lagi.
    - Perhatikan! `rahasia.txt` sudah **TIDAK MUNCUL** lagi dalam daftar. Git sekarang mengabaikannya.
    - Namun, file `.gitignore` itu sendiri sekarang muncul sebagai *untracked file*. Ini benar, karena file `.gitignore` adalah bagian penting dari proyek Anda dan harus di-commit.

5.  **Commit File `.gitignore`**: Lakukan `add` dan `commit` **hanya** untuk file `.gitignore`.
    ```bash
    git add .gitignore
    git commit -m "build: Menambahkan .gitignore untuk mengabaikan file rahasia"
    git push
    ```

---
*Kemampuan untuk mengabaikan file sangat penting untuk menjaga repositori tetap bersih dan aman. Selamat! Mari kita menuju latihan kolaborasi di akhir pekan.*