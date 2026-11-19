# Class dan Object 

Selamat datang di paradigma pemrograman baru! Sejauh ini, kita menulis kode dari atas ke bawah secara berurutan. Pendekatan ini disebut pemrograman prosedural. 

Sekarang, kita akan masuk ke **Pemrograman Berorientasi Objek (OOP)**. Bayangkan kalian sedang membuat pabrik robot atau membuat game. Daripada mencatat data satu per satu, akan lebih mudah jika kita membuat **Blueprint**. 

- **Class**: Adalah blueprint atau rancangan. (Contoh: Cetakan kue, atau gambar desain mobil).
- **Object**: Adalah benda nyata yang dihasilkan dari cetakan tersebut. (Contoh: Kue hasil cetakan, atau mobil fisik yang sudah jadi).

---

## 1. Membuat Class dan Object
Untuk membuat *Class*, kita menggunakan kata kunci `class` (biasanya diawali huruf kapital). Sedangkan untuk membuat *Object*, kita memanggil nama class tersebut seperti memanggil sebuah fungsi.

```python
# 1. MEMBUAT CLASS (Cetakan)
>>> class Kucing:
...     pass  # 'pass' digunakan jika class belum ada isinya
... 

# 2. MEMBUAT OBJECT (Benda Nyata)
>>> kucing_oyen = Kucing()
>>> kucing_putih = Kucing()

>>> print(type(kucing_oyen))
<class '__main__.Kucing'>
```
**Notes:** `kucing_oyen` dan `kucing_putih` adalah dua objek yang berbeda, meskipun mereka dicetak dari class `Kucing` yang sama.

---

## 2. Atribut (Sifat/Karakteristik) & Fungsi `__init__`
Setiap objek pasti punya sifat/karakteristik. Kucing punya nama dan warna. Mobil punya merk dan kecepatan. Dalam OOP, karakteristik ini disebut **Atribut**.

Untuk memberikan atribut sejak awal objek diciptakan, kita wajib menggunakan fungsi khusus bernama `__init__` (kependekan dari *initialize*). 

**Notes:** Parameter pertama di dalam fungsi/metode class WAJIB bernama **`self`**. `self` ini mewakili objek itu sendiri.

```python
>>> class Mahasiswa:
...     # Fungsi yang otomatis berjalan saat objek dibuat
...     def __init__(self, nama, prodi):
...         self.nama = nama
...         self.prodi = prodi
... 

# Membuat objek sambil memasukkan argumen atributnya
>>> mhs1 = Mahasiswa("Ijul", "Statistika Bisnis")
>>> mhs2 = Mahasiswa("Budi", "Informatika")

# Mengakses atribut objek menggunakan tanda titik (.)
>>> print(mhs1.nama)
Ijul
>>> print(mhs2.prodi)
Informatika
```

**Soal 1**
Buatlah class `Karyawan` dengan fungsi `__init__` yang menerima parameter `self`, `nama`, dan `gaji`. Di dalamnya, simpan nilai tersebut ke dalam atribut `self.nama` dan `self.gaji`. 
Buatlah satu objek karyawan dengan nama `"Siti"` dan gaji `5000000`, lalu cetak kalimat `"Karyawan [nama] memiliki gaji [gaji]"` menggunakan *F-String* dan tanda titik!

---

## 3. Method (Perilaku/Aksi)
Selain atribut (sifat), objek juga bisa melakukan aksi. Kucing bisa mengeong, mahasiswa bisa belajar. Aksi ini pada dasarnya adalah **Fungsi yang diletakkan di dalam Class**. Dalam OOP, kita menyebutnya **Method**.

Ingat, setiap *method* juga WAJIB memiliki `self` sebagai parameter pertamanya agar bisa mengakses atribut dari objek miliknya.

```python
>>> class Robot:
...     def __init__(self, nama):
...         self.nama = nama
...         self.baterai = 100
...         
...     def menyapa(self):
...         print(f"Bip bop! Halo, saya {self.nama}.")
...         
...     def bekerja(self):
...         self.baterai -= 20
...         print(f"{self.nama} sedang bekerja. Sisa baterai: {self.baterai}%")
... 

>>> bot = Robot("Alpha")

# Memanggil method menggunakan tanda titik (.)
>>> bot.menyapa()
Bip bop! Halo, saya Alpha.

>>> bot.bekerja()
Alpha sedang bekerja. Sisa baterai: 80%
```

**Soal 2**
Modifikasi class `Karyawan` dari Soal sebelumnya. Tambahkan atribut default `self.energi = 100` di dalam `__init__`.
Lalu, buat sebuah method bernama `lembur(self)`. Method ini akan mencetak `f"{self.nama} sedang lembur!"`, mengurangi `self.energi` sebanyak `30`, dan menambah `self.gaji` sebesar `200000` sebagai uang lembur.
Buat objeknya (gunakan data Siti dari soal sebelumnya), panggil method `lembur()`, lalu cetak sisa energi dan gaji terbarunya!

---

## 4. Mengubah Nilai Atribut
Kalian bisa mengubah nilai atribut objek secara langsung dari luar class menggunakan operator sama dengan (`=`), persis seperti mengubah nilai variabel biasa.

```python
>>> class GameCharacter:
...     def __init__(self, nama, level):
...         self.nama = nama
...         self.level = level
... 

>>> hero = GameCharacter("Arthur", 1)
>>> print(hero.level)
1

# Mengubah atribut secara langsung
>>> hero.level = 10
>>> print(f"Level {hero.nama} naik menjadi {hero.level}!")
Level Arthur naik menjadi 10!
```

**Soal 3**
Kalian memiliki class `Barang` dengan atribut `nama` dan `harga`. Kalian membuat objek `baju` dengan harga awal `100000`. Tuliskan kode untuk mengubah atribut `harga` dari objek `baju` tersebut menjadi `75000` (diskon), lalu cetak harga terbarunya ke layar!

---

## 5. Studi Kasus (Final Boss): Simulasi Rekening Bank
Mari kita gabungkan Atribut dan Method ke dalam skenario dunia nyata yang sangat sering menggunakan konsep OOP: **Sistem Rekening Bank**.

**Soal 4**
Buatlah sebuah class bernama `RekeningBank`.
1. **Atribut (`__init__`)**: Memiliki parameter `nama_pemilik` dan `saldo` (nilai default `saldo = 0`).
2. **Method `menabung(self, nominal)`**: Menambahkan `nominal` ke dalam `self.saldo` dan mencetak: `"Berhasil menabung Rp[nominal]. Saldo sekarang: Rp[saldo]"`.
3. **Method `tarik_tunai(self, nominal)`**: Gunakan percabangan `if-else`.
   - Jika `saldo` mencukupi: Kurangi saldo dengan nominal, lalu cetak `"Berhasil menarik Rp[nominal]. Saldo sekarang: Rp[saldo]"`.
   - Jika tidak mencukupi: Cetak `"Maaf, saldo tidak mencukupi."`

**Tugas Ekseskusi:**
1. Buat objek rekening atas nama kalian dengan saldo awal `150000`.
2. Lakukan tarik tunai sebesar `50000`.
3. Coba tarik tunai lagi sebesar `200000`. 
4. Terakhir, menabunglah sebesar `300000`.