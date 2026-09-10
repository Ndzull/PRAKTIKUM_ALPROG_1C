# Bilangan dan String

## Bilangan
Bilangan adalah tipe data yang digunakan untuk merepresentasikan nilai numerik. Dalam pemrograman Python, bilangan dapat dibagi menjadi beberapa jenis:

- **Integer (Bilangan Bulat)**
  ```python
  >>> int_var = 10
  >>> type(int_var)
  <class 'int'>
  ```

- **Float (Bilangan Desimal)**
  ```python
  >>> float_var = 3.14
  >>> type(float_var)
  <class 'float'>
  ```

- **Complex (Bilangan Kompleks)**
  ```python
  >>> complex_var = 2 + 3j
  >>> type(complex_var)
  <class 'complex'>
  ```

- **Boolean (True/False)**
  ```python
  >>> bool_var = True
  >>> type(bool_var)
  <class 'bool'>
  ```

### Operator Aritmatika (Arithmetic Operators)
Adapun operator aritmatika untuk mengoperasikan bilangan-bilangan tersebut, antara lain:

- **Penjumlahan (+)**
  ```python
  >>> 10 + 5
  15
  ```

- **Pengurangan (-)**
  ```python
  >>> 10 - 5
  5
  ```

- **Perkalian (*)**
  ```python
  >>> 10 * 5
  50
  ```

- **Pembagian (/)**
  ```python
  >>> 7 / 5
  1.4
  ```

- **Floor Division (//)**
  ```python
  >>> 7 // 5
  1
  ```

- **Modulus (%)**
  ```python
  >>> 7 % 5
  2
  ```

- **Pangkat (`**` atau `pow()`)**
  ```python
  >>> 10 ** 2
  100
  >>> pow(10, 2)
  100
  ```

- **Akar kuadrat (`** 0.5` atau `math.sqrt()`)**
  ```python
  >>> 16 ** 0.5
  4.0
  >>> import math
  >>> math.sqrt(16)
  4.0
  ```
<br>
<br>notes: pada python, perhitungan dieksekusi sesuai urutan operasi matematika, yaitu kurung, pangkat, perkalian/pembagian, penjumlahan/pengurangan.<br>
---
### Fungsi Numerik (Built-in Numeric Functions)
Python menyediakan beberapa fungsi numerik yang dapat digunakan untuk melakukan operasi pada bilangan, antara lain:
- **Fungsi `abs()`**: Mengembalikan nilai absolut dari sebuah bilangan.
  ```python
  >>> abs(-10)
  10
  ```
- **Fungsi `int()`**: Mengubah nilai menjadi bilangan bulat.
  ```python
  >>> int(3.14)
  3
  ```
- **Fungsi `float()`**: Mengubah nilai menjadi bilangan desimal.
  ```python
  >>> float(10)
  10.0
  ```
- **Fungsi `round()`**: Membulatkan bilangan ke jumlah desimal tertentu.
  ```python
  >>> round(3.14159, 2)
  3.14
  ```
- **Fungsi `math.ceil()`**: Mengembalikan bilangan bulat terkecil yang lebih besar atau sama dengan bilangan yang diberikan (memerlukan impor modul `math`).
  ```python
  >>> import math
  >>> math.ceil(3.2)
  4
  ```
- **Fungsi `math.floor()`**: Mengembalikan bilangan bulat terbesar yang lebih kecil atau sama dengan bilangan yang diberikan (memerlukan impor modul `math`).
  ```python
  >>> import math
  >>> math.floor(3.8)
  3
  ```
- **Fungsi `max()`**: Mengembalikan nilai maksimum dari sekumpulan bilangan.
  ```python
  >>> max(1, 5, 3)
  5
  ```
- **Fungsi `min()`**: Mengembalikan nilai minimum dari sekumpulan bilangan.
  ```python
  >>> min(1, 5, 3)
  1
  ```
- **Fungsi `sum()`**: Mengembalikan jumlah dari sekumpulan bilangan.
  ```python
  >>> sum([1, 2, 3, 4, 5])
  15
  ```
- **Fungsi `pow()`**: Mengembalikan hasil perpangkatan dari dua bilangan.
  ```python
  >>> pow(2, 3)
  8
  ```
- **Fungsi `math.sqrt()`**: Mengembalikan akar kuadrat dari sebuah bilangan (memerlukan impor modul `math`).
  ```python
  >>> import math
  >>> math.sqrt(16)
  4.0
  ```
- **Fungsi `math.factorial()`**: Mengembalikan faktorial dari sebuah bilangan (memerlukan impor modul `math`).
  ```python
  >>> import math
  >>> math.factorial(5)
  120
  ```
- **Fungsi `math.log()`**: Mengembalikan logaritma dari sebuah bilangan (memerlukan impor modul `math`).
  ```python
  >>> import math
  >>> math.log(100, 10)
  2.0
  ```
- **Fungsi `math.exp()`**: Mengembalikan nilai eksponensial dari sebuah bilangan (memerlukan impor modul `math`).
  ```python
  >>> import math
  >>> math.exp(2)
  7.38905609893065
  ```
- **Fungsi `math.sin()`, `math.cos()`, `math.tan()`**: Mengembalikan nilai sinus, kosinus, dan tangen dari sebuah sudut dalam radian (memerlukan impor modul `math`).
  ```python
  >>> import math
  >>> math.sin(math.pi / 2)
  1.0
  >>> math.cos(0)
  1.0
  >>> math.tan(math.pi / 4)
  0.9999999999999999
  ```
Dan masih banyak lagi fungsi numerik lainnya yang dapat digunakan sesuai kebutuhan kalian.
---

### Apa itu Variabel?
<p>
Variabel adalah tempat untuk menyimpan data atau nilai. Variabel dapat diibaratkan sebagai "wadah" yang dapat menampung berbagai jenis data, termasuk bilangan dan string.<br><br>
notes: Variabel di Python tidak memerlukan deklarasi tipe data secara eksplisit, karena Python menggunakan tipe data dinamis. Artinya, kalian bisa langsung memberikan nilai pada variabel tanpa harus menyebutkan tipe datanya.<br>
selain itu, python juga memiliki aturan penamaan variabel yang harus diikuti, seperti tidak boleh diawali dengan angka, tidak boleh menggunakan spasi, dan tidak boleh menggunakan karakter khusus kecuali underscore (_).<br>
Adapun case sensitif, artinya variabel dengan nama yang sama tetapi berbeda huruf besar/kecil dianggap sebagai variabel yang berbeda pula. Misalnya, `variabel` dan `Variabel` adalah dua variabel yang berbeda.<br>
Python sangat memperhatikan indentasi (spasi di awal baris) untuk menentukan blok kode. Jadi, pastikan kalian menggunakan indentasi yang konsisten saat menulis kode Python.<br></p>
---

### Operator Penugasan
Operator penugasan digunakan untuk memberikan nilai pada variabel. Beberapa operator penugasan yang umum digunakan antara lain:
- **Penugasan Sederhana (=)**
  ```python
  >>> x = 10
  >>> x
  10
  ```

- **Penugasan dengan Penjumlahan (+=)**
  ```python
  >>> x = 10
  >>> x += 5
  >>> x
  15
  ```

- **Penugasan dengan Pengurangan (-=)**
  ```python
  >>> x = 10
  >>> x -= 5
  >>> x
  5
  ```

- **Penugasan dengan Perkalian (*=)**
  ```python
  >>> x = 10
  >>> x *= 5
  >>> x
  50
  ```

- **Penugasan dengan Pembagian (/=)**
  ```python
  >>> x = 10
  >>> x /= 5
  >>> x
  2.0
  ```

- **Penugasan dengan Floor Division (//=)**
  ```python
  >>> x = 10
  >>> x //= 5
  >>> x
  2
  ```

- **Penugasan dengan Modulus (%=)**
  ```python
  >>> x = 10
  >>> x %= 5
  >>> x
  0
  ```

- **Penugasan dengan Pangkat (**=)**
  ```python
  >>> x = 10
  >>> x **= 2
  >>> x
  100
  ```

- **Penugasan dengan Akar Kuadrat (**= 0.5)**
  ```python
  >>> x = 16
  >>> x **= 0.5
  >>> x
  4.0
  ```
---
### Gimana cara menampilkannya di terminal?
Kalian bisa pake fungsi `print()` untuk menampilkan nilai dari variabel atau bilangan-bilangan tersebut ke layar.

```python
>>> hasil = 10 + 5
>>> print(hasil)
15
```

---

## String
String adalah tipe data yang digunakan untuk merepresentasikan teks. String dapat terdiri dari satu atau lebih karakter, termasuk huruf, angka, dan simbol. Dalam pemrograman, string biasanya didefinisikan dengan menggunakan tanda kutip tunggal (`' '`) atau tanda kutip ganda (`" "`).

```python
>>> teks_satu = 'Ini menggunakan kutip tunggal'
>>> teks_dua = "Ini menggunakan kutip ganda"
>>> type(teks_satu)
<class 'str'>
```
---
### Variabel String
Kalian bisa menyimpan string ke dalam variabel, sama seperti bilangan. Berikut contohnya:
```python
>>> nama = "Ijul Chlea"
>>> print(nama)
Ijul Chlea
---
### Operator String
Operator string digunakan untuk melakukan operasi pada string, seperti penggabungan (concatenation) dan pengulangan (repetition). Beberapa operator string yang umum digunakan antara lain:
- **Penggabungan (+)**
  ```python
  >>> str1 = "Hello"
  >>> str2 = "World"
  >>> hasil = str1 + " " + str2
  >>> print(hasil)
  Hello World
  ```
- **Pengulangan (*)**
  ```python
  >>> str1 = "Hello"
  >>> hasil = str1 * 3
  >>> print(hasil)
  HelloHelloHello
  ```
- **Pengecekan Keanggotaan (in)**
  ```python
  >>> str1 = "Hello World"
  >>> "Hello" in str1
  True
  >>> "Python" in str1
  False
  ```
- **Menghitung Panjang String (len())**
  ```python
  >>> str1 = "Hello World"
  >>> panjang = len(str1)
  >>> print(panjang)
  11
  ```
---
### Indexing dan Slicing
String di Python dapat diakses menggunakan indexing dan slicing. Indexing digunakan untuk mengakses karakter tertentu dalam string, sedangkan slicing digunakan untuk mengambil sebagian dari string.
<br><br>
note: Indexing dimulai dari 0 untuk karakter pertama, dan dapat menggunakan indeks negatif untuk mengakses karakter dari akhir string.
<br><br>
- **Indexing**

  ```python
  >>> str1 = "Hello World"
  >>> print(str1[0])  # Mengakses karakter pertama
  H
  >>> print(str1[-1])  # Mengakses karakter terakhir
  d
  ```
- **Slicing**
  ```python
  >>> str1 = "Hello World"
  >>> print(str1[0:5])  # Mengambil karakter dari index 0 hingga 4
  Hello
  >>> print(str1[6:])  # Mengambil karakter dari index 6 hingga akhir
  World
  >>> print(str1[:5])  # Mengambil karakter dari awal hingga index 4
  Hello
  >>> print(str1[::2])  # Mengambil karakter dengan langkah 2
  HloWrd
  ```
---

### Fungsi String (Built-in String Functions)
Python menyediakan berbagai fungsi bawaan untuk memanipulasi string. Beberapa fungsi string yang umum digunakan antara lain:
- **Fungsi `upper()`**: Mengubah semua huruf dalam string menjadi huruf besar.
  ```python
  >>> teks = "hello world"
  >>> teks.upper()
  'HELLO WORLD'
  ```
- **Fungsi `lower()`**: Mengubah semua huruf dalam string menjadi huruf kecil.
  ```python
  >>> teks = "HELLO WORLD"
  >>> teks.lower()
  'hello world'
  ```
- **Fungsi `capitalize()`**: Mengubah huruf pertama dalam string menjadi huruf besar dan sisanya menjadi huruf kecil.
  ```python
  >>> teks = "hello world"
  >>> teks.capitalize()
  'Hello world'
  ```
- **Fungsi `title()`**: Mengubah huruf pertama dari setiap kata dalam string menjadi huruf besar.
  ```python
  >>> teks = "hello world"
  >>> teks.title()
  'Hello World'
  ```
- **Fungsi `strip()`**: Menghapus spasi di awal dan akhir string.
  ```python
  >>> teks = "   hello world   "
  >>> teks.strip()
  'hello world'
  ```
- **Fungsi `replace()`**: Mengganti substring tertentu dalam string dengan substring lain.
  ```python
  >>> teks = "hello world"
  >>> teks.replace("world", "Python")
  'hello Python'
  ```
- **Fungsi `split()`**: Memisahkan string menjadi daftar berdasarkan pemisah tertentu.
  ```python
  >>> teks = "hello world"
  >>> teks.split(" ")
  ['hello', 'world']
  ```
- **Fungsi `join()`**: Menggabungkan elemen-elemen dalam daftar menjadi string dengan pemisah tertentu.
  ```python
  >>> daftar = ['hello', 'world']
  >>> " ".join(daftar)
  'hello world'
  ```

- **Fungsi `find()`**: Mengembalikan indeks dari substring pertama yang ditemukan dalam string. Jika substring tidak ditemukan, mengembalikan -1.
  ```python
  >>> teks = "hello world"
  >>> teks.find("world")
  6
  >>> teks.find("Python")
  -1
  ```
- **Fungsi `count()`**: Menghitung jumlah kemunculan substring dalam string.
  ```python
  >>> teks = "hello world"
  >>> teks.count("o")
  2
  >>> teks.count("Python")
  0
  ```
---




<br><br><br>
##TUGAS HEHEHE
akses lah soal berikut ini : <br> https://docs.google.com/document/d/1UIGhq1tGzRhm_bKKl8NCkBdIOG8oO3nWWbQUqNhN3N8/edit?usp=sharing


<br><br>
<b>DEADLINE: 20 September 2026, 23:59 WIB</b>
<br><br>
Kumpulin link repo/github kalian di spreadsheet:<br> https://docs.google.com/spreadsheets/d/1w_7-4rPP-2dWpsEoD6EZ1fd0WEB08PfHxuweXVvJzJ4/edit?usp=sharing