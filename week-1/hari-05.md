# Hari 05: Membatalkan Kesalahan (`restore`)

## Materi

Setiap orang pasti pernah membuat kesalahan. Git menyediakan beberapa cara untuk membatalkannya. Hari ini kita fokus pada yang paling sederhana dan umum digunakan untuk perubahan lokal.

- **`git restore <nama-file>`**: Perintah ini digunakan untuk membatalkan perubahan pada file di *Working Directory* Anda (file yang sudah Anda ubah tapi **belum** di-`add` ke Staging Area). Ia akan mengembalikan isi file ke versi terakhir yang ada di *commit*. Ini sangat berguna jika Anda salah mengedit file dan ingin kembali ke versi yang "bersih" tanpa harus mengingat-ingat apa yang Anda ubah.

- **Konsep `reset` dan `revert`**: Ini adalah perintah yang lebih kuat untuk membatalkan *commit* yang sudah terjadi. `git reset` bisa "menghapus" *commit* dari sejarah (bisa berbahaya jika sudah dibagikan), sedangkan `git revert` akan membuat *commit* baru yang isinya adalah kebalikan dari *commit* yang ingin dibatalkan (lebih aman). Kita akan membahasnya lebih dalam di minggu-minggu berikutnya.

## Praktik

1.  Buat file baru bernama `hari-05.txt`. Isi dengan teks: `"Ini teks yang benar."`
2.  Lakukan `add` dan `commit` untuk file tersebut.
    ```bash
    git add hari-05.txt
    git commit -m "Menambahkan file hari-05 dengan teks yang benar"
    ```
3.  Sekarang, buka kembali file `hari-05.txt` dan ubah isinya menjadi: `"Ini teks yang salah."` Simpan file tersebut.
4.  Jalankan `git status`. Anda akan lihat bahwa `hari-05.txt` terdeteksi sebagai *modified*.
5.  Untuk mengembalikan isinya ke versi yang sudah di-*commit*, jalankan perintah:
    ```bash
    git restore hari-05.txt
    ```
6.  Buka kembali file `hari-05.txt`. Isinya seharusnya sudah kembali menjadi `"Ini teks yang benar."`
7.  Buat file baru `pengalaman-hari-05.txt`. Tuliskan di dalamnya pengalaman Anda saat mencoba `git restore` ini. Jelaskan apa yang terjadi menurut pengamatan Anda.
8.  Lakukan `add` dan `commit` untuk file `pengalaman-hari-05.txt`.

---
*Materi hari ini selesai. Di akhir pekan, kita akan menggabungkan semua yang telah dipelajari dalam sebuah latihan.*