# Modul 3: Input dan Output

Dalam pembuatan program, kita pasti membutuhkan cara untuk berinteraksi dengan pengguna (*user*). Kita perlu menampilkan hasil pemrosesan (Output) dan menerima data atau perintah dari pengguna (Input).

## 1. Output (Menampilkan Data)
Di Python, kita menggunakan fungsi `print()` untuk menampilkan teks, angka, atau isi dari sebuah variabel ke layar (terminal).

### Penggunaan Dasar `print()`
```python
>>> nama = "Ijul"
>>> print("Halo,", nama)
Halo, Ijul
```

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

### F-String (Formatted String)
F-string adalah cara paling modern, rapi, dan direkomendasikan di Python untuk menyisipkan nilai variabel ke dalam string. Cukup tambahkan huruf `f` di depan tanda kutip, lalu masukkan variabel ke dalam kurung kurawal `{}`.

```python
>>> produk = "Laptop"
>>> harga = 15000000
>>> print(f"Harga {produk} adalah Rp{harga}")
Harga Laptop adalah Rp15000000
```

### Formatting output
Contoh lain penggunaan f-string untuk menampilkan angka dengan format tertentu, misalnya menampilkan angka desimal dengan dua tempat di belakang koma:

```python
>>> print(f"Nilai pi: {pi:.2f}")
Nilai pi: 3.14
```
<br>
adapun karakter khusus yang bisa digunakan dalam string,
seperti '/n' untuk baris baru, dan '/t' untuk tabulasi.

```python
>>> print("Nama\t: Ijul\nNRP\t: 123456789")
Nama    : Ijul
NRP     : 123456789
```


---

## 2. Input (Menerima Data)
Untuk menerima masukan dari pengguna saat program sedang berjalan, kita menggunakan fungsi `input()`. 

**Note:** Secara *default*, semua data yang ditangkap oleh fungsi `input()` akan selalu dianggap sebagai **String** (`str`), meskipun pengguna memasukkan sebuah angka!

### Penggunaan Dasar `input()`

```python
>>> nama_pengguna = input("Masukkan nama Anda: ")
Masukkan nama Anda: Andi

>>> print(f"Selamat datang di kelas, {nama_pengguna}!")
Selamat datang di kelas, Andi!
```

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