# Operator Dalam Python

## Daftar Isi
- [Operator Aritmatika](#operator-aritmatika)
- [Operator Penugasan](#assignment-operator-operator-penugasan)
- [Operator Perbandingan](#comparison-operator-operator-perbandingan)
- [Operator Logika](#logical-operator-operator-logika)
- [Operator Identitas](#identity-operator-operator-identitas)
- [Operator Keanggotaan](#membership-operator-operator-keanggotaan)
- [Operator Bitwise](#bitwise-operator)
- [Kesimpulan](#kesimpulan)

Dalam pemrograman, operator adalah simbol yang digunakan untuk melakukan operasi pada variable dan nilai. Python menyediakan berbagai jenis operator yang dapat digunakan untuk melakukan operasi matematika, logika, dan manipulasi data. Berikut ini adalah penjelasan mengenai berbagai jenis operator dalam Python

## Operator Aritmatika 

Operator aritmatika digunakan untuk melakukan operasi matematika dasar seperti penjumlahan pengurangan, perkalian, dan pembagian

| Operator | Nama | Contoh | Hasil|
|----------|------|--------|------|
| `+` | Penjumlahan | `a+b` | Jumlah dari `a` dan `b`|
| `-` | Pengurangan | `a-b` | Selisih dari `a` dan `b`|
| `*` | Perkalian | `a*b` | hasil kali dari `a` dan `b`|
| `/` | Pembagian | `a/b` | hasil bagi dari `a` dan `b` |
| `%` | Modulus | `a%b` | sisa dari hasil bagi `a` dan `b` |
| ** | Eksponensial | `a**b` | `a` pangkat `b` |
| // | Pembagian bulat | `a//b` | hasil bagi bulat dari `a` dan `b` |

**Contoh penggunaan**

```Python
x = 10
y = 3
print(x + y)    # Output 13
print(x - y)    # Output 7
print(x * y)    # Output 30
print(x / y)    # Output 3.33
print(x % y)    # Output 1
print(x ** y)   # Output 1000
print(x // y)   # Output 3
```

## *Assignment Operator* (Operator Penugasan)

Operator penugasan digunakan untuk memberikan nilai ke variabel. Operator ini menggabungkan operasi aritmatika dengan penugasan.

| Operator | Contoh | Hasil |
|----------|--------|-------|
| `=` | `x = 5` | `x` diberi nilai `5`|
| `+=` | `x += 3` | `x = x + 3` |
| `-=` | `x -= 3` | `x = x - 3` |
| `*=` | `x *= 3` | `x = x * 3` |
| `/=` | `x /= 3` | `x = x / 3` |
| `%=` | `x %= 3` | `x = x % 3` |
| `//=` | `x //= 3` | `x = x // 3` |
| `**=` | `x **= 3` | `x = x ** 3` |

**Contoh Penggunaan**

```Python
x = 10

print(x)    # Output 10
print(x += 3)    # Output 13
print(x -= 3)    # Output 7
print(x *= 3)    # Output 30
print(x /= 3)    # Output 3.33
print(x %= 3)    # Output 1
print(x //= 3)    # Output 3
print(x **= 3)    # Output 1000
```

## *Comparison Operator* (Operator Perbandingan)

Operator perbandingan digunakan untuk membandingkan dua nilai. Operator ini akan mengembalikan nilai boolean (`True` atau `False`)

| Operator | Nama | Contoh | Hasil |
|----------|------|--------|-------|
| `==` | Sama dengan | `x == y` | `True` jika `x` sama dengan `y` |
| `!=` | Tidak sama | `x != y` | `True` jika `x` tidak sama dengan `y` |
| `>` | Lebih besar | `x > y` | `True` jika `x` lebih besar dari `y` |
| `<` | Lebih kecil | `x < y` | `True` jika `x` lebih kecil dari `y` | 
| `>=` | Lebih besar atau sama dengan | `x >= y` | `True` jika `x` lebih besar atau sama dengan `y` |
| `<=` | Lebih kecil atau sama dengan | `x <= y` | `True` jika `x` lebih kecil atau sama dengan `y` |

**Contoh Penggunaan**

```Python
x = 10
y = 5

print(x == y)   # Output: False
print(x != y)   # Output: True
print(x > y)    # Output: True
print(x < y)    # Output: False
print(x >= y)   # Output: True
print(x <= y)   # Output: False
```

## *Logical Operator* (Operator Logika)

Operator logika digunakan untuk menggabungkan dua atau lebih kondisi

| Operator | Nama | Contoh | Hasil |
|----------|------|--------|-------|
| `and` | Dan | `x > 5 and x <10` | `True` jika kedua kondisi benar |
| `or` | Atau | `x > 5 or x < 10` | `True` jika salah satu kondisi benar |
| `not` | Tidak | `not(x > 5 and x < 10)` | Membalikan hasil, `True` menjadi `False` dan sebaliknya |

**Contoh penggunaan**`

```Python
x = 10
print(x > 5 and x < 15) # Output: True
print(x > 5 or x < 15)	# Output: True
print(not(x > 5 and x < 15))    # Output: False
```

## *Identity Operator* (Operator Identitas)

Operator identitas digunakan untuk membandingkan objek, apakah mereka sebenarnya adalah objek yang sama dalam memori

| Operator | Nama | Contoh | Hasil |
|----------|------|--------|-------|
| `is` | Adalah | `x is y` | `True` jika `x` dan `y` adalah objek yang sama|
| `is not` | Bukan | `x is not y` | `True` jika `x` dan `y` bukan objek yang sama |

**Contoh penggunaan**

```Python
x = 'Hello'
y = x
z = 'Hello World'

print(x is y)   # Output True
print(x is not z)   # Output True
```

## *Membership Operator* (Operator Keanggotaan)

Operator keanggotaan digunakan untuk menguji apakah sebuah nilai ada dalam urutan

| Operator | Nama | Contoh | Hasil |
|----------|------|--------|-------|
| `in` | Dalam | `x in y` | `True` jika `x` ada dalam `y`|
| `not in` | Tidak dalam | `x not in y` | `True` jika `x` tidak ada dalam `y` |

**Contoh Penggunaan**

```Python
x = [1, 2, 3, 4, 5]

print(3 in x)   # Output True
print(6 not in x)   # Output True
```

## *Bitwise Operator* 

Operator bitwise digunakan untuk operasi pada level bit

| Operator | Nama | Contoh | Hasil |
|----------|------|--------|-------|
| `&` | AND Bitwise | `x & y` | Bitwise and|
| `\|` | OR Bitwise | `x \| y` | Bitwise or|
| `^` | XOR Bitwise | `x ^ y` | Bitwise xor|
| `~` | NOT Bitwise | `x ~ y` | Bitwise not|
| `<<` | Geser kiri | `x << y` | Geser bit ke kiri|
| `>>` | Geser kanan | `x >> y` | Geser bit ke kanan|

**Contoh penggunaan**

```Python
x = 10
y = 4

print(x & y)
print(x | y)
print(x ^ y)
print(x ~ y)
print(x >> y)
print(x << y)
```

## Kesimpulan

Operator adalah komponen penting dalam pemrograman Python yang memungkinkan kita untuk melakukan berbagai operasi pada data. Dari operasi dasar artimatika, hingga manipulasi bit, memahami cara kerja berbagai jenis operator akan membantu anda menulis kode yang lebih efisien dan efektif.