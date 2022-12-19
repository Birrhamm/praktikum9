# Praktikum 9

# Exception Handling 
- Execption handling atau (eksepsi) adalah merupakan suatu kesalahan ( eror) yang terjadi atau yang telah di lakukan pada saat proses eksekusi program sedang berjalan.

- Kesalahan ini dapat menyebabkan program
 yang di buat tidak berakhir dengan normal

# Handling

- Yaitu penangan file adalah bagian yang sangat penting dari aplikasi apapun

# Assertion
- Assertion atau biasa sering di sebut (pernyataan) adalah kewajaran yang ada di dalam program yang bisa di atur aktif dan non aktif ketika pada saat selesai menjalankanya program

# The assert Statement

- Pada saat kita menemukan pernyataan, Python dapat mengevaluasi ekspresi yang menyertainya, Yang mana bisa benar bisa salah. Jika ekspresi tersebut salah maka python akan memunculkan AssertionError

- assert Exspression[, Argument]

Jika pernyataan gagal maka python akan menggunakan ArgumentExpression yaitu sebagai argumen untuk AssertionError. AssertionError juga dapat ditangkap dan ditangani seperti pengecualian lainya menggunakan try- , Tetapi ketika kita biarkan mereka akan menghentikan program tersebut maka akan menghasilkan backtrace

# Contoh

- Berikut adalah fungai yang untuk mengubah suhu derajat kelvin menjadi derajat Fahrenheit

- Kode program beserta hasil nya
```
def KelvinToFahrenheit(Temprature):
    assert(Temprature >= 0 ),"Colder than  absolute zero!"
    return((Temprature-273)*1.8)+32
print(KelvinToFahrenheit(237))
print(int(KelvinTOFahrenheit(505.78)))
print(KelvinToFahrenheit(-5))
```
![gambar1](gambar/x1.png)

# Ketika kita dalam menangani pengecualian 

Jika kita memiliki kode yang kemungkinan mencurigakan yang mungking dapat mengeluarkan pengecualian anda dapat menggunakan - try:box setelah itu sertakan - - except: statement

# Contoh

- Pada saat kita ingin membuka file menulis konten file dan keluar dari file tersebut dengan aman

- Kode program beserta hasil nya
```
try:
    fh = open("testlife", "w")
    fh.write("This is my test life for exception handling!!")
except IOerror:
    print("Error : cant\'tfind file or read data")
else:
    print("Written content in the file succesfully")
    fh.close()
```
![gambar1](gambar/x2.png)

- Contoh membuka file yang kita tidak dapat memiliki akses atau izin sehingga kita dapat membuat pengecualian

- Kode program dan hasil nya

# Fasal kecuali tanpa pengecualian

- kita dapat menggunakan pernyataan execption tanpa exception 

try:
You do your operatons here;
.......................................
except:
If there is any exception, then execute this block.
......................................
else:
If there is no exception then execute this block.

Pernyataan coba kecuali ini menangkap semua pengecualian yang ada menggunakan percobaan try-except pernyataan tidak di bisa di anggap sebagai praktik dalam pemrograman yang baik karena dapat memunculkan pengecualian 

# Klausa kecuali menggunakan berbagai pengecualian

- Kita juga dapat menggunakan pertanyaan exception yang kurang lebih sama

 try:
You do your operatons here;
.......................................
except(Exception1[, Exception2[,...ExceptionN]]]):
If There isbany exception from the given exception list,
Then execute this block.
......................................
else:
If there is no exception then execute this block.

# Contoh

- Pada saat coba kita tidak memiliki izin untuk dapat membuka file dalam model tulis yang juga dapat di tulis 

- Kode program dan hasil nya
```
try:
    fh = open("testlife", "r")
    fh.write("This is my test life for exception handling!!")
except IOError:
    print("Error : cant\'t find file or read data")
else:
    print("Written content in the file succesfully")
    fh.close()
```
![gambar1](gambar/x3.png)


- Contoh ketika kita ingin di tulis lebih rapih

```
try:
    fh = open("testlife", "r")
    try:
        fh.write("This is my test life for exception handling!!")
    finally:
        print("Goint to close the file")
        fh.close()
except IOError:
    print("Error : cant\'t find file or read data")
```

![gambar1](gambar/x4.png)

Pada saat kita ingin exception di lempar ke salam block try di lanjutkan dengan memblok setelau itu blok di eksekusi pengecualian tersebut di tangani dalam pernyataan kecuali jika terdapat lapisan yang lebih tinggi

# Argumen pengecualian

# Contoh

- contoh pengecualian

- Kode program dan hasil nya

```
# Define a function here :

def temp_convert(var):
    try:
        return int(var)
    except ValueError(Argument):
        print("The argument does not contain numbera\n", Argument)
# Call above function here

temp_convert("xyz")
```

![gambar1](gambar/x5.png)

# Malempar pengecualian

# Contoh

- Pengcualian dapat merupakan string, kelas, objek kurang lebih hampir semua pengecualian python menimbulkan kelas, Dengan argument yang merupakan turunan kelas 

- Mendefinisikan pengecualian dengan kode program dan hasil sebagai berikut
```
def functionName( level ):
    if level < 1:
        raise("Invalid level!".level)
        # The code below to this would not be executed
        # if we raise the exceptio
```
![gambar1](gambar/x6.png)

# Pengecualian yang di tetapkan

- Python juga dapat menguat pengecualian sendiri dengan kelas kelas 

- Contoh contoh dengan runtike eror dibuat yng merupakan subkelas berguna untuk menampilkan inforkasi saat pengecualian tangkap

- Kemudian di blok pengguna memunculkan dan di tangkap di blok kecuali variabel digunakan untuk membuat instance dari kelas network eror
```
class Networkerror(RuntimeError):
    def __int__(self, arg):
        self.arg = arg
try:
    raise Networkerror("Bad hostname")
except Networkerror(e):
    print(e.args)
```
![gambar1](gambar/x7.png)
