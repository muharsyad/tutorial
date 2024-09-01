# Fungsi pada python

## Pengantar fungsi
Fungsi adalah blok kode yang dirancang untuk melakukan tugas tertentu dan dapat digunakan kembali di berbagai bagian program. Fungsi memungkinkan anda untuk memecah kode menjadi bagian-bagian yang lebih kecil, lebih terstruktur dan lebih mudah dikelola

Fungsi membantu dalam modularisasi dan reuse (penggunaan kembali) kode. Anda bisa mendefinisikan fungsi sekali dan menggunakannya beberapa kali di seluruh program anda. Fungsi dapat menerima input dalam bentuk parameter dan mengembalikan output

**Sintask dasar fungsi**
```Python
def nama_fungsi(parameter1, parameter2, ...):
    # Blok kode yang akan dijalankan
    return hasil
```

* `def`: kata kunci untuk mendefinisikan fungsi
* `nama_fungsi`: nama yang anda berikan untuk fungsi, yang digunakan untuk memanggilnya
* `parameter`: variable yang diteruskan ke fungsi sebagai inpupt (opsional)
* `return`: pernyataan yang digunakan untuk mengembalikan nilai dari fungsi (opsional)

**Contoh fungsi sederhana**
```Python
def sapa(nama):
    return f"Halo, {nama}!"

# Memanggil fungsi
pesan = sapa("Arsyad")
print(pesan)  # Output: Halo, Arsyad!
```

## Fungsi tanpa parameter

Fungsi tidak harus selalu menerima parameter. Fungsi tanpa parameter dapat digunakan untuk melakukan tugas yang tidak memerlukan input tambahan.

**Contoh fungsi tanpa parameter**
```Python
def tampilkan_pesan():
    print("Selamat datang di kursus Python!")

# Memanggil fungsi
tampilkan_pesan()  # Output: Selamat datang di kursus Python!
```

## Fungsi dengan parameter

Fungsi dapat menerima satu atau lebih parameter, yang berfungsi sebagai input untuk fungsi tersebut. Parameter memungkinkan anda untuk menyesuaikan output fungsi berdasarkan input yang diberikan

**Contoh fungsi dengan parameter**
```Python
def tambah(angka1, angka2):
    return angka1 + angka2

# Memanggil fungsi dengan argumen
hasil = tambah(5, 3)
print(hasil)  # Output: 8
```

## Parameter default

Anda dapat memberikan nilai default untuk parameter dalam fungsi. Jika nilai untuk parameter tersebut tidak diberikan saat fungsi dipanggil, maka nilai default akan digunakan

**Contoh parameter default**
```Python
def sapa(nama, salam="Halo"):
    return f"{salam}, {nama}!"

# Memanggil fungsi tanpa argumen salam
print(sapa("Arsyad"))  # Output: Halo, Arsyad!

# Memanggil fungsi dengan argumen salam
print(sapa("Arsyad", "Selamat Pagi"))  # Output: Selamat Pagi, Arsyad!
```

## Fungsi dengan return

Fungsi dapat mengembalikan nilai menggunakan pernyataan return. Pernyataan ini juga menandai akhir dari eksekusi fungsi

**Contoh fungsi dengan return**
```Python
def kali(angka1, angka2):
    hasil = angka1 * angka2
    return hasil

# Memanggil fungsi dan menyimpan hasilnya
hasil_kali = kali(4, 5)
print(hasil_kali)  # Output: 20
```

## Fungsi tanpa return

Fungsi juga dapt tidak mengembalikan nilai apapun. Dalam kasus ini, fungsi akan mengemablikan None secara implisit
**Contoh fungsi tanpa return**
```Python
def cetak_pesan(pesan):
    print(pesan)

# Memanggil fungsi
cetak_pesan("Belajar Python itu menyenangkan!")
# Output: Belajar Python itu menyenangkan!
```

## Argumentasi posisi dan kata kunci

Saat memanggil fungsi, anda bisa memberikan argumen berdasarkan posisi atau kata kunci

**Contoh argumentasi posisi**
```Python
def sapa(nama, salam):
    return f"{salam}, {nama}!"

# Menggunakan argumentasi posisi
print(sapa("Arsyad", "Selamat Siang"))  # Output: Selamat Siang, Arsyad!
```

**Contoh argumentasi kata kunci**
```Python
# Menggunakan argumentasi kata kunci
print(sapa(nama="Arsyad", salam="Selamat Siang"))  # Output: Selamat Siang, Arsyad!

# Urutan tidak penting saat menggunakan kata kunci
print(sapa(salam="Selamat Siang", nama="Arsyad"))  # Output: Selamat Siang, Arsyad!
```

## Argumen sejumlah tak terhingga
Anda dapat membuat fungsi yang menerima jumlah argumen yang tidak terbatas menggunkan `*args` untuk argumen posisi dan `**kwargs` untuk argumen kata kunci

**Contoh menggunakan `*args`**
```Python
def jumlah(*angka):
    return sum(angka)

# Memanggil fungsi dengan banyak argumen
print(jumlah(1, 2, 3, 4, 5))  # Output: 15
```

**Contoh menggunakan `**kwargs`**
```Python
def data_diri(**info):
    return info

# Memanggil fungsi dengan argumen kata kunci
print(data_diri(nama="Arsyad", umur=22, jurusan="Matematika"))
# Output: {'nama': 'Arsyad', 'umur': 22, 'jurusan': 'Matematika'}
```

## Fungsi lambda

Fungsi lambda adalah fungsi anonim yang dapat didefinisikan dalam satu baris kode. Lambda biasanya digunakan untuk operasi sederhana yang tidak memerlukan blok kode yang panjang

**Contoh fungsi lambda**
```Python
# Fungsi lambda untuk menambah dua angka
tambah = lambda x, y: x + y

# Memanggil fungsi lambda
print(tambah(3, 4))  # Output: 7
```

## Dokumentasi fungsi (docstring)

Docstring adalah string literal yang ditempatkan di awal definisi fungsi untuk menjelaskan fungsi tersebut. Docstring digunakan untuk memberikan penjelasan singkat tentang apa yang dilakukan fungsi

**Contoh docstring**
```Python
def bagi(angka1, angka2):
    """
    Fungsi ini membagi angka1 dengan angka2.
    :param angka1: Pembilang
    :param angka2: Penyebut
    :return: Hasil pembagian angka1 dengan angka2
    """
    return angka1 / angka2

# Mengakses docstring fungsi
print(bagi.__doc__)
```

## Kesimpulan

Fungsi adalah elemen penting dalam pemrograman python yang memungkinkan anda untuk menulis kode yang lebih modular, terstruktur, dan dapat digunakan kembali. Dengan memahami cara kerja fungsi, parameter, return values, dan fitur-fitur lanjutan seperti lambda dan docstrings, anda dapat menulis program yang lebih efisien dan mudah dikelola
