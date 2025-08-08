# Hari 25: Menandai Rilis (`tag`)

## Materi

- **Apa itu `tag`?**: `Tag` di Git adalah penanda (bookmark) yang menunjuk ke sebuah commit spesifik. Tidak seperti `branch` yang terus bergerak, `tag` bersifat permanen. Biasanya `tag` digunakan untuk menandai titik-titik penting dalam sejarah proyek, seperti versi rilis (`v1.0`, `v1.1`, `v2.0-beta`).

- **Jenis Tag**:
    - **Lightweight Tag**: Hanya sebuah penunjuk ke sebuah commit. Tidak menyimpan informasi tambahan.
    - **Annotated Tag**: Sebuah objek penuh di Git. Ia menyimpan informasi pembuat tag, tanggal, pesan tagging, dan bisa diverifikasi dengan GPG. **Ini adalah jenis tag yang direkomendasikan untuk rilis resmi.**

- **Pushing Tags**: Secara default, `git push` tidak mengirimkan tag ke remote. Anda harus mendorongnya secara eksplisit.

## Praktik

Mari kita anggap proyek portofolio Anda sudah mencapai versi stabil pertama.

1.  **Pastikan di Commit yang Benar**: Pastikan Anda berada di commit terakhir dari branch `main` yang ingin Anda tandai.
    ```bash
    git switch main
    git pull
    ```

2.  **Buat Annotated Tag**: Buat tag `v1.0` dengan pesan yang jelas.
    ```bash
    git tag -a v1.0 -m "Rilis stabil pertama proyek portofolio"
    ```
    - `-a` menandakan *annotated*.
    - `-m` adalah untuk pesan tag.

3.  **Lihat Tag**: Jalankan `git tag` untuk melihat daftar semua tag yang ada di repositori lokal Anda.

4.  **Push Tag ke GitHub**: Kirim tag `v1.0` yang baru Anda buat ke `origin` (GitHub).
    ```bash
    git push origin v1.0
    ```
    Atau, untuk mendorong semua tag Anda sekaligus:
    ```bash
    git push --tags
    ```

5.  **Verifikasi**: Buka repositori Anda di GitHub. Di halaman utama, klik pada bagian "Releases" atau "Tags" (biasanya di sisi kanan). Anda akan melihat `v1.0` terdaftar di sana, lengkap dengan pesan yang Anda tulis.

---
*Selamat! Proyek Anda sekarang memiliki penanda versi resmi. Sekarang, saatnya untuk proyek final!*