# Tugas Praktikum { Pertemuan ke 9 } <img src=https://logos-download.com/wp-content/uploads/2016/05/MySQL_logo_logotype.png width="130px" >


|**Nama**|**NIM**|**Kelas**|**Matkul**|
|----|---|-----|------|
|Muhammad Ikhsan Fakhrudin|312210019|TI.22.A2|Basis Data|

# Soal Latihan Praktikum

- Implementasikan penggunaan ***CONSTRAINT FOREIGN KEY*** pada semua tabel yang berelasi.
- yang perlu diperhatikan:
  - tipe data pada field yang berelasi harus sama termasuk juga ukuran datanya.
  - misal: pada tabel dosen, kd_ds VARCHAR(10) maka tabel yang merujuk yaitu tabel mahasiswa, kd_ds juga harus bertipe VARCHAR(10).

1. Lakukan penambahan data pada tabel mahasiswa dengan mengisi kd_ds yang belum ada pada data dosen.
2. Hapus satu record data pada tabel dosen yang telah dirujuk pada tabel mahasiswa.
3. Ubah mode menjadi ON UPDATE CASCADE ON DELETE RESTRICT
4. Lakukan perubahan data pada tabel dosen (kd_ds)
5. Lakukan penghapusan data pada tabel dosen
6. Ubah mode menjadi ON UPDATE CASCADE ON DELETE SET NULL
7. Lakukan penghapusan data pada tabel dosen

### Evaluasi dan Pertanyaan

- ***Tulis semua perintah-perintah SQL percobaan di atas beserta outputnya!***
- ***Apa bedanya penggunaan RESTRICT dan penggunaan CASCADE***
- ***Berikan kesimpulan anda!***
- ***Buat laporan praktikum yang berisi, langkah-langkah praktikum beserta screenshot yang sudah dilakukan dalam bentuk dokumen.***

## Implementasi CONSTRAINT FOREIGN KEY

Berikut ini adalah langkah-langkah dan penerapan dalam pengimplementasian CONSTRAINT FOREIGN KEY pada Tabel mahasiswa dalam kolom kd_ds

- Pastikan kamu sudah mempunyai sebuah database yang berisi Tabel mahasiswa dan Tabel dosen, dan juga didalam tabel tersebut sudah berisi sebuah data. Berikut adalah contohnya:

![gambar1](screenshot/ss1.png)

- Membuat foreign key

Dalam ALTER TABLE:

ALTER TABLE mahasiswa
```
ADD CONSTRAINT fk_dosenwali FOREIGN KEY (kd_ds)     REFERENCES dosen(kd_ds)
```

![gambar2](screenshot/ss2.png)

- Dalam CREATE TABLE:
```
CREATE TABLE mahasiswa(
nim VARCHAR(10) NOT NULL,
nama VARCHAR(100) NOT NULL,
kd_ds VARCHAR(10),
PRIMARY KEY(nim),
CONSTRAINT fk_DosenWali FOREIGN KEY (kd_ds)
REFERENCES dosen(kd_ds)
);
```

![gambar3](screenshot/ss3.png)