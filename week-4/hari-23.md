# Hari 23: Mengambil Commit Pilihan (`cherry-pick`)

## Materi

- **Apa itu `cherry-pick`?**: Sesuai namanya, `cherry-pick` adalah perintah untuk "memetik buah ceri". Ini memungkinkan Anda untuk memilih satu (atau lebih) commit spesifik dari sebuah branch dan menempelkannya ke branch lain tempat Anda berada.

- **Kapan Berguna?**: Bayangkan sebuah skenario:
    - Anda sedang mengerjakan `branch-fitur-besar` yang belum siap di-merge.
    - Di dalam branch itu, Anda menemukan dan memperbaiki sebuah bug kritikal dalam satu commit.
    - Anda tidak bisa me-merge seluruh `branch-fitur-besar` hanya untuk mendapatkan perbaikan bug itu.
    - Solusinya: `cherry-pick`! Anda bisa "mencuri" hanya commit perbaikan bug tersebut dan menempelkannya ke branch `main` tanpa harus membawa serta sisa fitur yang belum selesai.

## Praktik

1.  **Buat Branch Eksperimen**: Dari `main`, buat branch baru.
    ```bash
    git switch -c eksperimen
    ```

2.  **Buat Dua Commit Terpisah**:
    - Buat file `resep_nusantara.txt`. Tambahkan resep soto, lalu `add` dan `commit` dengan pesan **C1**: `"feat: Menambahkan resep soto"`.
    - Edit lagi file tersebut, tambahkan resep rawon. `add` dan `commit` dengan pesan **C2**: `"feat: Menambahkan resep rawon"`.

3.  **Dapatkan ID Commit**: Jalankan `git log --oneline`. Anda akan melihat dua commit baru. Salin (copy) ID unik (hash) dari commit **C1** (resep soto). Misalnya `a1b2c3d`.

4.  **Kembali ke `main`**: Kita memutuskan hanya ingin merilis resep soto untuk saat ini.
    ```bash
    git switch main
    ```

5.  **Lakukan Cherry-pick**: Jalankan perintah `cherry-pick` dengan ID commit yang sudah Anda salin.
    ```bash
    git cherry-pick <ID_COMMIT_C1> 
    # Contoh: git cherry-pick a1b2c3d
    ```

6.  **Verifikasi**:
    - Cek isi file `resep_nusantara.txt` di branch `main`. Seharusnya hanya berisi resep soto.
    - Jalankan `git log`. Anda akan lihat commit "feat: Menambahkan resep soto" sekarang ada di riwayat `main`, sementara commit resep rawon tidak.

7.  **Push ke GitHub**:
    ```bash
    git push origin main
    ```

---
*Cherry-pick adalah alat yang sangat kuat untuk situasi spesifik. Besok, kita akan kembali ke dasar untuk melihat perbedaan antar file dengan `diff`.*