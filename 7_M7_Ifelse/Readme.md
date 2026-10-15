# Percabangan If-Else

Dalam kehidupan sehari-hari, kita sering membuat keputusan berdasarkan kondisi tertentu. Misalnya: "Jika hujan, maka saya bawa payung. Jika tidak, saya tidak bawa payung."

Dalam pemrograman Python, konsep pengambilan keputusan ini disebut **Percabangan** (*Conditional Statements*). Kita menggunakan hasil dari Operator Relasi dan Logika (yang bernilai `True` atau `False`) untuk menentukan blok kode mana yang akan dijalankan.

---

## 1. Statement `if` (Satu Kondisi)
Ini adalah bentuk percabangan paling dasar. Blok kode di dalam `if` HANYA akan dieksekusi jika kondisinya bernilai `True`. Jika `False`, program akan mengabaikannya dan lanjut ke baris berikutnya.

**Notes:** Perhatikan **indentasi** (spasi/tab di awal baris). Kode yang menjorok ke dalam menandakan bahwa kode tersebut adalah bagian dari blok `if`.

```python
>>> total_belanja = 150000

>>> if total_belanja > 100000:
...     print("Selamat! Anda mendapatkan diskon.")
... 
Selamat! Anda mendapatkan diskon.
```

**Soal 1**
Sebuah sistem kasir meminta input kode promo dari pelanggan. Jika pelanggan memasukkan kode `"STATBIS25"`, cetak pesan `"Kode valid, diskon 25% diterapkan!"`. Tuliskan kodenya menggunakan struktur `if`!

---

## 2. Statement `if-else` (Dua Kondisi)
Bagaimana jika kondisi `if` bernilai `False` dan kita ingin program melakukan hal lain? Kita gunakan `else`. 
`else` bertindak sebagai jalan keluar terakhir (jika semua kondisi di atasnya tidak terpenuhi).

```python
>>> nilai_ujian = 65
>>> kkm = 70

>>> if nilai_ujian >= kkm:
...     print("Anda Lulus!")
... else:
...     print("Anda harus mengikuti ujian perbaikan.")
... 
Anda harus mengikuti ujian perbaikan.
```

**Soal 2**
Sebuah toko kelontong mencatat variabel `pendapatan = 500000` dan `modal = 650000`. Buatlah program `if-else` untuk mengecek: jika pendapatan lebih besar dari modal, cetak `"Bisnis untung!"`. Namun jika sebaliknya (atau sama dengan), cetak `"Bisnis rugi atau balik modal."`

---

## 3. Statement `if-elif-else` (Lebih dari Dua Kondisi)
Jika kita memiliki tiga atau lebih kemungkinan, kita menggunakan `elif` (singkatan dari *else if*). Program akan mengecek kondisi dari paling atas ke bawah. Saat menemukan kondisi yang `True`, blok tersebut dijalankan dan sisanya diabaikan.

```python
>>> ipk = 3.8

>>> if ipk >= 3.5:
...     print("Predikat: Cumlaude")
... elif ipk >= 3.0:
...     print("Predikat: Sangat Memuaskan")
... elif ipk >= 2.5:
...     print("Predikat: Memuaskan")
... else:
...     print("Predikat: Cukup")
... 
Predikat: Cumlaude
```

**Soal 3**
Sebuah toko grosir mencatat stok barang. Terdapat ketentuan konversi: 1 lusin = 12 pcs, dan 1 kodi = 20 pcs.
Buatlah program yang meminta input **Jumlah Awal** (integer) dan **Satuan Awal** (string, pilihannya: "lusin" atau "kodi"). 
Gunakan `if-elif-else` untuk mengecek `Satuan Awal`:
- Jika "lusin", kalikan jumlah awal dengan 12 dan simpan ke variabel `total_pcs`.
- Jika "kodi", kalikan jumlah awal dengan 20 dan simpan ke variabel `total_pcs`.
- Jika selain keduanya, cetak `"Error: Satuan tidak dikenal"`.

Jika berhasil, cetak hasilnya menggunakan F-String (contoh: `"Total: 36 pcs"`).

---

## 4. Percabangan Bersarang (`Nested If`)
*Nested if* adalah sebuah percabangan di dalam percabangan. Ini sangat berguna ketika kita harus mengecek syarat bertingkat (kondisi kedua hanya akan dicek jika kondisi pertama sudah terpenuhi, atau nilainya bergantung pada kondisi sebelumnya).

```python
>>> status_member = "VIP"
>>> belanja = 200000

>>> if status_member == "VIP":
...     print("Member VIP dikenali.")
...     if belanja > 100000:
...         print("Anda mendapat voucher gratis ongkir!")
...     else:
...         print("Belanja tambah sedikit lagi untuk voucher.")
... else:
...     print("Member Reguler.")
... 
Member VIP dikenali.
Anda mendapat voucher gratis ongkir!
```

**Soal 4:**
Sebuah penginapan memiliki dua tipe kamar (Studio dan Apartment) dengan tarif yang berubah-ubah tergantung bulan menginap. Berikut adalah ketentuannya:
- **Mei dan Oktober:** Studio = Rp 500.000/malam | Apartment = Rp 650.000/malam
- **Juni dan September:** Studio = Rp 752.000/malam | Apartment = Rp 687.000/malam
- **Juli dan Agustus:** Studio = Rp 760.000/malam | Apartment = Rp 770.000/malam

*Aturan Diskon:* Jika tamu menginap **lebih dari 3 hari**, maka harga total tipe Studio mendapat diskon 15%, sedangkan tipe Apartment mendapat diskon 10%.

Buatlah program yang meminta 2 input:
1. `bulan` (string, contoh: "Juni")
2. `lama` (integer, menunjukkan berapa hari akan menginap)

Gunakan *nested if* (cek bulan apa terlebih dahulu untuk menentukan harga dasar, lalu di dalamnya cek apakah `lama > 3` untuk menerapkan diskon). Hitung total biaya untuk kedua tipe kamar tersebut dan cetak hasilnya dengan rapi sesuai contoh format berikut:
```text
Input bulan: Juni
Input lama inap: 3

Output:
Studio: 2256000
Apartment: 2061000
```