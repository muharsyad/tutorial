# Struktur data python : Dictionary

## Pengantar dictionary
Dictionary adalah salah struktur data bawaan python yang digunakan untuk menyimpan pasangan nilai key-value. Dictionary memungkinkan anda mengakses data dengan menggunakan key, yang berfungsi sebagai identifikator unik untuk setiap value yang disimpan. Dictionary sangat efisien untuk pencarian, penambahan, dan penghapusan elemen berdasarkan key.

Dictionary dalam python bersifat mutable, yang berarti anda dapat mengubah, menambahkan, atau menghapus item setelah disctionary dibuat. Dictionary dibuat dengan menggunakan kurung kurawal `{}` dan pasangan key-values dipisahkan oleh tanda titik dua :

**Contoh pembuatan dictionary**

```Python
# Dictionary kosong
kosong = {}

# Dictionary dengan pasangan key-value
mahasiswa = {
    "nama": "Arsyad",
    "umur": 22,
    "jurusan": "Matematika"
}

# Dictionary dengan berbagai tipe data sebagai value
data = {
    "nama": "Arsyad",
    "nilai": [90, 85, 88],
    "lulus": True
}
```

## Mengakses elemen dictionary

Anda dapat mengakses value dari dictionary menggunakan key-nya. Jika key tidak ditemukan, python akan mengembalikan error ‘`KeyError`’

**Contoh mengakses elemen**
```Python
mahasiswa = {"nama": "Arsyad", "umur": 22, "jurusan": "Matematika"}

# Mengakses value dengan key
print(mahasiswa["nama"])  # Output: Arsyad

# Mengakses value dengan metode get (aman dari KeyError)
print(mahasiswa.get("umur"))  # Output: 22
print(mahasiswa.get("alamat", "Tidak ditemukan"))  # Output: Tidak ditemukan
```

## Menambah dan mengubah elemen

Anda bisa menambahkan elemen baru atau mengubah elemen yang sudah ada dalam dictionary

**Contoh menambahkan dan mengubah elemen:**
```Python
mahasiswa = {"nama": "Arsyad", "umur": 22}

# Menambahkan pasangan key-value baru
mahasiswa["jurusan"] = "Matematika"

# Mengubah value dari key yang sudah ada
mahasiswa["umur"] = 23

print(mahasiswa)
# Output: {'nama': 'Arsyad', 'umur': 23, 'jurusan': 'Matematika'}
```

## Menghapus elemen

Python menyediakan beberapa cara untuk menghapus elemen dari dictionary, seperti menggunakan `del`, `pop()`, dan `clear()`

**Contoh menghapus elemen:**
```Python
mahasiswa = {"nama": "Arsyad", "umur": 22, "jurusan": "Matematika"}

# Menghapus pasangan key-value dengan del
del mahasiswa["umur"]

# Menghapus dengan metode pop, mengembalikan value yang dihapus
jurusan = mahasiswa.pop("jurusan")

# Menghapus semua elemen dengan clear
mahasiswa.clear()

print(mahasiswa)  # Output: {}
```

## Mengecek keberadaan key

anda bisa menggunakan kata kunci `in` untuk memeriksa apakah sebuah key ada di dalam dictionary

**contoh mengecek keberadaan key**
```Python
mahasiswa = {"nama": "Arsyad", "umur": 22, "jurusan": "Matematika"}

# Mengecek apakah key "nama" ada dalam dictionary
print("nama" in mahasiswa)  # Output: True

# Mengecek apakah key "alamat" ada dalam dictionary
print("alamat" in mahasiswa)  # Output: False
```

## iterasi pada dictionary

anda dapat melakukan iterasi pada dictionary untuk mendapatkan key, value, atau keduanya menggunakan metode `keys()`, `values()`, `items()`

**contoh iterasi**
```Python
mahasiswa = {"nama": "Arsyad", "umur": 22, "jurusan": "Matematika"}

# Iterasi melalui key
for key in mahasiswa.keys():
    print(key)
# Output: nama, umur, jurusan

# Iterasi melalui value
for value in mahasiswa.values():
    print(value)
# Output: Arsyad, 22, Matematika

# Iterasi melalui key dan value
for key, value in mahasiswa.items():
    print(f"{key}: {value}")
# Output:
# nama: Arsyad
# umur: 22
# jurusan: Matematika
```

## dictionary bersarang (nested dictionary)

python memungkinkan anda untuk membuat dictionary di dalam dictionary yang dikenal sebagai dictionary bersarang

**contoh dictionary bersarang**
```Python
mahasiswa = {
    "nama": "Arsyad",
    "umur": 22,
    "nilai": {"matematika": 90, "fisika": 85}
}

# Mengakses elemen dalam dictionary bersarang
print(mahasiswa["nilai"]["matematika"])  # Output: 90
```

## metode-metode pada dictionary

python menyediakan berbagai metode untuk bekerja dengan dictionary seperti `update()`, `popitem()`, `copy()`, dan lain-lain.

* `update()`: menambahkan elemen dari dictionary lain atau pasangan key-value
* `popitem()`: menghapus pasangan key-value terakhir yang dimasukan
* `copy()`: membuat salinan shallow dari dictionary

**Contoh penggunaan metode:**
```Python
mahasiswa = {"nama": "Arsyad", "umur": 22}

# Menggunakan update untuk menambahkan atau mengupdate dictionary
mahasiswa.update({"jurusan": "Matematika", "umur": 23})

# Menggunakan popitem untuk menghapus elemen terakhir
terakhir = mahasiswa.popitem()

# Menggunakan copy untuk membuat salinan dictionary
mahasiswa_copy = mahasiswa.copy()

print(mahasiswa)
# Output: {'nama': 'Arsyad', 'umur': 23, 'jurusan': 'Matematika'}
```

## Kapan menggunakan dictionary

Dictionary digunakan ketika anda membutuhkan asosiasi key-value, misalnya untuk menyimpan data yang terhubung dengan identitas unik (seperti id pengguna, nama, atau kategori). Dictionary sangat berguna untuk pengambilan data yang cepat, karena akses ke elemen dilakukan melalui key, yang jauh lebih efisien dibandingkan pencarian elemen dalam list.

## Kesimpulan

Dictionary adalah struktur data yang sangat kuat dan fleksibel dalam python. Dengan memahami cara kerja dictionary, bagaimana mengakses dan memanipulasi data di dalamnya, anda dapat menangani berbagai tugas pemrograman yang memerlukan struktur data yang kompleks dan efisien.
