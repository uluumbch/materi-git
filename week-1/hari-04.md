# Hari 04: Memeriksa Status & Sejarah (`status` & `log`)

## Materi

- **`git status`**: Anggap ini sebagai "GPS" Anda. Perintah ini akan memberitahu Anda segalanya tentang kondisi repositori saat ini: file mana yang sudah diubah, file mana yang ada di *Staging Area*, dan file mana yang belum dilacak oleh Git. Sering-seringlah menggunakan perintah ini untuk mengetahui posisi Anda sebelum melakukan tindakan apa pun.

- **`git log`**: Ini adalah "mesin waktu" Anda. Perintah ini akan menampilkan seluruh riwayat *commit* yang pernah Anda buat, dari yang terbaru hingga yang paling lama. Setiap *commit* memiliki kode unik (disebut *hash*), penulis, tanggal, dan pesan *commit* yang Anda tulis.

## Praktik

Hari ini kita akan melakukan dua commit terpisah untuk melihat bagaimana `git log` bekerja.

1.  Buat file baru bernama `hari-04.txt`.
2.  Jalankan perintah `git status` di terminal. Salin (copy-paste) seluruh output dari perintah tersebut dan tempelkan ke dalam file `hari-04.txt`.
3.  Lakukan proses `add` dan `commit` untuk file `hari-04.txt`. Gunakan pesan commit yang sesuai, misalnya:
    ```bash
    git add hari-04.txt
    git commit -m "Menambahkan status repositori ke file hari-04.txt"
    ```
4.  Sekarang, jalankan perintah `git log` di terminal. Perhatikan outputnya. Salin seluruh output tersebut.
5.  Buat file baru bernama `log-hari-04.txt`. Tempelkan hasil dari `git log` tadi ke dalam file ini.
6.  Lakukan `add` dan `commit` sekali lagi untuk file `log-hari-04.txt` tersebut.
    ```bash
    git add log-hari-04.txt
    git commit -m "Menambahkan riwayat log ke file terpisah"
    ```
7.  Setelah selesai, coba jalankan `git log` lagi. Anda sekarang seharusnya melihat dua commit baru dari hari ini ditambah commit pertama Anda dari hari kemarin.

---
*Materi hari ini selesai. Besok kita akan belajar cara memperbaiki kesalahan sederhana. Sampai jumpa!*