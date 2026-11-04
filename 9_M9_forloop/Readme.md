# Perulangan (For Loop)

Dalam pemrograman, ada prinsip yang sangat terkenal yaitu **DRY (Don't Repeat Yourself)**. Bayangkan kalian harus mencetak tulisan "Saya Mahasiswa ITS" sebanyak 100 kali. Menuliskan `print()` sebanyak 100 baris tentu sangat tidak efisien, bukan?

Di sinilah **Perulangan (Loop)** berperan. Loop memungkinkan kita menjalankan satu blok kode berulang kali secara otomatis. Pada modul ini, kita akan fokus pada **For Loop**, yaitu perulangan yang digunakan ketika kita sudah tahu secara pasti berapa kali kode tersebut harus diulang, atau saat kita ingin menelusuri isi dari sebuah List, Tuple, maupun String.

---

## 1. Iterasi pada Koleksi Data (List / Tuple)
Di Python, `for` loop sangat sering digunakan untuk menelusuri (*iterating*) elemen-elemen di dalam List atau Tuple satu per satu dari awal hingga akhir. Sebelumnya kalian sudah beberapa kali menggunakan `for` loop untuk menelusuri List pada materi sebelumnya.

```python
>>> daftar_buah = ["Apel", "Mangga", "Jeruk"]

>>> for buah in daftar_buah:
...     print(f"Saya suka makan {buah}")
... 
Saya suka makan Apel
Saya suka makan Mangga
Saya suka makan Jeruk
```
**Notes:** Variabel `buah` pada contoh di atas adalah variabel sementara (bebas diberi nama apa saja) yang mewakili nilai dari setiap elemen pada saat perulangan sedang berjalan. Jangan lupa gunakan **indentasi** (spasi/tab) di dalam blok `for`!

**Soal 1**
Diberikan list `nilai_kuis = [80, 75, 90, 65]`. Dosen memutuskan untuk memberikan bonus 5 poin untuk setiap mahasiswa. Gunakan `for loop` untuk menelusuri list tersebut, tambahkan setiap nilai dengan 5, dan cetak hasilnya satu per satu.

---

## 2. Menggunakan Fungsi `range()`
Bagaimana jika kita ingin mengulang kode beberapa kali, tapi kita tidak punya List? Kita bisa menggunakan fungsi `range()`. Fungsi ini akan menghasilkan deret angka.

- `range(stop)`: Mulai dari 0 sampai sebelum angka *stop*.
- `range(start, stop)`: Mulai dari *start* sampai sebelum *stop*.
- `range(start, stop, step)`: Mulai dari *start* sampai sebelum *stop*, dengan kelipatan *step*.

```python
# Mengulang 3 kali (menghasilkan angka 0, 1, 2)
>>> for i in range(3):
...     print(f"Perulangan ke-{i}")
... 
Perulangan ke-0
Perulangan ke-1
Perulangan ke-2

# Menghasilkan angka 1 sampai 5
>>> for i in range(1, 6):
...     print(i, end=" ")
... 
1 2 3 4 5 

# Menghasilkan angka ganjil dengan jarak/step 2
>>> for i in range(1, 10, 2):
...     print(i, end=" ")
... 
1 3 5 7 9 
```

**Soal 2**
Gunakan `for loop` dan fungsi `range()` untuk mencetak angka **kelipatan 3**, dimulai dari angka 1 dan diakhiri di angka 30 (angka 30 harus ikut tercetak). Cetak hasilnya memanjang ke samping menggunakan parameter `end=" "` (spasi).

---

## 3. Iterasi pada String
String pada dasarnya adalah kumpulan karakter. Oleh karena itu, kita juga bisa menggunakan `for loop` untuk mengambil hurufnya satu per satu.

```python
>>> nama_kampus = "ITS"

>>> for huruf in nama_kampus:
...     print(huruf)
... 
I
T
S
```

**Soal 3**
Diberikan sebuah string `teks = "STATISTIKA BISNIS"`. Gunakan `for loop` untuk mencetak setiap hurufnya satu per satu, **TETAPI** ubah setiap huruf tersebut menjadi huruf kecil terlebih dahulu.

---

## 4. Mengontrol Loop (`break` dan `continue`)
Terkadang, kita ingin menghentikan perulangan di tengah jalan, atau melompati satu putaran tertentu berdasarkan suatu kondisi. Kita bisa menggunakan `break` dan `continue`.

- **`break`**: Menghentikan perulangan sepenuhnya secara paksa.
- **`continue`**: Menghentikan putaran yang *sedang berjalan* dan langsung melompat ke putaran berikutnya.

```python
# Contoh penggunaan BREAK
>>> for i in range(1, 10):
...     if i == 4:
...         break  # Loop berhenti total saat i = 4
...     print(i, end=" ")
... 
1 2 3 

# Contoh penggunaan CONTINUE
>>> for i in range(1, 6):
...     if i == 3:
...         continue # Melompati angka 3
...     print(i, end=" ")
... 
1 2 4 5 
```

**Soal 4**
Diberikan list `peserta = ["Ijul", "Chlea", "Reza", "Citra", "Budi"]`. Buatlah `for loop` untuk mencetak nama peserta. JIKA nama peserta adalah `"Reza"`, gunakan statement `continue` untuk melompatinya agar nama tersebut tidak ikut tercetak.

---

## 5. Nested For Loop (Perulangan Bersarang)
Sama seperti *If-Else*, kita juga bisa memasukkan Loop di dalam Loop yang lain. Perulangan di dalam (inner loop) akan diselesaikan sepenuhnya terlebih dahulu sebelum perulangan di luar (outer loop) berlanjut ke langkah berikutnya. Teknik ini sangat berguna untuk membuat kombinasi data atau memanipulasi baris dan kolom.

```python
>>> warna = ["Merah", "Biru"]
>>> barang = ["Baju", "Topi"]

>>> for w in warna:
...     for b in barang:
...         print(w, b)
... 
Merah Baju
Merah Topi
Biru Baju
Biru Topi
```

**Soal 5**
Kalian memiliki dua buah list:
- `departemen = ["Statbis", "Statistika", "Matematika"]`
- `angkatan = [2025, 2026]`

Gunakan *Nested For Loop* untuk mencetak seluruh kombinasi kemungkinan antara departemen dan angkatan (contoh output: `"Statbis angkatan 2025"`, `"Statbis angkatan 2026"`, dst). Gunakan F-String agar hasil cetakannya rapi.

# Kombinasi For Loop, If-Else, dan Logika

Di dunia nyata, data jarang sekali hanya dicetak begitu saja. Biasanya, kita harus **menelusuri data** (menggunakan *For Loop*), lalu **menyaring atau mengambil keputusan** dari data tersebut (menggunakan *If-Else* dan *Logika*). 

Kombinasi dari ketiga materi inilah yang menjadi fondasi utama dalam ilmu Data Science dan pemrograman analisis bisnis. Mari kita bedah melalui 3 studi kasus berikut.

---

## Case 1
**Konsep:** `For Loop` + `If-Elif-Else` + Operator Logika `and`

Pada kasus ini, kita memiliki sekumpulan data mahasiswa. Kita ingin menelusuri data tersebut satu per satu menggunakan `for`, lalu mengecek dua syarat sekaligus menggunakan operator `and` untuk menentukan status kelulusannya.

```python
# List of tuple: (Nama, Nilai Ujian, Kehadiran)
data_mahasiswa = [
    ("Ijul", 85, 90),
    ("Andi", 65, 85),
    ("Budi", 90, 75),
    ("Citra", 75, 80)
]

print("=== HASIL EVALUASI KELAS ===")
for nama, nilai, hadir in data_mahasiswa:
    # Syarat lulus: nilai >= 70 DAN kehadiran >= 80
    if nilai >= 70 and hadir >= 80:
        status = "LULUS"
    # Remedial jika nilai kurang, TAPI kehadiran rajin
    elif nilai < 70 and hadir >= 80:
        status = "REMEDIAL UJIAN"
    else:
        status = "TIDAK LULUS (ALFA)"
        
    print(f"Mahasiswa: {nama:<6} | Status: {status}")
```
**Output:**
```text
=== HASIL EVALUASI KELAS ===
Mahasiswa: Ijul   | Status: LULUS
Mahasiswa: Andi   | Status: REMEDIAL UJIAN
Mahasiswa: Budi   | Status: TIDAK LULUS (ALFA)
Mahasiswa: Citra  | Status: LULUS
```

**Soal 6**
Kalian memiliki data pelamar asisten: `pelamar = [("Budi", 3.2, 5), ("Siti", 3.6, 3), ("Dodi", 3.8, 1)]` yang berisi (Nama, IPK, Semester). 
Gunakan `for loop` dan `if-else`. Seorang pelamar akan diterima jika IPK-nya **lebih besar atau sama dengan 3.5** DAN semesternya **lebih besar dari 2**. Cetak nama pelamar dan statusnya (Diterima/Ditolak)!

---

## Case 2
**Konsep:** `For Loop` + `If` + Operator Logika `or` (atau `in`)

Sebagai analis data, kalian sering diminta untuk menjumlahkan pengeluaran, tetapi **hanya untuk kategori tertentu**. Di sini kita menggunakan perulangan untuk menelusuri transaksi, dan operator `or` (atau `in`) untuk memfilter kategori yang akan dijumlahkan.

```python
# List of tuple: (Nama Barang, Kategori, Harga)
transaksi = [
    ("Laptop", "Elektronik", 12000000),
    ("Kemeja", "Pakaian", 250000),
    ("Mouse", "Aksesori", 150000),
    ("Celana", "Pakaian", 300000),
    ("Keyboard", "Aksesori", 450000)
]

total_pengeluaran = 0

print("=== REKAP BIAYA PERALATAN IT ===")
for barang, kategori, harga in transaksi:
    # Hanya memproses jika kategori Elektronik ATAU Aksesori
    if kategori == "Elektronik" or kategori == "Aksesori":
        total_pengeluaran += harga
        print(f"[+] {barang:<10}: Rp{harga:,}")

print("-" * 30)
print(f"Total Biaya : Rp{total_pengeluaran:,}")
```
**Output:**
```text
=== REKAP BIAYA PERALATAN IT ===
[+] Laptop    : Rp12,000,000
[+] Mouse     : Rp150,000
[+] Keyboard  : Rp450,000
------------------------------
Total Biaya : Rp12,600,000
```

**Soal 7**
Diberikan data pegawai: `karyawan = [("Joko", "IT", 7000), ("Rina", "HR", 5000), ("Toni", "Data", 8000), ("Lia", "IT", 6500)]`.
Buatlah program untuk menghitung **Total Gaji** HANYA untuk karyawan yang bekerja di departemen `"IT"` atau `"Data"`. Cetak total gaji akhirnya saja!

---

## Case 3
**Konsep:** `For Loop` + `If-Else` + Operator Logika `not`

Dalam sistem gudang, kita harus memberi peringatan jika stok menipis. Namun, kita **tidak perlu** memesan barang jika barang tersebut statusnya sudah dihentikan produksinya (*discontinued*). Kita menggunakan logika `not` untuk membalikkan status boolean.

```python
# List of tuple: (Nama Barang, Jumlah Stok, Is_Discontinued)
stok_gudang = [
    ("Buku Tulis", 50, False),  
    ("Pensil 2B", 8, False),
    ("Penggaris", 3, True),     # True = Sudah tidak diproduksi
    ("Spidol", 5, False)
]

stok_minimal = 10

print("=== SISTEM PERINGATAN GUDANG ===")
for nama, stok, is_discontinued in stok_gudang:
    
    # Peringatan re-order jika stok kurang DAN produk MASIH diproduksi (NOT discontinued)
    if stok < stok_minimal and not is_discontinued:
        print(f"PERINGATAN : Stok {nama} tinggal {stok}! Segera re-order.")
        
    # Peringatan khusus jika stok habis tapi produk sudah discontinued
    elif is_discontinued and stok < stok_minimal:
        print(f"INFO       : Stok {nama} sisa {stok} (Produk sudah tidak diproduksi).")
        
    # Jika stok masih di atas batas minimal
    else:
        print(f"AMAN       : {nama} ({stok} unit).")
```
**Output:**
```text
=== SISTEM PERINGATAN GUDANG ===
AMAN       : Buku Tulis (50 unit).
PERINGATAN : Stok Pensil 2B tinggal 8! Segera re-order.
INFO       : Stok Penggaris sisa 3 (Produk sudah tidak diproduksi).
PERINGATAN : Stok Spidol tinggal 5! Segera re-order.
```

**Soal 8**
Diberikan data penjualan: `penjualan = [("Kopi", 60, False), ("Teh", 30, False), ("Boba", 80, True)]` yang berisi (Nama Minuman, Jumlah Terjual, Sedang Promo).
Sebuah minuman dianggap laku keras murni jika terjual **lebih dari 50 cup** DAN **TIDAK sedang dalam masa promo**. Gunakan loop, if, dan logika `not` untuk mendeteksi minuman mana yang memenuhi kriteria tersebut, lalu cetak nama minumannya!