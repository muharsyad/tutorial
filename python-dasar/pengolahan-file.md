# **Pengolahan File dalam Python**

Pengolahan file adalah proses membaca dan menulis data dari dan ke file. Python menyediakan berbagai fungsi bawaan yang memudahkan pengolahan file, baik untuk file teks maupun file biner.

## **1. Membuka File (Opening a File)**

Untuk mengolah file, langkah pertama yang perlu dilakukan adalah membuka file tersebut. Python menggunakan fungsi `open()` untuk membuka file.

### **Sintaks Dasar:**

```python
file = open("nama_file", "mode")
```

- `nama_file`: Nama file yang akan dibuka (dapat mencakup path file).
- `mode`: Menentukan mode pembukaan file (misalnya membaca, menulis).

### **Mode Pembukaan File:**

- `"r"`: Membaca file (read-only mode). File harus ada.
- `"w"`: Menulis ke file (write mode). Jika file tidak ada, akan dibuat. Jika file ada, isinya akan dihapus.
- `"a"`: Menambahkan data ke file (append mode). Jika file tidak ada, akan dibuat.
- `"b"`: Mode biner (untuk file non-teks, seperti gambar).
- `"+"`: Membaca dan menulis.

### **Contoh Membuka File:**

```python
file = open("data.txt", "r")
```

## **2. Membaca File (Reading a File)**

Setelah file dibuka, Anda dapat membaca isinya menggunakan beberapa metode.

### **Metode Membaca File:**

- **`read()`**: Membaca seluruh isi file sebagai satu string.
  
    ```python
    content = file.read()
    print(content)
    ```

- **`readline()`**: Membaca satu baris dari file.
  
    ```python
    line = file.readline()
    print(line)
    ```

- **`readlines()`**: Membaca seluruh baris dalam file dan mengembalikannya sebagai list.
  
    ```python
    lines = file.readlines()
    print(lines)
    ```

## **3. Menulis ke File (Writing to a File)**

Untuk menulis data ke file, Anda harus membuka file dalam mode penulisan (`"w"`, `"a"`, atau `"w+"`).

### **Menulis Menggunakan `write()`:**

```python
file = open("output.txt", "w")
file.write("Ini adalah baris pertama.\n")
file.write("Ini adalah baris kedua.\n")
file.close()
```

- Jika file tidak ada, Python akan membuatnya.
- Jika file ada, isinya akan dihapus dan diganti dengan data baru.

### **Menambahkan Data Menggunakan `append()`**:

```python
file = open("output.txt", "a")
file.write("Ini adalah baris tambahan.\n")
file.close()
```

## **4. Menutup File (Closing a File)**

Setelah selesai bekerja dengan file, selalu disarankan untuk menutup file menggunakan metode `close()`. Ini memastikan bahwa semua perubahan disimpan dan tidak ada kebocoran memori.

```python
file.close()
```

## **5. Bekerja dengan `with` Statement**

Python menyediakan cara yang lebih aman dan bersih untuk membuka dan menutup file menggunakan `with` statement. Ini secara otomatis menutup file setelah blok kode dieksekusi.

### **Contoh `with` Statement:**

```python
with open("data.txt", "r") as file:
    content = file.read()
    print(content)
```

Setelah blok `with` selesai, file akan ditutup secara otomatis, sehingga tidak perlu memanggil `close()`.

## **6. Bekerja dengan File CSV**

File CSV (Comma-Separated Values) adalah format file teks yang digunakan untuk menyimpan data tabular. Python memiliki modul `csv` untuk mempermudah pengolahan file CSV.

### **Contoh Membaca File CSV:**

```python
import csv

with open("data.csv", "r") as file:
    reader = csv.reader(file)
    for row in reader:
        print(row)
```

### **Contoh Menulis ke File CSV:**

```python
import csv

data = [
    ["Nama", "Umur", "Kota"],
    ["Arsyad", "21", "Jakarta"],
    ["Budi", "22", "Bandung"]
]

with open("output.csv", "w", newline="") as file:
    writer = csv.writer(file)
    writer.writerows(data)
```

## **7. Bekerja dengan File JSON**

JSON (JavaScript Object Notation) adalah format file yang digunakan untuk menyimpan data yang terstruktur. Python memiliki modul `json` untuk membaca dan menulis data JSON.

### **Contoh Membaca File JSON:**

```python
import json

with open("data.json", "r") as file:
    data = json.load(file)
    print(data)
```

### **Contoh Menulis ke File JSON:**

```python
import json

data = {
    "nama": "Arsyad",
    "umur": 21,
    "kota": "Jakarta"
}

with open("output.json", "w") as file:
    json.dump(data, file)
```

## **8. Kesimpulan**

Pengolahan file adalah bagian penting dari pemrograman yang memungkinkan Anda membaca dan menulis data dari file eksternal. Dengan memahami konsep dasar seperti membuka, membaca, menulis, dan menutup file, Anda dapat mengelola data dalam berbagai format, termasuk teks, CSV, dan JSON. Python menyediakan antarmuka yang kuat dan mudah digunakan untuk pengolahan file, yang dapat membantu dalam pengembangan aplikasi yang lebih kompleks.