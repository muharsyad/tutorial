# **Abstraction dalam Python**

**Abstraction** (abstraksi) adalah salah satu konsep penting dalam Pemrograman Berorientasi Objek (OOP). Abstraksi berfokus pada menyembunyikan detail implementasi dari pengguna dan hanya menampilkan fungsionalitas yang diperlukan. Dengan abstraksi, Anda dapat bekerja dengan objek secara konseptual tanpa perlu memahami detail teknis yang mendasarinya.

## **1. Konsep Abstraction**

Abstraksi membantu menyederhanakan interaksi antara bagian-bagian kode dengan menyembunyikan detail kompleks dan hanya memperlihatkan metode atau atribut yang relevan. Dalam Python, abstraksi dapat dicapai dengan menggunakan **class abstract** dan **interface**.

## **2. Class Abstract**

Sebuah **class abstract** adalah kelas yang tidak dapat diinstansiasi secara langsung. Kelas ini hanya digunakan sebagai dasar untuk kelas lain dan biasanya berisi satu atau lebih metode abstrak. Metode abstrak adalah metode yang dideklarasikan di dalam kelas abstract tetapi tidak memiliki implementasi.

Python menyediakan modul `abc` (Abstract Base Class) yang memungkinkan Anda membuat class abstract.

### **Membuat Class Abstract:**

1. **Menggunakan Modul `abc`:** 
    * Impor `ABC` dan `abstractmethod` dari modul `abc`.
    * Turunkan class dari `ABC` untuk menjadikannya abstract.
    * Gunakan decorator `@abstractmethod` untuk mendeklarasikan metode abstrak.

2. **Contoh Class Abstract:**

```python
from abc import ABC, abstractmethod

class Bentuk(ABC):
    @abstractmethod
    def luas(self):
        pass

    @abstractmethod
    def keliling(self):
        pass

class Lingkaran(Bentuk):
    def __init__(self, jari_jari):
        self.jari_jari = jari_jari

    def luas(self):
        return 3.14 * self.jari_jari ** 2

    def keliling(self):
        return 2 * 3.14 * self.jari_jari

# Objek dari class abstract tidak bisa diinstansiasi
# bentuk = Bentuk()  # Akan menghasilkan TypeError

# Membuat objek dari kelas turunan yang mengimplementasikan metode abstrak
lingkaran = Lingkaran(5)
print(f"Luas Lingkaran: {lingkaran.luas()}")        # Output: Luas Lingkaran: 78.5
print(f"Keliling Lingkaran: {lingkaran.keliling()}")  # Output: Keliling Lingkaran: 31.400000000000002
```

## **3. Interface dalam Python**

Python tidak memiliki dukungan langsung untuk interface seperti bahasa lain (misalnya Java atau C#). Namun, konsep interface dapat dicapai menggunakan class abstract yang hanya berisi metode abstrak. Interface adalah sebuah kontrak yang mendefinisikan metode yang harus diimplementasikan oleh kelas yang mengimplementasikannya.

### **Contoh Interface:**

```python
from abc import ABC, abstractmethod

class Kendaraan(ABC):
    @abstractmethod
    def bergerak(self):
        pass

class Mobil(Kendaraan):
    def bergerak(self):
        print("Mobil bergerak di jalan raya")

class Pesawat(Kendaraan):
    def bergerak(self):
        print("Pesawat terbang di udara")

# Objek dari interface tidak bisa diinstansiasi
# kendaraan = Kendaraan()  # Akan menghasilkan TypeError

# Membuat objek dari kelas yang mengimplementasikan interface
mobil = Mobil()
pesawat = Pesawat()

mobil.bergerak()   # Output: Mobil bergerak di jalan raya
pesawat.bergerak() # Output: Pesawat terbang di udara
```

## **4. Abstraction vs Encapsulation**

- **Encapsulation** adalah proses menyembunyikan data dari akses langsung dan menyediakannya melalui metode khusus.
- **Abstraction** adalah proses menyembunyikan detail implementasi dan hanya menampilkan fungsionalitas yang relevan.

Keduanya saling melengkapi dalam OOP, membantu membuat kode lebih modular, terstruktur, dan mudah dikelola.

## **5. Keuntungan Menggunakan Abstraction**

- **Meminimalkan Kompleksitas:** Dengan abstraksi, Anda tidak perlu memahami seluruh detail implementasi; cukup mengetahui metode yang tersedia dan bagaimana menggunakannya.
- **Meningkatkan Reusability:** Kelas abstract dan interface memungkinkan Anda mendefinisikan blueprint untuk kelas lain, yang dapat digunakan kembali di berbagai bagian program.
- **Memudahkan Pemeliharaan:** Dengan memisahkan antarmuka dan implementasi, kode menjadi lebih mudah dikelola dan diperbarui.

## **6. Contoh Penggunaan dalam Dunia Nyata**

- **Framework dan API:** Banyak framework dan API yang menggunakan konsep abstraksi untuk menyembunyikan detail implementasi dari pengguna dan hanya menampilkan antarmuka yang perlu digunakan.
- **Desain Software Modular:** Abstraksi memungkinkan pembuatan perangkat lunak yang modular, di mana bagian-bagian yang berbeda dari aplikasi dapat dikembangkan dan dipelihara secara independen.

