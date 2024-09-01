# Struktur data python : Tuple

## Pengantar tuple

Tuple adalah salah satu struktur data yang disediakan oleh python yang mirip dengan list, tetapi dengan perbedaan penting yaitu tuple bersifat immutable. Ini berarti bahwa setelah tuple di buat, elemen-elemennya tidak dapat diubah, ditambahkan, atau dihapus. Tuple sangat berguna ketika anda ingin memastikan bahwa data yang anda gunakan tidak berubah secara tidak sengaja selama program berjalan

Tuple adalah urutan elemen yang terurut dan tidak dapat diubah (immutable). Elemen-elemen dalam tuple bisa terdiri dari berbagai tipe data, seperti integer, string, list, bahkan tuple lainnya. Tuple didefinisikan menggunakan tanda kurung biasa (`()`), dan elemen-elemennya dipisahkan oleh koma.

**Contoh pembuatan tuple**

```Python
# Tuple kosong
tuple_kosong = ()

# Tuple dengan elemen-elemen integer
angka = (1, 2, 3, 4, 5)

# Tuple dengan elemen-elemen berbagai tipe data
campuran = (1, "dua", 3.0, True)

# Tuple dengan satu elemen (gunakan koma)
satu_elemen = (5,)
```

## Mengakses elemen tuple

Seperti list, setiap elemen dalam tuple memiliki indeks yang dimulai dari nol. Anda dapat mengakses elemen-elemen ini menggunakna indeks

**Contoh mengakses elemen tuple**

```Python
buah = ("apel", "jeruk", "pisang")

# Mengakses elemen pertama
print(buah[0])  # Output: apel

# Mengakses elemen terakhir dengan indeks negatif
print(buah[-1])  # Output: pisang
```

Adalah juga dapat melakukan slicing pada tuple untuk mengakses sebagian elemen

**Contoh slicing tuple**

```Python
angka = (0, 1, 2, 3, 4, 5)

# Mengakses elemen dari indeks 2 hingga 4
print(angka[2:5])  # Output: (2, 3, 4)

# Mengakses elemen dari awal hingga indeks 3
print(angka[:4])  # Output: (0, 1, 2, 3)

# Mengakses elemen dari indeks 3 hingga akhir
print(angka[3:])  # Output: (3, 4, 5)
```

## Immutability pada tuple

Perbedaan utama antara tuple dan list adalah immutability pada tuple. Setelah tuple dibuat, anda tidak dapat mengubah elemen-elemen di dalamnya

**Contoh immutability**

```Python
angka = (1, 2, 3)

# Ini akan menyebabkan TypeError
angka[0] = 10  # Error: 'tuple' object does not support item assignment
```

## Operasi dan fungsi pada tuple

Meskipun tuple bersifat immutability, anda masih bisa melakukan beberapa operasi dan menggunakan beberapa fungsi bawaan untuk memanipulasi atau memeriksan tuple

* Menggabungkan tuple (`+`): anda dapat menggabungkan dua tuple untuk membuat tuple baru
```Python
a = (1, 2, 3)
b = (4, 5, 6)
c = a + b
print(c)  # Output: (1, 2, 3, 4, 5, 6)
```

* Mengulang tuple (`*`): anda dapat mengulang elemen-elemen dalam tuple beberapa kali
```Python
angka = (1, 2, 3)
hasil = angka * 2
print(hasil)  # Output: (1, 2, 3, 1, 2, 3)
```

* Mengecek keberadaan elemen (`in`): anda bisa menggunakan kata kunci in untuk mengecek apakah suatu elemen ada di dalam tuple
```Python
buah = ("apel", "jeruk", "pisang")
print("apel" in buah)  # Output: True
```

* Mengihitung elemen (`count()`): mengembalikan jumlah kemunculan elemen tertentu dalam tuple
```Python
angka = (1, 2, 3, 2, 2)
print(angka.count(2))  # Output: 3
```

* Mendapatkan indeks elemen (`index()`): mengembalikan indeks pertama dari elemen yang ditemukan
```Python
angka = (1, 2, 3, 2, 2)
print(angka.index(3))  # Output: 2
```

* Menghitung panjang tuple (`len()`): mengembalikan jumlah elemen dalam tuple
```Python
buah = ("apel", "jeruk", "pisang")
print(len(buah))  # Output: 3
```

## Tuple bersarang (nedted tuple)

Tuple dapat berisi tuple lain sebagai elemen-elemennya, yang dikenal sebagai tuple bersaran

**Contoh tuple bersarang**
```Python
nested_tuple = (1, (2, 3), (4, (5, 6)))

# Mengakses elemen dalam tuple bersarang
print(nested_tuple[1])  # Output: (2, 3)
print(nested_tuple[2][1])  # Output: (5, 6)
```

## Tuple sebagai retrun value

Tuple sering digunakan dalam python sebagai cara untuk mengembalikan beberapa nilai dari sebuah fungsi

**Contoh fungsi yang mengembalikan tuple**
```Python
def fungsi_matematika(x, y):
    penjumlahan = x + y
    pengurangan = x - y
    return (penjumlahan, pengurangan)

hasil = fungsi_matematika(10, 5)
print(hasil)  # Output: (15, 5)

# Mendapatkan masing-masing hasil
tambah, kurang = fungsi_matematika(10, 5)
print(tambah)  # Output: 15
print(kurang)  # Output: 5
```

## Mengubah tuple menjadi list dan sebaliknya

Meskipun tuple bersifat immutable, anda bisa mengubah tuple menjadi list (mutable), melakukan modifikasi, lalu mengubahnya kembali menjadi tuple

**Contoh konversi tuple ke list**
```Python
angka = (1, 2, 3)
list_angka = list(angka)
list_angka.append(4)
angka_baru = tuple(list_angka)
print(angka_baru)  # Output: (1, 2, 3, 4)
```

## Kapan menggunakan tuple?

Tuple digunakan ketika anda ingin menyimpan sekumpulan data yang tidak akan berubah sepanjang eksekusi program. Contoh umum penggunaan tuple adalah untuk mengembalikan beberapa nilai dari sebuah fungsi, sebagai kunci dalam dictionary (karena tuple hashable dan immutable) atau untuk menggabungkan beberapa elemen yang bersifat tetap

## Kesimpulan

Tuple adalah struktur data yang sederhana dan efisien dalam python berguna untuk menyimpan data yang tidak dapat diubah. Memahami tuple dan bagaimana menggunakannya dengan benar akan sangat membantu dalam menulis kode python yang bersih, aman, dan efisien.
