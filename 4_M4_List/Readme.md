# List

List adalah salah satu struktur data bawaan di Python yang digunakan untuk menyimpan sekumpulan item (data) dalam satu variabel. List bersifat terurut (*ordered*), dapat diubah nilainya (*mutable*), dan dapat berisi berbagai tipe data sekaligus (angka, string, boolean, bahkan list lain).

List dibuat dengan menggunakan tanda kurung siku `[]` dan setiap elemen di dalamnya dipisahkan oleh koma.

---

## 1. Membuat List
Kalian bisa membuat list kosong atau list yang sudah ada isinya.

```python
# Membuat list kosong
>>> list_kosong = []
>>> type(list_kosong)
<class 'list'>

# Membuat list dengan berbagai tipe data
>>> data_mahasiswa = ["Ijul", 2024, 3.85, True]
>>> print(data_mahasiswa)
['Ijul', 2024, 3.85, True]
```

### Soal latihan
1. Buatlah sebuah list yang berisi 4 elemen, masing-masing elemen memiliki tipe data yang berbeda (misalnya string, integer, float, dan boolean). Simpan list tersebut dalam variabel dengan nama bebas dan cetak isinya.
---

## 2. Mengakses Elemen List (indexing & slicing)
### Indexing
```python
>>> matkul = ["Kalkulus", "Alpro", "Statistika", "Basis Data"]
>>> print(matkul[0])
Kalkulus
>>> print(matkul[-1])
Basis Data
```

### Slicing
```python
>>> angka = [10, 20, 30, 40, 50, 60]
>>> print(angka[1:4])  # Mengambil elemen dari indeks 1 hingga 3
[20, 30, 40]
>>> print(angka[:3])   # Mengambil elemen dari awal hingga indeks 2
[10, 20, 30]
>>> print(angka[3:])   # Mengambil elemen dari indeks 3 hingga akhir
[40, 50, 60]
```

### Soal latihan
Diberikan list `huruf = ["A", "B", "C", "D", "E"]`. Tuliskan kode untuk mengambil huruf **"C"** menggunakan *indexing*, dan kode untuk mengambil list berisi **["B", "C", "D"]** menggunakan *slicing*!

## 3. Mengubah Elemen List (mutable)
List bersifat mutable, artinya kita bisa mengubah nilai elemen yang sudah ada dalam list.

```python
>>> buah = ["apel", "pisang", "jeruk"]
>>> print(buah)
['apel', 'pisang', 'jeruk']
>>> buah[1] = "mangga"
>>> print(buah)
['apel', 'mangga', 'jeruk']
```

### Soal latihan
Diberikan list `warna = ["merah", "hijau", "biru"]`. Ubah elemen kedua menjadi **"kuning"** dan cetak list tersebut.

## 4. Menambahkan Elemen List
Python menyediakan beberapa metode khusus untuk menambahkan data baru ke dalam list yang sudah ada.

- **`append()`**: Menambahkan satu elemen baru di posisi paling akhir.
  ```python
  >>> prodi = ["Statistika"]
  >>> prodi.append("Bisnis")
  >>> print(prodi)
  ['Statistika', 'Bisnis']
  ```

- **`insert()`**: Menambahkan elemen baru pada indeks tertentu. (Format: `insert(indeks, elemen)`).
  ```python
  >>> angka = [1, 2, 4]
  >>> angka.insert(2, 3)  # Menyisipkan angka 3 di indeks ke-2
  >>> print(angka)
  [1, 2, 3, 4]
  ```

- **`extend()`**: Menggabungkan elemen dari list lain ke dalam list saat ini.
  ```python
  >>> list_a = [1, 2]
  >>> list_b = [3, 4]
  >>> list_a.extend(list_b)
  >>> print(list_a)
  [1, 2, 3, 4]
  ```

### Soal latihan
Buatlah sebuah list kosong bernama `mata_kuliah`. Tambahkan tiga hobi favorit kalian ke dalam list tersebut menggunakan metode `append()`. Setelah itu, cetak isi list `mata_kuliah`.

---

## 5. Menghapus Elemen List
Python juga menyediakan beberapa metode untuk menghapus elemen dari list.

- **`remove()`**: Menghapus elemen berdasarkan nilainya (hanya elemen pertama yang ditemukan yang dihapus).
  ```python
  >>> data = ["A", "B", "C", "B"]
  >>> data.remove("B")
  >>> print(data)
  ['A', 'C', 'B']
  ```

- **`pop()`**: Menghapus elemen berdasarkan indeks dan mengembalikan nilai tersebut. Jika indeks dikosongkan, ia akan menghapus elemen paling akhir.
  ```python
  >>> matkul = ["Alpro", "Pelter", "Matematika"]
  >>> yang_dihapus = matkul.pop(1)
  >>> print(yang_dihapus)
    Pelter
  >>> print(matkul)
  ['Alpro', 'Matematika']
  ```

- **`clear()`**: Menghapus seluruh elemen di dalam list, menjadikannya list kosong.
  ```python
  >>> angka = [1, 2, 3, 4, 5]
  >>> angka.clear()
  >>> print(angka)
  []
  ```

- **Keyword `del`**: Menghapus elemen pada indeks tertentu atau menghapus variabel list secara keseluruhan.
  ```python
  >>> nama = ["Ijul", "Chlea", "Lea"]
  >>> del nama[1]
  >>> print(nama)
  ['Ijul', 'Lea']
  ```

### Soal latihan
Diberikan list `tugas = ["Matematika", "Fisika Terapan", "Peluang Terapan", "Kimia Terapan"]`. Hapus `"Fisika Terapan"` menggunakan `remove()`, lalu keluarkan elemen terakhir (`"Kimia Terapan"`) menggunakan `pop()`. Tampilkan sisa elemen dalam list!

---

## Fungsi dan Metode Bawaan Lainnya
- **`len()`**: Menghitung total jumlah elemen dalam list.
  ```python
  >>> nilai = [80, 90, 85, 100]
  >>> print(len(nilai))
  4
  ```

- **`sort()`**: Mengurutkan elemen dari yang terkecil ke terbesar (*Ascending*). Gunakan `reverse=True` untuk *Descending*. (Semua elemen dalam list harus memiliki tipe data yang sama agar bisa diurutkan).
  ```python
  >>> angka = [5, 2, 9, 1]
  >>> angka.sort()
  >>> print(angka)
  [1, 2, 5, 9]
  
  >>> angka.sort(reverse=True)
  >>> print(angka)
  [9, 5, 2, 1]
  ```

- **`reverse()`**: Membalikkan urutan elemen dalam list (elemen terakhir menjadi pertama, elemen pertama menjadi terakhir) tanpa mengurutkannya berdasarkan nilai.
  ```python
  >>> urutan = ["Pertama", "Kedua", "Ketiga"]
  >>> urutan.reverse()
  >>> print(urutan)
  ['Ketiga', 'Kedua', 'Pertama']
  ```

- **`count()`**: Menghitung berapa kali suatu nilai muncul di dalam list.
  ```python
  >>> jawaban = ["A", "B", "A", "C", "A"]
  >>> print(jawaban.count("A"))
  3
  ```

- **`index()`**: Mencari posisi indeks pertama dari sebuah nilai yang ditemukan di dalam list.
  ```python
  >>> prodi = ["Matematika", "Statistika", "Fisika"]
  >>> print(prodi.index("Statistika"))
  1
  ```

Diberikan list `angka_acak = [3, 1, 4, 1, 5, 9, 2, 6, 5]`. Gunakan kode Python untuk:
1. Mengurutkan list dari yang **terbesar ke terkecil**, cetak list yang sudah diurutkan.
2. Hitunglah ada berapa banyak angka **`5`** di dalam list tersebut, print hasilnya!
3. Jumlahkan semua elemen dalam list tersebut dan cetak hasilnya.