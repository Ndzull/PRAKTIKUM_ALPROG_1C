# Tuple

Tuple adalah salah satu struktur data bawaan di Python yang sangat mirip dengan List, yaitu berfungsi untuk menyimpan sekumpulan item dalam satu variabel. 

Perbedaan utamanya adalah: **Tuple bersifat *immutable* (tidak dapat diubah)** setelah dibuat. Artinya, kalian tidak bisa menambah, menghapus, atau mengganti elemen di dalam tuple. Tuple sangat cocok digunakan untuk data yang sifatnya konstan/tetap (seperti koordinat lokasi, bulan dalam setahun, atau data konfigurasi).

Tuple dibuat dengan menggunakan tanda kurung biasa `()` dan setiap elemen di dalamnya dipisahkan oleh koma.

---

## 1. Membuat Tuple
Kalian bisa membuat tuple kosong, tuple dengan berbagai tipe data, atau tuple yang hanya berisi satu elemen.

```python
# Membuat tuple biasa
>>> data_dosen = ("Pak Budi", 1985, "Statistika")
>>> print(data_dosen)
('Pak Budi', 1985, 'Statistika')
>>> type(data_dosen)
<class 'tuple'>

>>> tuple_satu = ("Tunggal",)
>>> bukan_tuple = ("Tunggal")

>>> print(type(tuple_satu))
<class 'tuple'>
>>> print(type(bukan_tuple))
<class 'str'>
```

**Soal 1:**
Buatlah sebuah variabel tuple bernama `jadwal_hari` yang berisi nama-nama hari kerja (Senin sampai Jumat). Cetak tuple tersebut beserta tipe datanya untuk membuktikan bahwa itu benar-benar sebuah tuple.

---

## 2. Mengakses Elemen Tuple (Indexing & Slicing)
Sama persis seperti List dan String, kalian bisa mengakses data di dalam Tuple menggunakan *indexing* (berbasis 0) dan *slicing* menggunakan tanda kurung siku `[]`.

```python
>>> bulan = ("Jan", "Feb", "Mar", "Apr", "Mei", "Jun")

# Mengakses elemen dengan Indexing
>>> print(bulan[0])
Jan
>>> print(bulan[-1])
Jun

# Mengambil beberapa elemen dengan Slicing
>>> print(bulan[1:4])
('Feb', 'Mar', 'Apr')
```

**Soal 2:**
Diberikan tuple `koordinat = (10, 20, 30, 40, 50)`. Tuliskan kode untuk mengambil angka **30** menggunakan *indexing*, dan ambil angka **(40, 50)** menggunakan *slicing*!

---

## 3. Sifat Immutable (Tidak Dapat Diubah)
Karena Tuple bersifat *immutable*, kalian akan mendapatkan pesan *error* (TypeError) jika mencoba mengubah, menambah (`append`), atau menghapus (`remove`) nilainya.

```python
>>> warna = ("Merah", "Kuning", "Hijau")

# Jika kita mencoba mengubah nilainya:
>>> warna[0] = "Biru"
TypeError: 'tuple' object does not support item assignment
```

**Notes:** Sifat ini justru membuat eksekusi Tuple sedikit lebih cepat dibandingkan List di memori komputer, dan sangat aman dari perubahan data yang tidak disengaja.

**Soal 3:**
Coba ketikkan kode tuple `warna` di atas pada kode kalian, lalu cobalah ubah elemen indeks ke-1 menjadi `"Ungu"`. Amati pesan *error* yang muncul agar kalian terbiasa membaca *error* pada kode kalian

---

## 4. Fungsi dan Metode Bawaan Tuple
Karena tidak bisa diubah-ubah, metode bawaan pada Tuple sangat sedikit, yaitu hanya metode untuk mencari data.

- **`len()`**: Menghitung total jumlah elemen dalam tuple.
  ```python
  >>> angka = (1, 2, 3, 4)
  >>> print(len(angka))
  4
  ```

- **`count()`**: Menghitung berapa kali suatu nilai spesifik muncul di dalam tuple.
  ```python
  >>> nilai = (80, 90, 80, 100, 80)
  >>> print(nilai.count(80))
  3
  ```

- **`index()`**: Mencari posisi indeks pertama dari sebuah nilai yang ditemukan di dalam tuple.
  ```python
  >>> nama = ("Andi", "Budi", "Citra")
  >>> print(nama.index("Budi"))
  1
  ```

**Soal 4:**
Diberikan tuple `kumpulan_huruf = ("a", "b", "c", "a", "d", "a", "e")`. Gunakan metode bawaan tuple untuk mencari tahu di indeks ke berapa huruf **"d"** berada, dan berapa banyak huruf **"a"** di dalam tuple tersebut!

---

## 5. Tuple Unpacking (Membongkar Tuple)
*Tuple Unpacking* adalah fitur yang sangat keren dan sering digunakan di Python. Kalian bisa "membongkar" isi sebuah tuple dan memasukkan masing-masing nilainya ke dalam variabel yang berbeda hanya dalam satu baris kode.

```python
>>> data_mhs = ("Ijul", "Statistika Bisnis", 2024)

# Membongkar tuple ke dalam 3 variabel
>>> (nama, prodi, angkatan) = data_mhs

>>> print(nama)
Ijul
>>> print(prodi)
Statistika Bisnis
```
**Notes:** Jumlah variabel penampung di sebelah kiri **harus sama persis** dengan jumlah elemen di dalam tuple. Jika tidak, akan terjadi *error*.

**Soal 5:**
Diberikan tuple `titik_lokasi = (112.79, -7.28)`. Lakukan *unpacking* agar angka pertama masuk ke variabel `longitude` dan angka kedua masuk ke variabel `latitude`. Cetak kedua variabel tersebut secara terpisah

---

## 6. Mengubah Tuple (Casting)
Walaupun tuple *immutable*, ada kalanya kita tiba-tiba butuh mengubah isinya. Triknya adalah: Ubah dulu tuple menjadi list menggunakan fungsi `list()`, lakukan perubahan, lalu ubah kembali menjadi tuple menggunakan fungsi `tuple()`.

```python
>>> keranjang = ("Apel", "Jeruk")
>>> print(keranjang)
('Apel', 'Jeruk')

# Ubah ke list
>>> keranjang_list = list(keranjang)

# Modifikasi list
>>> keranjang_list.append("Mangga")

# Kembalikan menjadi tuple
>>> keranjang = tuple(keranjang_list)

>>> print(keranjang)
('Apel', 'Jeruk', 'Mangga')
```

**Soal 6:**
Diberikan tuple `kendaraan = ("Motor", "Mobil", "Sepeda")`. Gunakan trik *casting* untuk mengubah `"Mobil"` menjadi `"Bus"`, lalu kembalikan tipe datanya menjadi tuple dan cetak hasil akhirnya!