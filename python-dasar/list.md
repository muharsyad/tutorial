# Struktur data python : list



## Pengantar list

List adalah salah satu struktur data paling mendasar dan sering digunakan dalam python. List memungkinkan anda menyimpan sekumpulan data dalam satu variable dan sangat fleksibel karena elemen-elemen di dalamnya dapat berupa berbagai tipe data
List adalah urutan elemen yang terurut dapat ubah (mutable) dan memungkinkan duplikasi elemen. Setiap elemen dalam list memiliki indeks yang dimulai dari nol. List didefinisikan menggunakan tanda kurung siku (`[]`) dan elemen-elemen dipisahkan oleh koma

**Contoh pembuatan list**

```Python
# List kosong
list_kosong = []


# List dengan elemen-elemen integer
angka = [1, 2, 3, 4, 5]

# List dengan elemen-elemen berbagai tipe data
campuran = [1, "dua", 3.0, True]
```

## Mengakses elemen list
Setiap elemen dalam list memiliki indeks yang digunakan untuk mengakses elemen tersebut. Indeks list dimulai dari 0 untuk elemen pertama

**Contoh mengakses elemen list**

```Python
buah = ["apel", "jeruk", "pisang"]

# Mengakses elemen pertama
print(buah[0])  # Output: apel

# Mengakses elemen terakhir dengan indeks negatif
print(buah[-1])  # Output: pisang
```

Anda juga dapat mengakses bagian dari list (slicing) menggunakan sintaks berikut: `list[star:end]` dimana start adalah indeks awal (inklusif) dan end adalah indeks terakhir (eksklusif)

**Contoh slicing list**

```Python
angka = [0, 1, 2, 3, 4, 5]

# Mengakses elemen dari indeks 2 hingga 4
print(angka[2:5])  # Output: [2, 3, 4]

# Mengakses elemen dari awal hingga indeks 3
print(angka[:4])  # Output: [0, 1, 2, 3]

# Mengakses elemen dari indeks 3 hingga akhir
print(angka[3:])  # Output: [3, 4, 5]
```

## Memodifikasi list

List bersifat mutable, artinya anda dapat mengubah, menambah, atau menghapus elemen setelah list diubah

```Python
Mengubah elemen list
buah = ["apel", "jeruk", "pisang"]

# Mengubah elemen kedua
buah[1] = "mangga"
print(buah)  # Output: ['apel', 'mangga', 'pisang']
```

## Menambahkan elemen list
* Menggunakan `append()`: menambahkan elemen ke akhir list
```Python
buah = ["apel", "jeruk"]
buah.append("anggur")
print(buah)  # Output: ['apel', 'jeruk', 'anggur']
```

* Menggunakan `insert()`: menyisipkan elemen di posisi tertentu
```Python
buah = ["apel", "jeruk"]
buah.insert(1, "mangga")
print(buah)  # Output: ['apel', 'mangga', 'jeruk']
```

* Menggunakan `extend()`: menambahkan beberapa elemen sekaligus
```Python
buah = ["apel", "jeruk"]
buah.extend(["pisang", "anggur"])
print(buah)  # Output: ['apel', 'jeruk', 'pisang', 'anggur']
```

## Menghapus elemen dari list

* Menggunakan `remove()`: menghapus elemen tertentu berdasarkan nilai
```Python
buah = ["apel", "jeruk", "pisang"]
buah.remove("jeruk")
print(buah)  # Output: ['apel', 'pisang']
```

* Menggunakan `pop()`: menghapus elemen berdasarkan indeks dan mengembalikannya
```Python
buah = ["apel", "jeruk", "pisang"]
elemen = buah.pop(1)
print(elemen)  # Output: jeruk
print(buah)  # Output: ['apel', 'pisang']
```

* Menggunakan `clear()`: menghapus semua elemen dalam list
```Python
buah = ["apel", "jeruk", "pisang"]
buah.clear()
print(buah)  # Output: []
```

## Fungsi dan metode list

Python menyediakan berbagai fungsi dan metode untuk memanipulasi list

* `len()`: mengembalikan jumlah elemen dalam list
```Python
buah = ["apel", "jeruk", "pisang"]
print(len(buah))  # Output: 3
```

* `sort()`: mengurutkan elemen-elemen list secara menak atau menurun
```Python
angka = [3, 1, 4, 2]
angka.sort()
print(angka)  # Output: [1, 2, 3, 4]

# Mengurutkan secara menurun
angka.sort(reverse=True)
print(angka)  # Output: [4, 3, 2, 1]
```

* `reverse()`: membalik urutan elemen dalam list
```Python
buah = ["apel", "jeruk", "pisang"]
buah.reverse()
print(buah)  # Output: ['pisang', 'jeruk', 'apel']
```

* `index()`: mengembalikan indeks dari elemen pertama yang ditemukan
```Python
buah = ["apel", "jeruk", "pisang"]
print(buah.index("jeruk"))  # Output: 1
```

* `count()`: menghitung berapa kali elemen tertentu muncul dalam list
```Python
angka = [1, 2, 2, 3, 4, 2]
print(angka.count(2))  # Output: 3
```

* `copy()`: membuat salinan dari list
```Python
buah = ["apel", "jeruk", "pisang"]
buah_baru = buah.copy()
print(buah_baru)  # Output: ['apel', 'jeruk', 'pisang']
```

## List bersarang (nested list)
List dapat berisi list lainnya sebagai elemen-elemennya, yang dikenal sebagai list bersarang

**Contoh list bersarang**
```Python
angka = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

# Mengakses elemen dalam list bersarang
print(angka[0])  # Output: [1, 2, 3]
print(angka[1][2])  # Output: 6
```

List bersarang berguna untuk merepresentasikan matriks atau tabel data

## List comprehension

List comprehension adalah cara singkat dan elegan untuk membuat list baru dengan menerapkan ekspresi ke setiap elemen dalam urutan

**Contoh list comprehension**

```Python
# Membuat list dengan elemen berupa kuadrat dari 0 hingga 4
kuadrat = [x**2 for x in range(5)]
print(kuadrat)  # Output: [0, 1, 4, 9, 16]

# Membuat list hanya dengan bilangan genap dari 0 hingga 9
genap = [x for x in range(10) if x % 2 == 0]
print(genap)  # Output: [0, 2, 4, 6, 8]
```

List comprehension membuat kode lebih ringkas dan mudah dibaca

## Kesimpulan 
List adalah struktur data yang kuat dan serbaguna dalam python. Memahami cara membuat, mengakses, memodifikasi, dan menghapus elemen dalam list, serta menggunakan metode dan fungsi terkait, akan sangat membantu dalam memanipulasi data secara efektif dalam program pyhton anda. Dengan list comprehension anda dapat membuat list dengan cara yang lebih efisien dan elegan
