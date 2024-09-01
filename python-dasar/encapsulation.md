# Encapsulation dalam Python

Encapsulation (enkapsulasi) adalah salah satu pilar utama dalam Pemrograman Berorientasi Objek (OOP). Konsep ini bertujuan untuk melindungi data dengan menyembunyikan atribut dari akses langsung di luar kelas, serta memberikan cara yang aman untuk mengakses dan memodifikasi melalui metode khsusu.

## Konsep Encapsulation

Encapsulation mengizinkan anda untuk menyembunyikan atribut dari pengguna eksternal dan memberikan metode untuk mengakses atau memodifikasi. Ini membantu menjaga integritas data dan mencegah modifikasi yang tidak disengaja atau tidak sah.

Dalam Python, enkapsulasi dapat dilakukan dengan membuat atribut atau metode menjadi "private" (pribadi) dengan menambahkan garis bawah ganda (`__`) di awal nama atribut atau metode

**Contoh Encapsulation**

```Python
class Mahasiswa:
    def __init__(self, nama, umur):
        self.__nama = nama  # Atribut privat
        self.__umur = umur  # Atribut privat

    # Getter method untuk mendapatkan nilai atribut
    def gen_nama(self):
        return.self.__nama

    def get_umur(self):
        return sefl.__umur

    # Setter method untu memodifikasi nilai atribut
    def set_nama(self, nama_baru):
        self.__nama = nama_barus

    def set_umur(self, umur_baru):
        if umur_baru > 0:
            self.__umur = umur_baru
        else:
            print("Umur harus positif")

# Membuat objek Mahasiswa
mhs = Mahasiswa("Arsyad", 21)

# Mengakses atribut menggunakan getter
print(mhs.get_nama())  # Output: Arsyad
print(mhs.get_umur())  # Output: 21

# Memodifikasi atribut menggunakan setter
mhs.set_nama("Budi")
mhs.set_umur(22)

print(mhs.get_nama())  # Output: Budi
print(mhs.get_umur())  # Output: 22
```

# Mengakses Atribut dengan getter

Getter adalah metode yang digunakan untuk mengakses atau mengambil nilai dari atribut privat. Dalam contoh di atas `get_nama()` dan `get_umur()` adalah getter methods yang mengembalikan nilai dari atribut `__nama` dan `__umur`.

Menggunakan getter menjaga kontrol terhadap akses ke atribut, dan memungkinkan anda untuk mengelola bagaimana data tersebut di ambil.

**Contoh Getter**
```Python
class Buku:
    def __init__(self, judul, penulis):
        self.__judul = judul
        self.__penulis = penulis

    def get_judul(self):
        return self.__judul

    def get_penulis(self):
        return self.__penulis

buku1 = Buku("Pemrograman Python", "Arsyad")
print(buku1.get_judul())  # Output: Pemrograman Python
print(buku1.get_penulis())  # Output: Arsyad
```

## Memodifikasi Atribut dengan Setter

Setter adalah metode yang digunakan untuk memodifikasi atau mengubah nilai dari atribut privat. Dalam contoh sebelumnya, `set_nama()` dan `set_umur()` adalah setter methods yang digunakan untuk mengubah nilai `__nama` dan `__umur`

Dengan setter, anda dapat menerapkan logika tambahan, seperti validasi, sebelum mengubah nilai atribut.

**Contoh Setter**
```Python
class Produk:
    def __init__(self, nama, harga):
        self.__nama = nama
        self.__harga = harga

    def get_nama(self):
        return self.__nama

    def get_harga(self):
        return self.__harga

    def set_harga(self, harga_baru):
        if harga_baru > 0:
            self.__harga = harga_baru
        else:
            print("Harga harus lebih besar dari 0")

produk1 = Produk("Laptop", 5000000)
print(produk1.get_harga())  # Output: 5000000

produk1.set_harga(5500000)   # Mengubah harga
print(produk1.get_harga())  # Output: 5500000

produk1.set_harga(-1000)  # Output: Harga harus lebih besar dari 0
```

## Penyembunyian Data (Data Hidding)

Dengan enkapsulasi, atribut dan metode yang diprivatkan tidak dapat diakses langsung dari luar kelas. Ini membantu melindungi data dari manipulasi yang tidak diinginkan.

Meskipun Python tidak memeilki konsep akses seperti `private`, `protected`, dan `public` secara eksplisit seperti di beberapa bahasa pemrograman lain, anda dapat menggunakan konvensi penamaan (misalnya, `__`) untuk menunjukkan bahwa atribut atau metode tidak boleh diakses langsung dari luar kelas.

**Contoh penyembunyian data**

```Python
class AkunBank:
    def __init__(self, saldo):
        self.__saldo = saldo  # Atribut private

    def lihat_saldo(self):
        return self.__saldo

    def tarik_uang(self, jumlah):
        if jumlah <= self.__saldo:
            self.__saldo -= jumlah
        else:
            print("Saldo tidak cukup")

akun1 = AkunBank(1000000)

# Akses langsung akan gagal
# print(akun1.__saldo)  # Akan menghasilkan AttributeError

# Menggunakan metode untuk mengakses
print(akun1.lihat_saldo())  # Output: 1000000

# Tarik uang
akun1.tarik_uang(250000)
print(akun1.lihat_saldo())  # Output: 750000
```

## Kesimpulan

Encapsulation adalah teknik penting dalam OOP yang bertujuan untuk melindungi data dan memastikan akses yang aman serta terkontrol terhadap atribut dari sebuah kelas. Dengan menggunakan getter dan setter, anda dapat mengontrol bagaimana data diakses dan dimodifikasi, serta menjaga integritas data. Enkapsulati membantu menjaga kode lebih meodular dan terstruktur, memungkinkan perubahan dalam satu bagian kode tanpa memengaruhi bagian lain.