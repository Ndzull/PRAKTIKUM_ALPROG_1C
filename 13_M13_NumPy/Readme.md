# Library NumPy

Sejauh ini, kita selalu menyimpan kumpulan angka menggunakan **List**. Masalahnya, List bawaan Python tidak dirancang khusus untuk komputasi matematika skala besar. Jika kalian ingin mengalikan setiap angka di dalam List dengan 2, kalian harus repot-repot membuat `for loop`.

Di sinilah **NumPy** (*Numerical Python*) hadir. NumPy adalah *library* paling fundamental di dunia Data Science dan Statistika yang menyediakan struktur data bernama **ndarray** (*N-dimensional array*).

Kenapa harus NumPy?
- **Jauh Lebih Cepat:** Proses perhitungan ribuan hingga jutaan data bisa berjalan puluhan kali lebih cepat dibanding List biasa.
- **Operasi Langsung (*Vectorization*):** Kalian bisa melakukan operasi matematika pada seluruh isi data sekaligus tanpa perlu `for loop`.
- **Kaya Fungsi Statistika:** Menghitung rata-rata, median, hingga standar deviasi cukup dengan satu baris kode.

---

## 1. Instalasi, Import, dan Membuat Array
Karena NumPy adalah *library* eksternal, pastikan kalian sudah menginstalnya terlebih dahulu melalui terminal:
```bash
pip install numpy
```

Di dalam kode Python, kesepakatan global programmer adalah mengimpor NumPy dengan nama panggilan (alias) **`np`**.

```python
>>> import numpy as np

# 1. Membuat Array 1 Dimensi (seperti List/Vektor)
>>> data_1d = np.array([10, 20, 30, 40])
>>> print(data_1d)
[10 20 30 40]
>>> type(data_1d)
<class 'numpy.ndarray'>

# 2. Membuat Array 2 Dimensi (seperti Tabel/Matriks)
>>> data_2d = np.array([
...     [1, 2, 3],
...     [4, 5, 6]
... ])
>>> print(data_2d)
[[1 2 3]
 [4 5 6]]

# Mengecek dimensi dan ukuran (baris, kolom)
>>> print(data_2d.ndim)   # Jumlah dimensi
2
>>> print(data_2d.shape)  # (2 baris, 3 kolom)
(2, 3)
```

**Notes:** Perhatikan saat dicetak dengan `print()`, elemen pada NumPy array **tidak dipisahkan oleh koma**, berbeda dengan List. Selain itu, seluruh elemen di dalam satu NumPy array idealnya memiliki tipe data yang seragam (misalnya angka semua).

**Soal 1**
Import NumPy sebagai `np`. Buatlah sebuah array 2 dimensi bernama `penjualan` berukuran 2 baris dan 3 kolom yang berisi angka bebas (misalkan data penjualan 2 cabang toko selama 3 hari). Cetak array tersebut beserta hasil dari `.shape` dan `.ndim`-nya!

---

## 2. Membuat Array Otomatis
Terkadang kita butuh membuat deret angka atau matriks awal tanpa harus mengetiknya satu per satu secara manual. NumPy menyediakan beberapa fungsi bawaan yang sangat praktis:

- **`np.zeros(n)`**: Membuat array berisi angka `0` semua.
- **`np.ones(n)`**: Membuat array berisi angka `1` semua.
- **`np.arange(start, stop, step)`**: Sama persis seperti `range()` di Python, tapi langsung menghasilkan NumPy array.
- **`np.linspace(start, stop, jumlah_titik)`**: Membagi rentang angka menjadi beberapa titik dengan jarak yang sama rata.

```python
>>> import numpy as np

>>> print(np.zeros(4))
[0. 0. 0. 0.]

>>> print(np.ones((2, 3)))  # Matriks 2x3 berisi angka 1
[[1. 1. 1.]
 [1. 1. 1.]]

>>> print(np.arange(0, 10, 2))
[0 2 4 6 8]

>>> print(np.linspace(0, 1, 5))
[0.   0.25 0.5  0.75 1.  ]
```

**Soal 2**
Gunakan fungsi bawaan NumPy untuk membuat:
1. Array bernama `kelipatan_lima` yang berisi angka dari `5` sampai `50` dengan kelipatan `5` (gunakan `np.arange()`).
2. Array 2D bernama `matriks_nol` berukuran 3 baris dan 3 kolom yang seluruh isinya angka `0` (gunakan `np.zeros()`).
Cetak kedua array tersebut!

---

## 3. Indexing dan Slicing pada Array
Untuk array 1D, cara *indexing* dan *slicing*-nya sama persis dengan List. Namun, untuk array 2D (Matriks), kita menggunakan format **`[baris, kolom]`** yang dipisahkan oleh koma.

```python
>>> matriks = np.array([
...     [10, 20, 30],
...     [40, 50, 60],
...     [70, 80, 90]
... ])

# Mengambil 1 elemen: baris ke-0, kolom ke-1
>>> print(matriks[0, 1])
20

# Mengambil 1 baris penuh: baris ke-2, semua kolom (:)
>>> print(matriks[2, :])
[70 80 90]

# Mengambil 1 kolom penuh: semua baris (:), kolom ke-0
>>> print(matriks[:, 0])
[10 40 70]

# Slicing sebagian matriks (baris 0-1, kolom 1-2)
>>> print(matriks[0:2, 1:3])
[[20 30]
 [50 60]]
```

**Soal 3**
Diberikan matriks berikut:
```python
data = np.array([
    [11, 12, 13],
    [21, 22, 23],
    [31, 32, 33]
])
```
Tuliskan kode untuk mengambil:
1. Angka **23** menggunakan *indexing*.
2. Seluruh elemen pada **kolom tengah** (`[12, 22, 32]`) menggunakan *slicing*.

---

## 4. Operasi Matematika (*Vectorization*)
Inilah kekuatan utama NumPy dibandingkan List biasa. Jika kalian menjumlahkan dua List (`[1, 2] + [3, 4]`), hasilnya malah digabung menjadi `[1, 2, 3, 4]`. Di NumPy, operasi matematika langsung diterapkan ke **masing-masing elemen yang posisinya sejajar**.

```python
>>> a = np.array([10, 20, 30])
>>> b = np.array([1, 2, 3])

# Operasi antar 2 array (elemen per elemen)
>>> print(a + b)
[11 22 33]
>>> print(a * b)
[10 40 90]

# Operasi dengan 1 angka (Skalar / Broadcasting)
>>> print(a * 2)
[20 40 60]
>>> print(a - 5)
[ 5 15 25]
```

**Soal 4**
Sebuah kafe menjual 3 jenis minuman dengan data array berikut:
- `harga = np.array([15000, 20000, 25000])`
- `terjual = np.array([10, 5, 8])`

Tanpa menggunakan `for loop`, hitung array `pendapatan` (hasil perkalian `harga` dan `terjual`). Kemudian, karena ada pajak layanan 10%, buat array `pendapatan_bersih` dengan mengalikan `pendapatan` dengan `0.9`. Cetak kedua array hasilnya!

---

## 5. Fungsi Statistika Dasar di NumPy
Bagi mahasiswa Statistika Bisnis, bagian ini akan sangat sering dipakai. NumPy menyediakan fungsi statistik siap pakai yang tinggal dipanggil:

- `np.sum()` : Menjumlahkan seluruh elemen.
- `np.mean()` : Menghitung rata-rata (*mean*).
- `np.median()` : Mencari nilai tengah (*median*).
- `np.std()` : Menghitung standar deviasi (*standard deviation*).
- `np.min()` & `np.max()` : Mencari nilai terkecil dan terbesar.

```python
>>> nilai = np.array([70, 80, 90, 85, 75])

>>> print("Total   :", np.sum(nilai))
Total   : 400
>>> print("Mean    :", np.mean(nilai))
Mean    : 80.0
>>> print("Median  :", np.median(nilai))
Median  : 80.0
>>> print("Max     :", np.max(nilai))
Max     : 90
>>> print("Std Dev :", np.std(nilai))
Std Dev : 7.0710678118654755
```

**Notes:** Pada array 2D, kalian bisa menambahkan parameter `axis=0` untuk menghitung statistik **per kolom** (ke bawah), atau `axis=1` untuk menghitung **per baris** (ke samping). Contoh: `np.mean(matriks, axis=0)`.

**Soal 5**
Diberikan data nilai ETS kelas Statistika Bisnis:
`nilai_ets = np.array([65, 78, 92, 84, 55, 88, 76, 95, 70])`

Gunakan fungsi bawaan NumPy untuk menghitung dan mencetak:
1. Nilai rata-rata (*mean*)
2. Nilai tengah (*median*)
3. Nilai tertinggi (*max*) dan terendah (*min*)
4. Standar deviasi (*std*)

---

## 6. Filtering Data (*Boolean Indexing*)
Di modul sebelumnya, untuk menyaring data di dalam List kita harus menggabungkan `for loop` dan `if-else`. Di NumPy, kalian cukup memasukkan **kondisi logika langsung ke dalam kurung siku `[]`**! Teknik ini disebut *Boolean Indexing*.

```python
>>> skor = np.array([65, 80, 95, 50, 85])

# Langkah 1: Cek kondisi (menghasilkan array Boolean True/False)
>>> print(skor >= 75)
[False  True  True False  True]

# Langkah 2: Masukkan kondisi ke dalam kurung siku untuk menyaring data
>>> lulus = skor[skor >= 75]
>>> print(lulus)
[80 95 85]

# Menggabungkan 2 syarat (WAJIB pakai '&' untuk AND, '|' untuk OR, dan tanda kurung)
>>> rentang_baik = skor[(skor >= 75) & (skor <= 90)]
>>> print(rentang_baik)
[80 85]
```

**Notes:** Saat menggabungkan dua kondisi di dalam NumPy, **jangan** gunakan kata kunci `and` / `or` milik Python biasa, melainkan gunakan simbol **`&`** (untuk *and*) dan **`|`** (untuk *or*), serta bungkus masing-masing kondisi dengan tanda kurung `()`.

**Soal 6**
Sebuah toko mencatat omzet harian (dalam ribu rupiah) selama seminggu dalam bentuk NumPy array:
`omzet_harian = np.array([450, 620, 380, 750, 810, 500, 920])`

Buatlah program menggunakan NumPy (tanpa `for loop` sama sekali!) untuk:
1. Menghitung **total** dan **rata-rata** omzet selama seminggu.
2. Menyaring hari-hari yang mencapai target (omzet $\ge 600$) menggunakan *Boolean Indexing*, lalu simpan ke variabel `capai_target` dan cetak hasilnya.
3. Menghitung **berapa hari** toko tersebut berhasil mencapai target (Hint: gunakan fungsi `len()` pada variabel `capai_target`).
4. Memberikan proyeksi kenaikan omzet 15% untuk seluruh data di `omzet_harian` (kalikan dengan `1.15`), lalu cetak hasilnya!