# Pewarisan (*Inheritance*) dalam Python

Pewarisan (*Inheritance*) adalah salah satu pilar utama dalam Pemrograman Berorientasi Objek (OOP). Pewarisan memungkinkan sebuah `class` untuk mewarisi atribut dan metode dari `class` lain, yang memungkinkan kode yang lebih terstruktur, modular, dan dapat digunakan kembali. Kelas yang mewarisi disebut sebagai subclass (kelas turunan), dan kelas yang diwarisi disebut sebagai superclass (kelas induk)

## Konsep Pewarisan

Dengan pewarisan, subclass dapat menggunakan (atau "mewarisi") properti dan metoda yang sudah ada dari superclass tanpa harus menuliskannya kembali. Subclass juga dapat memperluas atau mengubah perilaku superclass dengan menambahkan atau mengubah metode dan atribut

**Sintaks Dasar Pewarisan**

```Python
class Superclass:
    # Inisialisasi kelas induk
    def __init__(self, atribut1):
        self.atribut1 = atribut1

    def method1(self):
        return f"Atribut 1: {self.atribut1}
        
# Subclass yang mewarisi dari superclass
def Subclass(Superclass):
    def __init__(self, atribut1, atribut2):
        # memanggila konstruktor dari kelas induk
        super().__init__(atribut1)
        self.atribut2 = atribut2
    
    def method2(self):
        return f"Atribut 2: {self.atribut2}"
```

## Membuat Kelas Turunan (Subclass)

Untuk membuat subclass, cukup tentukan nama kelas induk dalam tanda kurung setelah nama subclass. Subclass mewarisi semua metode dan atribut dari superclass

**Contoh membuat subclass**

```Python
class Hewan:
    def __init__(self, nama, umur):
        self.nama = nama
        self.umur = umur

    def suara(self):
        return "Hewan mengeluarkan suara"

# Kelas kucing mewarisi dari kelas hewan
class Kucing(Hewan):
    def __init__(self, nama, umur, ras):
        # Memanggil konstruktor kelas induk
        super().__init__(nama, umur)
        self.ras = ras

    def suara(self):
        return "Meong"

    def info(self):
        return f"{self.nama} adalah kucing berumur {self.umur} tahun dan berjenis {self.ras}"

# Membuat objek dari subclass
kucing1 = Kucing("Kitty", 3, "Persia")
print(kucing1.suara())  # Output: Meong
print(kucing1.info())   # Output: Kitty adalah kucing berumur 3 tahun dan berjenis Persia
```

Dalam contoh di atas, kelas `Kucing` mewarisi atribut `nama` dan `umur` dari kelas `Hewan`, serta metode `suara`. Kelas `Kucing` juga menambahkan atribut baru, `ras` dan metode barus `info`

## `super()` dalam Pewarisan

Fungsi `super()` digunakan untuk memanggila metode atau konstruktor dari kelas induk dalam subclass. Ini berguna ketika anda ingin memperluas atau memodifikasi perilaku kelas induk di dalam subclass

**Contoh penggunaan `super()`**

```Python
class Hewan:
    def __init__(self, nama):
        self.nama = nama

    def suara(self):
        return "Hewan mengeluarkan suara"

class Anjing(Hewan):
    def __init__(self, nama, warna):
        # Memanggila konstruktor dari kelas Hewan
        super().__init__(nama)
        self.warna = warna

    def suaru(self):
        return "guk guk"

    def infor(self):
        return f"{self.nama} adalah anjing berwarna {self.warna}"

anjing1 = Anjing("Rover", "coklat")
print(anjing1.suara())  # Output: guk guk
print(anjing.infor())   # Output: Rover adalah anjing berwarna coklat
```

## Kesimpulan

Pewarisan (*Inheritance*) adalah fitur penting dalam OOP yang memungkinkan kode yang lebih modular, reusable, dan fleksibel. Pewarisan memungkinkan subclass untuk menggunakan dan memperluas perilaku superclass. Dengan memahami dan menerapkan konsep ini, anda dapat menulis program yang lebih efisien dan terstruktur.