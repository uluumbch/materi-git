# Hari 18: Mengatasi Konflik Merge

## Materi

- **Apa itu Merge Conflict?**: Konflik terjadi ketika Anda mencoba me-merge dua branch yang telah mengubah **baris yang sama** di **file yang sama** dengan cara yang berbeda. Git tidak bisa memutuskan versi mana yang benar, jadi ia berhenti dan meminta Anda sebagai manusia untuk menjadi penengah.

- **Kenapa Bisa Terjadi?**: Ini sangat umum terjadi dalam tim. Misalnya, Anda dan teman Anda sama-sama mengubah judul di halaman `index.html` pada branch yang berbeda. Saat di-merge, Git akan bingung judul mana yang harus dipakai.

- **Cara Menyelesaikannya**: Ketika konflik terjadi, Git akan menandai area yang berkonflik di dalam file tersebut dengan penanda khusus:
    ```
    <<<<<<< HEAD
    Teks dari branch Anda saat ini (misal: main)
    =======
    Teks dari branch yang ingin di-merge (misal: fitur-baru)
    >>>>>>> fitur-baru
    ```
    Tugas Anda adalah:
    1.  Buka file tersebut.
    2.  Hapus penanda `<<<<<<<`, `=======`, `>>>>>>>`.
    3.  Edit area tersebut menjadi versi final yang Anda inginkan (bisa jadi gabungan keduanya, atau memilih salah satu).
    4.  Lakukan `git add <nama-file-yang-konflik>`.
    5.  Lakukan `git commit` untuk menyelesaikan proses merge.

## Praktik

Kita akan sengaja menciptakan sebuah konflik.

1.  **Buat Branch Baru**: Dari `main`, buat branch baru.
    ```bash
    git switch -c eksperimen-konflik
    ```

2.  **Ubah di `main`**: Kembali ke `main`.
    ```bash
    git switch main
    ```
    - Buka file `profil.txt`. Ubah baris pertama, misalnya menjadi `Nama: Budi Keren`.
    - Commit perubahan ini di `main`.
      ```bash
      git add profil.txt
      git commit -m "docs: Memperbarui nama di profil"
      ```

3.  **Ubah di Branch Lain**: Sekarang, kembali ke branch eksperimen.
    ```bash
    git switch eksperimen-konflik
    ```
    - Buka file `profil.txt`. Ubah baris pertama dengan isi yang **berbeda**, misalnya `Nama: Budi Programmer`.
    - Commit perubahan ini di branch `eksperimen-konflik`.
      ```bash
      git add profil.txt
      git commit -m "docs: Mengganti nama di profil menjadi lebih profesional"
      ```

4.  **Ciptakan Konflik**: Kembali ke `main` dan coba merge.
    ```bash
    git switch main
    git merge eksperimen-konflik
    ```
    **BOOM!** Git akan berhenti dan menampilkan pesan `CONFLICT (content): Merge conflict in profil.txt`.

5.  **Selesaikan Konflik**:
    - Buka file `profil.txt` di editor Anda. Anda akan melihat penanda konflik.
    - Hapus semua baris penanda (`<<<<<<<`, `=======`, `>>>>>>>`).
    - Putuskan versi finalnya. Misal, Anda ingin hasil akhirnya adalah `Nama: Budi Keren (Programmer)`.
    - Setelah file terlihat benar, simpan.

6.  **Selesaikan Merge**: Beri tahu Git bahwa Anda sudah menyelesaikan konflik.
    ```bash
    git add profil.txt
    git commit 
    ```
    Editor akan terbuka untuk menulis pesan commit. Anda bisa biarkan pesan default yang sudah disediakan Git, lalu simpan dan tutup editor untuk menyelesaikan merge.

---
*Konflik merge mungkin terlihat menakutkan pada awalnya, tetapi sebenarnya itu adalah proses yang logis. Anda sekarang siap menghadapi situasi kolaborasi yang lebih kompleks.*