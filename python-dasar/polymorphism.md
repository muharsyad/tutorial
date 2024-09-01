# Polymorphism (Polimorfisme)

Polimorfisme adalah kemampuan metode untuk bekerja dengan cara yang berbeda berdasarkan objek yang memanggilnya. Dalam konteks OOP, polimorfisme memungkinkan metode dengan nama yang sama untuk diterapkan pada objek dari berbagai kelas, sehingga kode menjadi lebih fleksibel dan mudah dikelola.

## Polimorfisme dengan metode

Metode yang sama dapat berperilaku berbeda tergantung pada objek yang memanggilnya. Polimorfisme memungkinkan fungsi atau metode untuk menangani berbagai jenis objek

**Contoh Polimorfisme**

```Python
class Burung:
    def bersuara(self):
        return "Kicau"

class Bebek(Burung):
    def bersuara(self):
        return "kwek kwek"

class Ayam(Burung):
    def bersuara(self):
        return "kukuruyuk"

# Fungsi umum yang dapat menerima objek dari kelas apa pun

def suara_hewan(hewan):
    print(hewan.bersuara())

burung1 = Burung()
bebek1 = Bebek()
ayam1 = Ayam()

suara_hewan(burung1)    # Output: Kicau
suara_hewan(bebek1)     # Output: kwek kwek
suara_hewan(ayam1)      # Output: kukuruyuk
```

Dalam contoh ini, fungsi `suara_hewan` dapat menerima objek dari berbagai kelas (`Burung`, `Bebek`, atau `Ayam`), dan masing-masing objek akan memanggila metode `bersuara` yang sesuai dengan kelasnya.

## Polimorfisme dengan method overriding

Method overriding adalah cara untuk mengubah atau memperbarui perilaku metode yang diwarisi dari superclass dalam subclass. Metode dalam subclass dengan nama yang sama seperti di superclass akan "menimpa" metode superclass.

**Contoh method overriding**
```Python
class Hewan:
    def bersuara(self):
        return "Hewan mengeluarkan suara"

class Kucing(Hewan):
    def bersuara(self):
        return "Meong"

class Anjing(Hewan):
    def bersuara(self):
        return "Guk guk"

# Objek dari masing-masing subclass
kucing = Kucing()
anjing = Anjing()

print(kucing.bersuara())  # Output: Meong
print(anjing.bersuara())  # Output: Guk guk
```

Disini, metode `bersuara` pada kelas `Kucing` dan `Anjing` menimpa metode yang sama di kelas `Hewan`, sehingga mereka memberikan output yang berbeda saat dipanggil.

## Kesimpulan

Polimorfisme adalah fitur penting dalam OOP yang memungkinkan kode yang lebih modular, reusable, dan fleksibel. Polimorfisme memungkinkan metode yang sama berperilaku berbeda tergantung pada objeknya. Dengan memahami dan menerapkan konsep ini, anda dapat menulis program yang lebih efisien dan terstruktur.