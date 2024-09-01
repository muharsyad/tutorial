# Struktur Kontrol Perulangan `for` dan `while` dalam Python

## Daftar Isi
- [Perulangan for](#perulangan-for)
- [Perulangan while](#perulangan-while)
- [Menggunakan Range()](#menggunakan-range-dengan-for)

Perulangan adalah konsep penting dalam pemrograman ayng memungkinkan anda untuk mengeksekusi blok kode yang sama berulang kali, baik untuk sejumlah iterasi tertentu maupun hingga kondisi tertentu terpenuhi, Python menyediakan dua jenis perulangan utama, `for` dan `while`

## Perulangan `for`

Perulangan `for` digunakan ketika anda ingin mengulangi blok kode untuk setiap elemen dalam suatu urutan (seperti `list`, `tuple` atau `string`) atau untuk rentang nilai tertentu.

**Sintaks Umum**

```Python
for item in iterable:
    # blok kode yang akan diulang
```

* item: variable yang akan mengambil nilai dari setiap elemen dalam urutan
* iterable: urutan elemen yang akan diiterasi (misalnya `list`, `tuple`, `string` atau objek `range`)

**Contoh penggunaa**

```Python
buah = ["apel", "jeruk", "pisang"]

for item in buah:
    print(item)
```

Dalam contoh di atas, perulangan `for` akan mengiterasi melalui setiap elemen dalam list `buah` dan mencetaknya setiap nama buah

## Menggunakan `range()` dengan for

Fungsi `range()` sering digunakan dengan perulanga for untuk mengulai blok kode sejumlah iterasi tertentu

```Python
for i in range(5):
    print(i)
```

Contoh di atas akan mencetak angka 0 hingga 4. `range(5)` menghasilkan urutan angka dari 0 hingga 4.

## Penggunaan `for` dengan `string`

Anda juga dapat mengiterasi setiap karakter dalam sebuah `string` menggunakan perulangan `for`

```Python
kalimat = "Python"

for huruf in kalimat:
    print(huruf)
```

Hasilnya adalah setiap huruf dari string kalimat dicetak pada baris yang terpisah

## Perulangan `while`

Perulangan `while` digunakan ketika anda ingin mengulangi blok kode selama suatu kondisi tertentu tetap benar. Kondisi ini diperiksa sebelum setiap itersi, sehingga perulangan `while` bisa saja tidak pernah dieksekusi jika kondisi awalnya sudah salah

**Sintaks umum**

```Python
while kondisi:
    # Blok kode yang akan diulang
```

* kondisi: ekspresi yang dievaluasi sebelum setiap iterasi. Jika bernilai benar, maka blok kode akan dieksekusi

**Contoh penggunaan `while`**

```Python
i = 0

while i < 5:
    print(i)
    i += 1
```

Dalam contoh di atas, selama nilai `i` kurang dari 5, perulangan `while` akan terus dijalankan. Setiap kali perulangan dijalankan nilai `i` akan di tambah

**Penggunaan while untuk mengulangi input pengguna**

Perulangan `while` sering digunakan untuk mengulangi permintaan input dari pengguna hingga input yang valid diberikan

```Python
password = ""

while password != "1234":
    password = input("masukan password")

print("password benar")
```

contoh di atas akan terus meminta input password hingga pengguna memasukan "1234"

## Kombinasi `else` dengan `for` dan `while`

Python mendukung penggunaan `else` dengan perulangan `for` dan `while`. Blok kode dalam `else` akan dieksekusi jika perulangan selesai secara normal tanpa intervensi `break`

**Contoh penggunaan `else` dan `for`**

```Python
for i in range(5):
    print(i)
else:
    print("perulangan selesai")
```

dalam contoh ini, setelah perulangan for selesai, pesan "perulangan selesai" akan dicetak

**Contoh penggunaan `else` dengan `while`**

```Python
while i < 5:
    print(i)
    i += 1

else:
    print("perulangan selesai")
```

Sama seperti contoh `for`, setelah perulangan `while` selesai, pesan "perulangan selesai' akan dicetak

## Menghentikan Perulangan dengan `break` dan melanjutkan perulangan dengan `continue`

* `break`: digunakan untuk menghentikan perulangan sebelum kondisinya selesai atau sebelum semua elemen dalam iterable diiterasi.
* `continue`: digunakkan untuk melompati iterasi saat ini dan langsung melanjutkan ke iterasi berikutnya.

**Contoh penggunaan break**

```Python
for i in range(10):
    if i == 5:
        break
    print(i)
```

Dalam contoh ini perulangan `for` akan berhenti ketika `i` mencapai 5, sehingga angka 5 tidak akan dicetak.

**Contoh penggunaan `continue`**

```Python
for i in range(10):
    if i%2 == 0:
        continue
    print(i)
```

Dalam contoh ini, hanya angka ganjil yang akan dicetak, karena perintah `continue` melompati iterasi saat `i` adalah bilangan genap.

## Perulangan bersarang (*nested loop*)

Anda dapat menempatkan satu perulangan di dalam perulangan lainnya. Ini disebut perulangan bersarang

**Contoh penggunaan**

```Python
for i in range(3):
    for j in range(5):
        print(f"i={i}, j={j}")
```

Dalam contoh ini, untuk setiap iterasi dari `i`, perulangan `j` akan berjalan sepenuhnya.

## Kesimpulan

Struktur kontrol perulangan `for` dan `while` dalam python memberikan fleksibel besar dalam bagaimana anda dapat mengulangi eksekusi blok kode berdasarkan kondisi atau urutan elemen. Memahami perulangan ini sangat penting untuk menulis kode yang efesien dan efektif