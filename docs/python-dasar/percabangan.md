# Struktur Kontrol Percabangan

##  Daftar Isi

- [Konsep Dasar Percabangan](#konsep-dasar-percabangan)
- [Penggunaa If](#penggunaan-if)
- [Penggunaan elif](#penggunaan-elif)
- [Penggunaan Else](#penggunaan-else)
- [Penggunaan Bersama](#penggunaan-bersama-if-elif-dan-else)
- [Percabangan Bersarang](#percabangan-bersarang-nested-if)
- [Kesimpulan](#kesimpulan)

Struktur kontrol adalah salah satu konsep penting dalam pemrograman yang memungkinkan program untuk mengambil keputusan berdasarkan kondisi tertentu. Di Python, percabangan ini dapat dilakukan menggunakan `if`, `elif`, dan `else`

## Konsep Dasar Percabangan

Percabangan memungkinkan program untuk menjalankan blok kode tertentu hanya jika suatu kondisi terpenuhi. Kondisi ini bisanya diekspresikan dalam bentuk eksperesi yang mengembalikan nilai boolean (`True` atau `False`)

**Sintaks umum:**

```Python
if kondisi
    # blok kode yang dieksekusi jika kondisi benar (True)
elif kondisi lain
    # Blok kode yang dieksekusi jika kondisi_lain benar (True)
else:
    # Blok kode yang dieksekusi jika semua kondisi di atas salah (False)
```

* `if`: Memeriksa kondisi pertama, jika kondisi ini benar, maka blok kode di bawahnya akan dieksekusi
* `elif`: Singkatnya dari 'else if', digunakan untuk memeriksa kondisi tambahan jika kondisi `if` sebelumnya salah (`False`)
* `else`: Digunakan untuk mengeksekusi blok kode jika semua kondisi di atasnya salah (`False`)

## Penggunaan `if`

`if` digunakan untuk mengeksekusi sebuah blok kode jika kondisi yang diberikan bernilai benar (`True`)

**Contoh penggunaan**

```Python
nilai = 85

if nilai >= 75:
    print("Selamat, anda lulus")
```

Dalam contoh di atas, blok kode `print('selamat, anda lulus')` hanya akan diekskusi jika nilai variabel `nilai` lebih besar atau sama dengan `75`

## Penggunaan `elif`

`elif` digunakan untuk memeriksa kondisi lain jika kondisi `if` sebelumnya salah. Anda dapat menggunakan beberapa `elif` untuk memeriksa beberapa kondisi.

**Contoh penggunaan**

```Python
nilai = 65

if nilai >= 75:
    print("selamat, anda lulus")
elif nilai >= 50:
    print("Anda harus mengikut ujian ulang")
```

Dalam contoh ini, jika `nilai` kurang dari `75` tetapi lebih besar atau sama dengan `50`, maka pesan "anda harus mengukiti ujian ulang" akan dicetak.

## Penggunaan else

`else` digunakan untuk menangani semua kondisi yang tidak terpenuhi oleh `if` atau `elif`. Blok kode dalam `else` akan dieksekusi jika semua kondisi sebelumnya salah

**Contoh Penggunaa**

```Python
nilai = 40

if nilai >= 75:
    print("selamat, anda lulus")
elif nilai >= 50:
    print("anda harus mengikuti ujian ulang")
else:
    print("maaf, anda tidak lulus")
```

Dalam contoh ini, jika nilai kurang dari 50, maka pesan "maaf, anda tidak lulus" akan dicetak

## Penggunaan bersama `if`, `elif` dan `else`

Ketika anda memiliki beberapa kondisi yang perlu diuji, anda bisa menggunakan kombinasi `if`, `elif`, dan `else`

**Contoh penggunaan**

```Python
umur = 18

if umur >= 18:
    print("anda sudah dewasa")
elif umur >= 13:
    print("anda adalah seorang remaja")
else:
    print("anda masih anak-anak")
```

Dalam contoh di atas, pesan yang akan dicetak tergantung pada nilai variabel `umur`. Jika `umur` adalah `18` atau lebih, maka pesan "anda sudah dewasa" akan dicetak. Jika umur adalah 13 atau lebih, tetapi kurang dari 18, maka pesan "anda seorang remaja" akan dicetak. Jika umur kurang dari 13 tahun, maka pesan "anda masih anak-anak" akan dicetak.

**Contoh lain penggunaan percabangan**

Anda juga dapat menggunakan operator logika seperti `and`, `or`, dan `not` dalam kondisi percabangan untuk membuat ekspresi yang lebih kompleks`

contoh penggunaan dengan operator logika

```Python
x = 10
y = 5

if x > 5 and y < 10:
    print("x lebih besar dari 5 dan y lebih kecil dari 10")
elif x > 5 or y <10:
    print("salah satu dari kondisi terpenuhi")
else:
    print("tidak ada kondisi yang terpenuhi")
```

Dalam contoh ini, kombinasi `x > 5 and y < 10` atau `x > 5 or y < 10` menentukan kondisi mana yang akan dieksekusi

## Percabangan bersarang (*nested if*)

Anda dapat menempatkan satu pernyataan `if`, `elif`, atau `else` di dalam blok kode dari pernyataan `if` lainnya. Ini disebut percabangan bersarang.

**Contoh penggunaan**

```Python
nilai = 85:

if nilai >= 75:
    if nilai >= 90:
        print("nilai anda sangat baik")
    else:
        print("nilai anda baik")
else:
    print("anda tidak lulus")
```

Dalam contoh ini, jika nilai lebih besar atau sama dengan 75, program akan memeriksa lagi apakah nilai tersebut juga lebih besar atau sama dengan 90

## Kesimpulan

Struktur kontrol percabangan `if`, `elif`, dan `else` dalam Python memungkinkan anda untuk membuat keputusan dalam program anda berdasarkan kondisi tertentu. Dengan pemahaman yang baik tentang bagaimana percabangan bekerja, anda dapat menulis program yang lebih fleksibel dan dinamis.