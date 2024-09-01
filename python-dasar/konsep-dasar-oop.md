# Konsep dasar OOP: Class, Object, Method, and Attribute

## Apa itu OOP?
Object-oriented programming (OOP) atau pemrograman berorientasi objek adalah paradigma pemrograman yang didasarkan pada konsep objek. OOP digunakan untuk menstrukturkan program dengan cara membagi program ke dalam objek-objek yang merepresentasikan entitas di dunia nyata.
OOP memungkinkan pemrogram untuk membuat objek yang menggabungkan data dan fungsi yang bekerja pada data tersebut. Hal ini memudahkan dalam membuat, memelihara, dan mengembangkan perangkat lunak yang lebih kompleks

## Class

Kelas adalah cetak biru atau blueprint dari objek. Kelas mendefinisikan properti (attributes) dan perilaku (methods) dari objek yang akan dibuat

**Sintaks dasar kelas**
```Python
class NamaKelas:
    # Inisialisasi kelas
    def __init__(self, attribute1, attribute2):
        self.attribute1 = attribute1
        self.attribute2 = attribute2

    # Method contoh
    def contoh_method(self):
        return self.attribute1 + self.attribute2
```
* `__init__`: merupakan konstruktor di python, digunakan untuk menginisialisasi atribut objek saat objek diciptakan
* `self`: mengacu pada instance dari kelas tersebut, digunakan untuk mengakses atribut dan method dalam kelas

**Contoh pembuatan kelas**
```Python
class Mobil:
    def __init__(self, merk, model, tahun):
        self.merk = merk
        self.model = model
        self.tahun = tahun

    def deskripsi(self):
        return f"{self.merk} {self.model} tahun {self.tahun}"
```

## Objeks
Objek adalalh instansi nyata dari kelas. Setelah sebuah kelas didefinisikan, objek dapat dibuat berdasarkan kelas tersebut

**Membuat objek dari kelas**
```Python
mobil1 = Mobil("Toyota", "Camry", 2022)
mobil2 = Mobil("Honda", "Civic", 2021)

print(mobil1.deskripsi())  # Output: Toyota Camry tahun 2022
print(mobil2.deskripsi())  # Output: Honda Civic tahun 2021
```

## Attribute

Atribut adalah variable yang menyimpan data terkait dengan objek. Atribut didefinisikan di dalam kelas dan diinisialisasi dalam konstruktor __init__

**Contoh atribute**
Dalam contoh kelas mobil di atas merk, model, dan tahun adalah atribut dari objek mobil1, dan mobil2

## Method (metode)

Metode adalah fungsi yang didefinisikan di dalam kelas dan berorientasi pada atribut-atribut dari kelas tersebut. Metode menggambarkan perilaku yang dapat dilakukan oleh objek

**Contoh method**

Metode deskripsi pada kelas mobil adalah contoh dari metode yang mengembalikan string deskriptif berdasarkan atribut objek

## Self dalam python

Kata kunci `self` digunakan sebagai referensi ke objek yang sedang dibuat dari kelas tersebut. Setiap metode dalam kelas harus memiliki self sebagai parameter pertama, yang digunakan untuk mengakses atribut dan metode lain dari objek yang sama

**Contoh penggunaan self**
```Python
class Buku:
    def __init__(self, judul, penulis):
        self.judul = judul
        self.penulis = penulis

    def info(self):
        return f"Buku: {self.judul}, Penulis: {self.penulis}"

buku1 = Buku("Python for Beginners", "John Doe")
print(buku1.info())  # Output: Buku: Python for Beginners, Penulis: John Doe
```
## Kesimpulan
OOP adalah paradigma pemrograman yang berfokus pada objek, yang merupakan kombinasi data (atribut) dan fungsi (method). Konsep dasar seperti kelas, objek, metode dan atribut adalah fondasi dari oop. Dengan memahami dan menerapkan konsep-konsep ini, anda dapat membuat program yang lebih modular, terstruktur dan mudah dikelola
