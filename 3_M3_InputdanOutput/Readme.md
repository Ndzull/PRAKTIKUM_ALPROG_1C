# Modul 3: Input dan Output

Dalam pembuatan program, kita pasti membutuhkan cara untuk berinteraksi dengan pengguna (*user*). Kita perlu menampilkan hasil pemrosesan (Output) dan menerima data atau perintah dari pengguna (Input).

---

## 1. Input (Menerima Data)
Untuk menerima masukan dari pengguna saat program sedang berjalan, kita menggunakan fungsi `input()`. 

**Note:** Secara *default*, semua data yang ditangkap oleh fungsi `input()` akan selalu dianggap sebagai **String** (`str`), meskipun pengguna memasukkan sebuah angka!

---

### Penggunaan Dasar `input()`

```python
>>> nama_pengguna = input("Masukkan nama Anda: ")
Masukkan nama Anda: Andi

>>> print(f"Selamat datang di kelas, {nama_pengguna}!")
Selamat datang di kelas, Andi!
```

---

### Type Casting (Mengubah Tipe Data Input)
Karena `input()` selalu menghasilkan string, jika kita ingin meminta pengguna memasukkan angka untuk keperluan operasi matematika (misalnya menghitung rata-rata nilai, atau memasukkan jumlah sampel observasi), kita harus mengubahnya (*casting*) menjadi tipe data numerik seperti `int` (bilangan bulat) atau `float` (bilangan desimal) terlebih dahulu.

```python
# Meminta input angka dan langsung mengubahnya ke integer (int)
>>> jumlah_data = int(input("Masukkan jumlah observasi: "))
Masukkan jumlah observasi: 32

>>> print(type(jumlah_data))
<class 'int'>

# Contoh kasus: Operasi matematika dengan input float dan int
>>> harga = float(input("Masukkan harga barang: "))
Masukkan harga barang: 50000.50

>>> jumlah_beli = int(input("Masukkan jumlah beli: "))
Masukkan jumlah beli: 3

>>> total_bayar = harga * jumlah_beli
>>> print(f"Total yang harus dibayar: Rp{total_bayar}")
Total yang harus dibayar: Rp150001.5
```

---

## 2. Output (Menampilkan Data)
Di Python, kita menggunakan fungsi `print()` untuk menampilkan teks, angka, atau isi dari sebuah variabel ke layar (terminal).

---

### Penggunaan Dasar `print()`
```python
>>> nama = "Ijul"
>>> print("Halo,", nama)
Halo, Ijul
```

---

### Parameter `sep` dan `end`
Secara bawaan (*default*), jika kita mencetak beberapa nilai sekaligus, `print()` akan memisahkan setiap nilai dengan spasi, dan selalu mengakhiri cetakan dengan baris baru (*enter/newline*). Kita bisa mengubah perilaku ini menggunakan parameter `sep` (*separator*) dan `end`.

```python
# Mengubah pemisah (separator) menjadi garis strip
>>> print("Statistika", "Bisnis", "ITS", sep="-")
Statistika-Bisnis-ITS

# Mengubah akhiran (end) agar tidak pindah baris
>>> print("Data pertama", end=" | ")
>>> print("Data kedua")
Data pertama | Data kedua
```

---

### F-String (Formatted String)
F-string adalah cara paling modern, rapi, dan direkomendasikan di Python untuk menyisipkan nilai variabel ke dalam string. Cukup tambahkan huruf `f` di depan tanda kutip, lalu masukkan variabel ke dalam kurung kurawal `{}`.

```python
>>> produk = "Laptop"
>>> harga = 15000000
>>> print(f"Harga {produk} adalah Rp{harga}")
Harga Laptop adalah Rp15000000
```

---

### Formatting output (Escape Character)
Kita juga bisa menggunakan *escape character* untuk mengatur format tampilan output. Beberapa *escape character* yaitu:

---

- `\n` : pindah ke baris baru (*new line*)
```python
>>> print("Halo!\nSelamat datang di kelas Statistika Bisnis ITS.")
Halo!
Selamat datang di kelas Statistika Bisnis ITS.
```

---

- `\t` : tabulasi vertikal (*tab space*)
```python
>>> print("Nama\t: Ijul\nNRP\t: 123456789")
Nama    : Ijul
NRP     : 123456789
```

---

- `\v` : tabulasi horizontal (*vertical tab space*)
```python
>>> print("Halo!\vSelamat datang di kelas Statistika Bisnis ITS.")
Halo!
Selamat datang di kelas Statistika Bisnis ITS.
```

---

- `\\` : menampilkan karakter backslash (`\`)
```python
>>> print("C:\\Users\\Ijul\\Documents")
C:\Users\Ijul\Documents
```

---

- `\"` : menampilkan tanda kutip ganda (`"`)
```python
>>> print("Chlea berkata, \"Halo!\"")
Chlea berkata, "Halo!"
```

---

- `\'` : menampilkan tanda kutip tunggal (`'`)
```python
>>> print('Chlea berkata, \'Halo!\'')
Chlea berkata, 'Halo!'
```

---

- `\r` : carriage return, mengembalikan kursor ke awal baris
```python
>>> print("Halo!\rSelamat datang di kelas Statistika Bisnis ITS.")
Selamat datang di kelas Statistika Bisnis ITS.
```

---

### Formating output (justifikasi teks)
Kita juga bisa mengatur *justifikasi* teks (rata kiri, rata kanan, atau rata tengah) menggunakan *formatting string*.

---

### Metode format
```python
>>> print(f"{'Nama':<10} {'NRP':<10} {'Kelas':<10}")
Nama       NRP        Kelas
>>> print(f"{'Ijul':<10} {'123456789':<10} {'Statistika':<10}")
Ijul       123456789  Statistika
>>> print(f"{'Ijul':>10} {'123456789':>10} {'Statistika':>10}")
      Ijul 123456789 Statistika
>>> print(f"{'Ijul':^10} {'123456789':^10} {'Statistika':^10}")
   Ijul    123456789 Statistika
```

---

### Metode argumen fungsi
bisa juga menggunakan beberapa argumen sseperti center, left, right, dan width untuk mengatur posisi teks.
```python
>>> print(lstr.center(20, "-"))
---------Ijul---------
>>> print(lstr.ljust(20, "-"))
Ijul------------------
>>> print(lstr.rjust(20, "-"))
------------------Ijul
```

---

### Format angka
Kita juga bisa mengatur format angka, misalnya menampilkan angka dengan jumlah digit tertentu,
```python
>>> angka = 123.456789
>>> print(f"{angka:.2f}")  # Menampilkan 2 digit di belakang koma
123.46
>>> print(f"{angka:.4f}")  # Menampilkan 4 digit di belakang koma
123.4568
>>> print(f"{angka:,.2f}")  # Menampilkan angka dengan pemisah ribuan dan 2 digit di belakang koma
123.456,79
>>> print(f"{angka:,.4f}")  # Menampilkan angka dengan pemisah ribuan dan 4 digit di belakang koma
123.456,7890
```
---
<br>
KERJAKAN SOAL PADA LINK BERIKUT: <br>
[Soal Modul 3](https://docs.google.com/document/d/1UIGhq1tGzRhm_bKKl8NCkBdIOG8oO3nWWbQUqNhN3N8/edit?tab=t.a03w0sdtbszu)
<br>
<b>DEADLINE PENGUMPULAN: 20 September 2026, 23.59 WIB</b>
<br>
LINK PENGUMPULAN: <br>
[Link Pengumpulan](https://docs.google.com/spreadsheets/d/1w_7-4rPP-2dWpsEoD6EZ1fd0WEB08PfHxuweXVvJzJ4/edit?gid=62181998#gid=62181998)