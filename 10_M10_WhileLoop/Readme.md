# Perulangan (While Loop)

Pada materi sebelumnya, kita sudah belajar `for loop` yang sangat cocok digunakan jika kita **sudah tahu** berapa kali kode harus diulang (misalnya mengulang sebanyak 10 kali, atau menelusuri setiap elemen di dalam list).

Lalu, bagaimana jika kita **tidak tahu** pasti berapa kali perulangan harus dilakukan, dan hanya ingin kode terus mengulang *selama* suatu kondisi terpenuhi? Di sinilah kita menggunakan **`while loop`**. 

Perulangan `while` akan terus mengeksekusi blok kode di dalamnya **selama kondisinya bernilai `True`**.

---

## 1. Penggunaan Dasar `While Loop`
Struktur `while` sangat mirip dengan `if`. Bedanya, setelah blok kode selesai dijalankan, program akan kembali ke atas untuk mengecek kondisi itu lagi. Jika masih `True`, blok kode dijalankan lagi. Begitu seterusnya sampai kondisinya menjadi `False`.

**Aturan wajib:** Kalian WAJIB mengubah nilai variabel pengontrol di dalam blok `while` agar kondisinya bisa berubah menjadi `False` suatu saat nanti.

Variabel pengontrol ini biasanya berupa **counter** (penghitung) yang nilainya bertambah atau berkurang setiap kali perulangan dijalankan.

```python
>>> angka = 1 # Variabel pengontrol

# Selama angka lebih kecil atau sama dengan 5, jalankan kode:
>>> while angka <= 5:
...     print(f"Perulangan ke-{angka}")
...     angka += 1  # SANGAT PENTING: Tambahkan 1 agar loop bisa berhenti
... 
Perulangan ke-1
Perulangan ke-2
Perulangan ke-3
Perulangan ke-4
Perulangan ke-5
```

**Soal 1**
Buatlah sebuah program hitung mundur menggunakan `while loop`. Dimulai dari variabel `waktu = 10`. Selama `waktu` lebih besar dari 0, cetak angka tersebut, lalu kurangi nilainya dengan 1 (`waktu -= 1`). Ketika perulangan selesai, cetak `"Selesai!"`.

---

## 2. *Infinite Loop* (Perulangan Tanpa Henti)
Apa yang terjadi jika kita lupa menambahkan kode `angka += 1` pada contoh di atas? Kondisi `angka <= 5` akan **selalu `True`** (karena nilai angka selalu 1). 

Akibatnya, program akan mencetak "Perulangan ke-1" ribuan kali tanpa henti sampai komputer *hang* atau *crash*. Ini disebut **Infinite Loop**.

```python
# CONTOH KODE SALAH (JANGAN DITIRU)
>>> x = 10
>>> while x > 5:
...     print("Ini tidak akan pernah berhenti!")
...     # Lupa mengurangi nilai x
```
**Notes:** Jika kalian terjebak dalam *infinite loop* saat menjalankan program di terminal, tekan tombol **`Ctrl + C`** secara bersamaan pada keyboard untuk menghentikan program secara paksa!

**Soal 2**
Seorang mahasiswa menulis kode ini untuk mencetak angka genap dari 2 hingga 10:
```python
bilangan = 2
while bilangan <= 10:
    print(bilangan)
```
Kode di atas akan menyebabkan *infinite loop*. Tuliskan sebaris kode apa yang kurang dan di mana kode tersebut harus diletakkan agar program berjalan dengan benar!

---

## 3. Mengontrol Loop dengan `break`
Sama seperti pada `for loop`, kita bisa menghentikan paksa sebuah `while loop` kapan saja menggunakan statement `break`. Teknik ini sering digunakan dengan pola `while True:` (loop abadi yang sengaja dibuat, lalu dihentikan dari dalam menggunakan `if-break`).

```python
>>> counter = 1

>>> while True:  # Sengaja dibuat selalu True
...     print(f"Langkah {counter}")
...     if counter == 3:
...         print("Kondisi terpenuhi, menghentikan loop!")
...         break  # Memaksa keluar dari while loop
...     counter += 1
... 
Langkah 1
Langkah 2
Langkah 3
Kondisi terpenuhi, menghentikan loop!
```

**Soal 3**
Kalian memiliki sebuah kardus kosong. Setiap kali perulangan berjalan, kalian memasukkan barang seberat 5 kg ke dalam kardus tersebut (gunakan variabel `total_berat` yang terus bertambah). Gunakan `while True:` dan `break` untuk menghentikan loop JIKA `total_berat` sudah mencapai atau melebihi 25 kg. Cetak `total_berat` di setiap putaran!

---

## 4. Kombinasi While & Input
Kekuatan sejati `while loop` terlihat saat kita membuat program interaktif. Kita bisa meminta input dari pengguna terus-menerus sampai mereka memasukkan jawaban yang benar atau mengetikkan kata kunci tertentu untuk keluar.

```python
>>> while True:
...     perintah = input("Ketik 'keluar' untuk menghentikan program: ")
...     if perintah.lower() == "keluar":
...         print("Program dihentikan. Sampai jumpa!")
...         break
...     else:
...         print(f"Anda mengetik: {perintah}. Program masih berjalan...\n")
```
*(Coba salin kode di atas ke file Python kalian dan jalankan. Program akan terus meminta input sampai kalian mengetik kata "keluar").*

**Soal 4**
Buatlah sebuah program simulasi login dengan ketentuan berikut:
1. Simpan password yang benar dalam variabel `password_rahasia = "statbis2026"`.
2. Gunakan `while True:` untuk meminta pengguna memasukkan password secara berulang menggunakan `input()`.
3. Gunakan `if-else`: 
   - Jika tebakan password **benar**, cetak `"Login Berhasil, Selamat Datang!"` dan hentikan perulangan (`break`).
   - Jika tebakan **salah**, cetak `"Password salah, silakan coba lagi!"` dan biarkan perulangan terus berlanjut.