# Hari 02: Repositori Git Pertama (`git init`)

## Materi

- **Konsep Repositori:** Repositori (sering disingkat "repo") adalah sebutan untuk sebuah proyek yang sudah diinisialisasi oleh Git. Ini adalah folder proyek Anda yang kini memiliki "kemampuan super" untuk melacak versi.

- **Folder `.git`:** Ketika Anda menjalankan `git init`, Git akan membuat sebuah folder tersembunyi bernama `.git` di dalam direktori proyek Anda. Folder inilah "otak" dari repositori Anda. Ia berisi semua data dan riwayat perubahan. **Jangan pernah mengubah atau menghapus isi folder ini secara manual!**

- **Perintah `git init`:** Ini adalah perintah untuk mengubah folder biasa menjadi sebuah repositori Git. Anda hanya perlu menjalankannya sekali di awal sebuah proyek.

## Praktik

1.  Pastikan Anda berada di dalam folder `30-hari-git-github-NAMA_ANDA` melalui terminal.
2.  Jalankan perintah berikut untuk menginisialisasi repositori:
    ```bash
    git init
    ```
    Anda akan melihat pesan seperti `Initialized empty Git repository in ...`
3.  Untuk membuktikan folder `.git` telah dibuat, jalankan perintah yang sesuai untuk sistem operasi Anda:
    - Mac/Linux: `ls -a`
    - Windows: `dir /a`
    Anda akan melihat `.git` ada di dalam daftar file dan folder.
4.  Buat file baru bernama `hari-02.txt`.
5.  Di dalam file `hari-02.txt`, jelaskan dengan kata-kata Anda sendiri apa fungsi dari perintah `git init` berdasarkan pemahaman Anda dari materi hari ini.

---
*Materi hari ini selesai. Besok kita akan belajar menyimpan pekerjaan kita secara permanen. Sampai jumpa!*