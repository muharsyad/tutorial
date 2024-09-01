# Struktur data python : set

## Pengantar set

Set adalah salah satu struktur data bawaan python yang digunakan untuk menyimpan koleksi item yang unik dan tidak berutan. Tidak seperti list atau tuple, elemen dalam set tidak memiliki urutan tertentu, dan setiap elemen harus unik, artinya tidak ada duplikasi elemen dalam set
Set dalam python adalah koleksi yang tidak terurut dan tidak memiliki indeks. Set didefinisikan menggunakan kurung kurawal `{}` atau fungsi `set()`. Set hanya dapat menyimpan elemen-elemen yang hashable (misalnya tipe data seperti string, integer, tuple), tetapi tidak dapat menyimpan elemen yang bersifat mutable seperti list, atau dictionary

**Contoh pembuatan set**

```Python
# Set kosong
kosong = set()

# Set dengan elemen-elemen unik
buah = {"apel", "jeruk", "pisang"}

# Set dengan elemen-elemen campuran
campuran = {1, "dua", 3.0, (4, 5)}
```

## Mengakses elemen set

Karena set tidak terurut dan tidak memiliki indeks, anda tidak dapat mengakses elemen-elemen set dengan menggunakan indeks seperti pada list atau tuple. Namun, anda dapat melakukan iterasi melalui elemen-elemen dalam set

**Contoh itarasi set**
```Python
buah = {"apel", "jeruk", "pisang"}

for item in buah:
    print(item)
# Output bisa berbeda urutannya:
# apel
# pisang
# jeruk
```

## Menambahkan dan menghapus elemen

Set memungkinkan anda untuk menambahkan atau menghapus elemen-elemen menggunakan metode `add()`, `update()`, `remove()`, dan `discard()`

**Contoh menambahkan elemen**
```Python
buah = {"apel", "jeruk"}

# Menambahkan satu elemen
buah.add("pisang")

# Menambahkan beberapa elemen sekaligus
buah.update(["mangga", "anggur"])

print(buah)
# Output: {'mangga', 'anggur', 'pisang', 'apel', 'jeruk'}
```

**Contoh menghapus elemen**
```Python
buah = {"apel", "jeruk", "pisang"}

# Menghapus elemen menggunakan remove
buah.remove("jeruk")

# Menghapus elemen menggunakan discard (tidak menimbulkan error jika elemen tidak ada)
buah.discard("mangga")

# Menghapus dan mengembalikan elemen acak dengan pop
elemen = buah.pop()

# Menghapus semua elemen dalam set
buah.clear()

print(buah)  # Output: set()
```

## Operasi pada set

Set mendukung berbagai operasi matematis seperti gabungan, irisan, perbedaan, dan perbedaan simetris. Operasi-operasi ini sangat berguna dalam berbagai aplikasi yang membutuhkan manipulasi himpunan
**Contoh operasi pada set**
```Python
a = {1, 2, 3, 4}
b = {3, 4, 5, 6}

# Union (gabungan) - elemen yang ada di set A atau B
print(a | b)  # Output: {1, 2, 3, 4, 5, 6}

# Intersection (irisan) - elemen yang ada di set A dan B
print(a & b)  # Output: {3, 4}

# Difference (perbedaan) - elemen yang ada di set A tetapi tidak di B
print(a - b)  # Output: {1, 2}

# Symmetric Difference (perbedaan simetris) - elemen yang ada di set A atau B tetapi tidak keduanya
print(a ^ b)  # Output: {1, 2, 5, 6}
```

## Mengecek keberadaan elemen

Anda bisa menggunakan kata kunci in untuk memeriksa apakah sebuah elemen ada di dalam set

**Contoh mengecek keberadaan elemen**
```Python
buah = {"apel", "jeruk", "pisang"}

print("apel" in buah)  # Output: True
print("mangga" in buah)  # Output: False
```

## Set bersarang dan frozenset

Python memungkinkan anda untuk membuat set yang berisi set lain yang bersifat immutable (frozenset). Frozenset adalah versi immutable dari set, sehingga elemen-elemennya tidak dapat diubah setelah frozenset dibuat

**Contoh frozenset**
```Python
# Membuat frozenset
a = frozenset([1, 2, 3, 4])

# Menambahkan frozenset ke dalam set lain
set_bersarang = {a, 5, 6}

print(set_bersarang)
# Output: {frozenset({1, 2, 3, 4}), 5, 6}
```

## Metode-metode pada set

Python menyediakan berbagai metode yang dapat digunakan untuk bekerja dengan set, seperti `copy()`, `isdisjoint()`, `issubset()`, `issuperset()`, dan `difference_update()`

* `isdisjoint()`: mengembalikan True jika dua set tidak memiliki elemen yang sama
* `issubset()`: mengembalikan True jika semua elemen set ada dalam set lain
* `issuperset()`: mengembalikan True jika set memiliki semua elemen dari set lain
`difference_upadate()`: menghapus semau elemen dari set yang juga ada dalam set lain.

**Contoh penggunaan metode**
```Python
a = {1, 2, 3, 4}
b = {3, 4, 5, 6}

# Mengecek apakah a adalah subset dari b
print(a.issubset(b))  # Output: False

# Menghapus elemen yang ada di kedua set
a.difference_update(b)
print(a)  # Output: {1, 2}
```

## Kapan menggunakan set?

Set digunakan ketika anda membutuhkan koleksi elemen yang unik dan tidak terurut. Set sangat berguna ketika anda perlu melakukan operasi himpunan seperti gabungan, irisan, atau perbedaan, atau ketika anda ingin memastikan bahwa tidak ada elemen duplikat dalam koleksi

## Kesimpulan
Set adalah struktur data yang poweful dalam python untuk mengelola koleksi elemen yang unik dan tidak terurut. Memahami cara kerja set dan bagaimana melakukan operasi himpunan dasar sangat penting untuk menangani tugas-tugas yang melibatkan data unik dan pemrosesan himpunan
