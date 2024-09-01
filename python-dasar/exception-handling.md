# **Exception Handling dalam Python**

**Exception Handling** adalah mekanisme dalam Python yang digunakan untuk menangani kesalahan (error) yang terjadi saat program berjalan. Kesalahan ini, yang dikenal sebagai *exceptions*, dapat menyebabkan program berhenti bekerja jika tidak ditangani dengan baik.

## **1. Apa itu Exception?**

Exception adalah kejadian tak terduga yang terjadi selama eksekusi program yang mengganggu alur normal instruksi. Contoh umum exception meliputi:

- **ZeroDivisionError**: Terjadi saat mencoba membagi angka dengan nol.
- **ValueError**: Terjadi saat tipe data yang diberikan tidak sesuai dengan tipe yang diharapkan.
- **FileNotFoundError**: Terjadi saat mencoba mengakses file yang tidak ada.

## **2. Blok Try-Except**

Untuk menangani exception, Python menyediakan blok `try-except`. Blok `try` digunakan untuk menulis kode yang mungkin menyebabkan exception, dan blok `except` digunakan untuk menentukan apa yang harus dilakukan jika exception terjadi.

### **Sintaks Dasar:**

```python
try:
    # Kode yang mungkin menyebabkan exception
    hasil = 10 / 0
except ZeroDivisionError:
    # Kode untuk menangani exception
    print("Tidak bisa membagi dengan nol!")
```

### **Contoh Penggunaan:**

```python
try:
    angka = int(input("Masukkan angka: "))
    hasil = 10 / angka
    print(f"Hasil pembagian: {hasil}")
except ZeroDivisionError:
    print("Error: Tidak bisa membagi dengan nol!")
except ValueError:
    print("Error: Input harus berupa angka!")
```

## **3. Blok Else**

Blok `else` dapat digunakan untuk menulis kode yang akan dijalankan jika tidak ada exception yang terjadi.

### **Sintaks Dasar:**

```python
try:
    # Kode yang mungkin menyebabkan exception
    hasil = 10 / 2
except ZeroDivisionError:
    print("Tidak bisa membagi dengan nol!")
else:
    print(f"Hasil pembagian: {hasil}")
```

### **Contoh Penggunaan:**

```python
try:
    angka = int(input("Masukkan angka: "))
    hasil = 10 / angka
except ZeroDivisionError:
    print("Error: Tidak bisa membagi dengan nol!")
except ValueError:
    print("Error: Input harus berupa angka!")
else:
    print(f"Hasil pembagian: {hasil}")
```

## **4. Blok Finally**

Blok `finally` digunakan untuk menulis kode yang akan dijalankan tidak peduli apakah exception terjadi atau tidak. Blok ini biasanya digunakan untuk membersihkan sumber daya, seperti menutup file atau melepaskan koneksi.

### **Sintaks Dasar:**

```python
try:
    file = open("data.txt", "r")
    content = file.read()
except FileNotFoundError:
    print("File tidak ditemukan!")
finally:
    file.close()
    print("File telah ditutup.")
```

### **Contoh Penggunaan:**

```python
try:
    file = open("data.txt", "r")
    content = file.read()
    print(content)
except FileNotFoundError:
    print("Error: File tidak ditemukan!")
finally:
    print("Operasi file selesai.")
```

## **5. Menggunakan Exception Umum**

Python memiliki banyak built-in exceptions yang dapat digunakan untuk menangani berbagai jenis kesalahan. Berikut adalah beberapa exceptions umum:

- **IndexError**: Terjadi ketika mencoba mengakses indeks yang tidak ada dalam list.
- **KeyError**: Terjadi ketika mencoba mengakses kunci yang tidak ada dalam dictionary.
- **TypeError**: Terjadi ketika operasi dilakukan pada tipe data yang tidak sesuai.
- **AttributeError**: Terjadi ketika mencoba mengakses atribut yang tidak ada dalam objek.

### **Contoh Penggunaan:**

```python
my_list = [1, 2, 3]

try:
    print(my_list[5])
except IndexError:
    print("Error: Indeks di luar jangkauan!")
```

## **6. Membuat Exception Sendiri (Custom Exceptions)**

Anda juga dapat membuat exception sendiri dengan mewarisi kelas `Exception`. Ini berguna ketika Anda ingin menangani kesalahan spesifik yang tidak tercakup oleh exception bawaan.

### **Contoh Custom Exception:**

```python
class NilaiNegatifError(Exception):
    def __init__(self, nilai):
        self.nilai = nilai
        super().__init__(f"Nilai tidak bisa negatif: {self.nilai}")

def hitung_akar_kuadrat(nilai):
    if nilai < 0:
        raise NilaiNegatifError(nilai)
    return nilai ** 0.5

try:
    hasil = hitung_akar_kuadrat(-4)
except NilaiNegatifError as e:
    print(e)
```

## **7. Best Practices dalam Exception Handling**

- **Tangani Hanya Exception yang Diketahui:** Sebaiknya hanya tangani exception yang Anda prediksi akan terjadi. Jangan gunakan `except:` yang terlalu umum, karena ini dapat menyembunyikan kesalahan yang tidak terduga.

    ```python
    try:
        # Kode yang mungkin menyebabkan exception
        hasil = 10 / 0
    except ZeroDivisionError:
        print("Tidak bisa membagi dengan nol!")
    ```

- **Gunakan Exception untuk Kasus yang Tidak Diharapkan:** Jangan gunakan exception untuk mengendalikan alur normal program.

- **Sertakan Pesan Error yang Jelas:** Berikan pesan error yang informatif untuk membantu memahami apa yang salah.

    ```python
    try:
        hasil = 10 / 0
    except ZeroDivisionError as e:
        print(f"Error terjadi: {e}")
    ```

## **8. Kesimpulan**

Exception handling adalah bagian penting dari pemrograman yang memastikan bahwa program Anda tetap berjalan meskipun terjadi kesalahan. Dengan menggunakan blok `try-except`, `else`, dan `finally`, Anda dapat menangani kesalahan secara efektif dan menjaga program tetap stabil. Python menyediakan banyak built-in exceptions yang dapat digunakan untuk menangani berbagai jenis kesalahan, dan Anda juga dapat membuat custom exceptions untuk menangani kasus-kasus khusus.
