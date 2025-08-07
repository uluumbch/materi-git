# Hari 24: Melihat Perbedaan (`diff`)

## Materi

Seringkali sebelum melakukan `commit`, kita ingin melihat kembali perubahan apa saja yang telah kita buat. `git diff` adalah perintah untuk itu.

- **`git diff`**: Perintah ini, jika dijalankan tanpa argumen, akan membandingkan file-file di **Working Directory** Anda (yang belum di-stage) dengan versi terakhir yang ada di **Staging Area** (atau commit terakhir jika Staging Area kosong). Ini menunjukkan perubahan yang "kotor" atau belum di-`add`.

- **`git diff --staged`** (atau `git diff --cached`): Perintah ini membandingkan file-file yang sudah Anda `add` ke **Staging Area** dengan versi terakhir yang ada di **commit**. Ini berguna untuk me-review ulang perubahan yang akan Anda commit.

Alurnya:
1.  Anda mengubah file.
2.  `git diff` akan menunjukkan perubahan tersebut.
3.  Anda menjalankan `git add <file>`.
4.  Sekarang `git diff` tidak menunjukkan apa-apa (karena Working Directory & Staging Area sama), tetapi `git diff --staged` akan menunjukkan perubahan yang siap di-commit.

## Praktik

1.  **Ubah Beberapa File**:
    - Buka `profil.txt` dan tambahkan baris baru, misalnya "Kota: Jakarta".
    - Buka `portofolio.html` dan ubah teks di dalam tag `<h1>`.

2.  **Lihat Perubahan Belum di-Stage**: Jalankan `git diff`. Anda akan melihat output yang menunjukkan baris mana yang dihapus (`-`) dan ditambahkan (`+`) di kedua file.
    - Salin seluruh output dari perintah ini.
    - Buat file `hari-24.txt` dan tempelkan hasilnya di sana.

3.  **Stage Salah Satu File**: Tambahkan hanya satu file ke Staging Area.
    ```bash
    git add profil.txt
    ```

4.  **Lihat Perbedaan Lagi**:
    - Jalankan `git diff` lagi. Sekarang ia hanya akan menunjukkan perubahan untuk `portofolio.html`, karena perubahan di `profil.txt` sudah masuk ke Staging Area.
    - Jalankan `git diff --staged`. Perintah ini sekarang akan menunjukkan perubahan untuk `profil.txt`.
    - Salin output dari `git diff --staged` dan tempelkan ke bagian bawah file `hari-24.txt`.

5.  **Commit dan Push**: `add` semua sisa perubahan, lalu `commit` dan `push` file `hari-24.txt` tersebut.
    ```bash
    git add .
    git commit -m "docs: Menambahkan contoh hasil diff"
    git push
    ```

---
*`git diff` adalah alat vital untuk memastikan Anda hanya meng-commit perubahan yang Anda inginkan. Besok kita akan belajar cara menandai rilis resmi.*