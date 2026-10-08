# Operator Relasi dan Logika

Dalam pemrograman, kita tidak hanya melakukan perhitungan matematika dasar, tetapi juga sering kali harus **membandingkan data** atau **membuat keputusan** berdasarkan kondisi tertentu. Sama halnya seperti Penalaran Umum UTBK, soal benar salah sesuai kondisi yang diberikan.

Untuk melakukan hal tersebut, kita menggunakan Operator Relasi dan Operator Logika. Hasil akhir dari kedua operator ini selalu berupa tipe data **Boolean** (`True` atau `False`).

---

## 1. Operator Relasi (Perbandingan)
Operator relasi digunakan untuk membandingkan dua buah nilai. Apakah nilai A lebih besar dari B? Apakah nilai A sama dengan B?

Berikut adalah operator relasi di Python:
- `==` : Sama dengan
- `!=` : Tidak sama dengan
- `>`  : Lebih besar dari
- `<`  : Lebih kecil dari
- `>=` : Lebih besar atau sama dengan
- `<=` : Lebih kecil atau sama dengan

```python
>>> a = 10
>>> b = 5

>>> print(a > b)
True
>>> print(a < b)
False
>>> print(a >= 10)
True
>>> print(a != b)
True
```

**notes:** 
 `=` dan `==` tidak sama. 
Tanda `=` (satu sama dengan) digunakan untuk **mengisi nilai ke variabel** (contoh: `x = 5`). Sedangkan `==` (dua sama dengan) digunakan untuk **bertanya/membandingkan** apakah nilainya sama (contoh: `x == 5`).

**Soal 1:**
Buatlah dua variabel, `nilai_saya = 85` dan `kkm = 75`. Tuliskan kode menggunakan operator relasi untuk mengecek apakah `nilai_saya` lebih besar atau sama dengan `kkm`. Cetak hasilnya!

---

## 2. Operator Logika (Logical Operators)
Operator logika digunakan untuk menggabungkan dua atau lebih kondisi Boolean. Ada tiga operator logika utama di Python: `and`, `or`, dan `not`.

- **`and` (Dan)**: Akan menghasilkan `True` JIKA DAN HANYA JIKA **semua** kondisi bernilai `True`.
- **`or` (Atau)**: Akan menghasilkan `True` JIKA **salah satu** (atau semua) kondisi bernilai `True`.
- **`not` (Kebalikan)**: Membalikkan keadaan. Jika `True` di-`not`-kan akan menjadi `False`, begitu pula sebaliknya.

```python
>>> x = True
>>> y = False

>>> print(x and y)
False
>>> print(x or y)
True
>>> print(not x)
False
```

**Soal 2:**
Ada dua variabel: `punya_ktp = True` dan `usia_cukup = False`. Jika syarat untuk membuat SIM adalah harus punya KTP **dan** usianya cukup, gunakan operator logika yang tepat untuk mengecek apakah orang tersebut bisa membuat SIM, lalu cetak hasilnya!

---

## 3. Menggabungkan Operator Relasi dan Logika
Kekuatan sesungguhnya dari operator ini terlihat ketika kita menggabungkannya. Kita bisa mengecek apakah sebuah angka berada di dalam rentang tertentu, atau apakah seorang mahasiswa memenuhi syarat kelulusan.

```python
>>> nilai_ujian = 80
>>> absensi = 85

# Syarat lulus: nilai ujian minimal 70 DAN absensi di atas 75
>>> status_lulus = (nilai_ujian >= 70) and (absensi > 75)
>>> print(status_lulus)
True

# Mengecek apakah angka berada di rentang 1 sampai 10
>>> angka = 15
>>> cek_rentang = (angka >= 1) and (angka <= 10)
>>> print(cek_rentang)
False
```

**Soal 3:**
Seorang mahasiswa berhak mendapat predikat *Cumlaude* jika IPK-nya lebih besar atau sama dengan `3.5` **DAN** masa studinya kurang dari atau sama dengan `8` semester. 
Diberikan variabel `ipk = 3.6` dan `semester = 9`. Buatlah ekspresi logika untuk mengecek apakah mahasiswa tersebut mendapat *Cumlaude*, lalu cetak hasilnya!

---

## 4. Operator Keanggotaan (in / not in)
Khusus di Python, ada operator logika tambahan yang sangat praktis bernama operator keanggotaan. Operator ini digunakan untuk mengecek apakah suatu elemen ada di dalam suatu List, Tuple, atau String.

- **`in`**: Menghasilkan `True` jika elemen ditemukan.
- **`not in`**: Menghasilkan `True` jika elemen TIDAK ditemukan.

```python
# Cek keanggotaan pada List
>>> mahasiswa = ["Ijul", "Chlea", "Didi"]
>>> print("Ijul" in mahasiswa)
True
>>> print("Budi" in mahasiswa)
False

# Cek keanggotaan pada String
>>> teks = "Statistika Bisnis"
>>> print("Bisnis" in teks)
True
>>> print("Data" not in teks)
True
```

**Soal 4:**
Diberikan tuple `daftar_email = ("admin@its.ac.id", "dosen@its.ac.id", "mahasiswa@its.ac.id")`. Tuliskan kode untuk mengecek apakah `"hacker@gmail.com"` **tidak ada** (`not in`) di dalam daftar email tersebut. Cetak hasil pengecekannya!