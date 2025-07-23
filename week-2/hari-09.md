# Hari 09: Mengambil Proyek dari Remote (`clone`)

## Materi

- **Apa itu `git clone`?**: Jika `git push` adalah untuk mengunggah, maka `git clone` adalah untuk **mengunduh (download)**. Perintah ini digunakan untuk membuat salinan lokal yang identik dari sebuah repositori yang sudah ada di remote (seperti GitHub).

- **Kapan Menggunakannya?**: Anda akan menggunakan `git clone` saat:
    1.  Anda ingin mulai mengerjakan sebuah proyek yang sudah ada di GitHub.
    2.  Anda ingin bekerja di komputer lain dan perlu mengunduh repositori Anda sendiri dari GitHub.

`git clone` secara otomatis membuat folder proyek, menginisialisasi Git di dalamnya (`.git`), menambahkan `remote` bernama `origin` yang menunjuk ke alamat URL sumber, dan mengunduh semua file serta riwayat commit.

## Praktik

1.  **Pindah ke Folder Lain**: Di terminal Anda, pindah ke direktori **di luar** folder proyek `30-hari-git-github-NAMA_ANDA`. Misalnya, jika proyek Anda ada di `Documents/bootcamp`, pindahlah ke `Documents`.
    ```bash
    cd .. 
    ```

2.  **Clone Repositori Anda**: Sekarang, gunakan `git clone` dengan URL repositori GitHub Anda untuk mengunduhnya ke folder baru.
    ```bash
    git clone https://github.com/USERNAME_ANDA/NAMA_REPO_ANDA.git
    ```
    Perintah ini akan membuat folder baru bernama `NAMA_REPO_ANDA` yang berisi salinan lengkap proyek Anda.

3.  **Masuk ke Folder Hasil Kloning**: Pindah ke dalam direktori yang baru saja dibuat oleh `git clone`.
    ```bash
    cd NAMA_REPO_ANDA
    ```

4.  **Buat Perubahan Baru**:
    - Buat file baru bernama `hari-09.txt`.
    - Isi file tersebut dengan teks: `"Saya berhasil mengkloning repo ini."`

5.  **Simpan dan Unggah Perubahan**: Lakukan siklus kerja yang sudah Anda pelajari (`add`, `commit`, `push`) dari dalam folder hasil kloning ini.
    ```bash
    git add hari-09.txt
    git commit -m "feat: Menambahkan file verifikasi kloning"
    git push
    ```
    (Anda tidak perlu `-u origin main` lagi karena koneksi *upstream* sudah diatur saat proses `clone`).

6.  **Verifikasi**: Cek halaman GitHub Anda, `hari-09.txt` seharusnya sudah muncul.

---
*Anda sekarang bisa bekerja dari mana saja dengan meng-clone repositori Anda. Besok kita akan belajar cara menyinkronkan perubahan antar folder.*