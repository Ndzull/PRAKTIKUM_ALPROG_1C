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

### Operator Aritmatika
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
  >>> 10 / 5
  2.0
  ```

- **Floor Division (//)**
  ```python
  >>> 10 // 5
  2
  ```

- **Modulus (%)**
  ```python
  >>> 10 % 5
  0
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

---

### Apa itu Variabel?
Variabel adalah tempat untuk menyimpan data atau nilai. Variabel dapat diibaratkan sebagai "wadah" yang dapat menampung berbagai jenis data, termasuk bilangan dan string.

### Gimana cara menampilkannya di terminal?
Kamu bisa menggunakan fungsi `print()` untuk menampilkan nilai dari variabel atau bilangan-bilangan tersebut ke layar.

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