# Modul 1
# Introduction Google Colab, Data Exploration dan Data Preparation

## Tujuan : 
- Mahasiswa dapat  memahami fungsi dari Google Colab
- Mahasiswa dapat menggunakan Google Colab
- Mahasiswa dapat memahami dan menghasilkan Data Exploration dan Data Preparation

## Table of Contents
1. [Dasar Teori](#dasar-teori)
2. [Intro to Python & Colab](#intro-to-python--colab)
3. [Data Exploration](#data-exploration)
4. [Data Preparation](#data-preparation)

## Dasar Teori :
Python merupakan salah satu bahasa pemrograman dengan kode yang jelas, lengkap, dan mudah untuk dipahami. Python menjadi bahasa pemrograman yang digunakan dalam pembuatan aplikasi berbasis kecerdasan buatan (artificial intelligence). Python dikembangkan pada 1991 oleh Guido van Rossum (programmer Belanda) di CWI, Amsterdam. Nama python berasal dari nama acara televisi kesayangan Guido yaitu Monty Python's Flying Circus.

Kenapa python? Python terampil dalam menyelesaikan permasalahan big data, data mining, deep learning, data science, hingga machine learning. Secara umum python memiliki bentuk pemrograman berorientasi objek, pemrograman imperatif, dan pemrograman fungsional.
Python memiliki fitur dan kelebihan sebagai berikut:

1. Memiliki berbagai kepustakaan/modul
2. Berorientasi prosedural dan objek sekaligus (multiparadigma)
3. Memiliki sistem pengelolaan memori otomatis
4. Bersifat modular sehingga mudah untuk dikembangkan dalam membuat modul baru

Code editor yang dapat digunakan untuk pengembangan Python diantaranya adalah Google Collab (Colaboratory), Visual Studio Code (VS Code), IDLE (Python's Integrated Development and Learning Environment), PyCharm (Development Environment (IDE) yang kuat yang dikembangkan oleh JetBrains), Jupyter Notebook, dll.

Kenapa Google Colaboratory?
Google Colaboratory (https://colab.research.google.com/) merupakan perangkat komputasi awan (cloud computing) yang dibuat oleh Google dengan tujuan untuk memudahkan kegiatan pembelajaran dan pengolahan data dengan mudah menggunakan antarmuka berbasis Jupyter Notebook atau iPython (interactive Python). Google Colab menyediakan sebuah platform komputasi gratis berupa komputer virtual untuk setiap penggunanya yang dilengkapi dengan kemampuan pengolahan data yang memadai. Dengan memanfaatkan Google Colab, pengguna tidak perlu melakukan instalasi atau pengaturan yang rumit untuk keperluan pengolahan data dengan menggunakan Python.

## Intro to Python & Colab

**1. Cara menggunakan Google Colab**

Kamu dapat menggunakan Google Colab dengan gratis dengan syarat kamu memiliki akun google ada 2 cara menggunakan Google colab : 

a. Cara yang pertama kalian bisa mengaksesnya melalui GDrive dengan klik New > More > Google Colaboratory.
![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Analytics%20Essentials/images/image17.png?raw=true)

b. Cara yang kedua kalian bisa mengakses dengan menuliskan alamat link berikut https://colab.research.google.com/?hl=id dan mengklik New Notebook
![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Analytics%20Essentials/images/image12.png?raw=true)
![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Analytics%20Essentials/images/image18.png?raw=true)

**2. Cara menuliskan Kode Program pada Google Colab**

Menulis kode program pada google colab yaitu dengan menuliskan syntax pada code cell yang telah disediakan
![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Analytics%20Essentials/images/image10.png?raw=true)

**3. Run Kode Program**

Cara menjalankan (Run) program ialah dengan mengklik tombol play di kanan code cell ataupun klik menu diatas bertuliskan runtime dengan menyesuaikan cell mana yang ingin dijalankan.
![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Analytics%20Essentials/images/image5.png?raw=true)
![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Analytics%20Essentials/images/image11.png?raw=true)

**4. Cara Menambahkan Code Cell/ Text Cell**

Untuk menambahkan code cell dapat dilakukan dengan cara mengklik tombol Code yang ada pada bagian kiri atas notebook atau dengan cara “Ctrl + M B”
![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Analytics%20Essentials/images/image8.png?raw=true)
![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Analytics%20Essentials/images/image9.png?raw=true)



## Data Exploration

Contoh data : 
https://drive.google.com/file/d/18Htoqg91o6Ej95tVK1K0wWCPOClulf4K/view?usp=sharing 

Import Data

 Ada banyak cara untuk mengimport data, salah satunya adalah menggunakan pandas, pandas merupakan salah satu library milik python yang biasa digunakan untuk data analytics. Import library pandas tersebut dengan cara sebagai berikut:

**import library**

```
import pandas as pd
```

**1. Cara memasukkan data dari GDrive**
   
   Untuk memasukan data dari Gdrive dapat dilakukan dengan cara mengklik tombol folder > klik tombol folder Gdrive
![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Analytics%20Essentials/images/Cara%20memasukkan%20data%20dari%20GDrive.png?raw=true)

kalian akan melihat folder Gdrive kalian  di dalam file explorer. Selanjutnya copy path file yang akan digunakan dan masukan file tersebut dengan cara seperti dibawah ini:
	(df = pd.read_csv(‘path-file-Gdrive’, sep='separator yang digunakan pada file .csv’))
![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Analytics%20Essentials/images/data-GDrive.png?raw=true)

**2. Cara memasukkan data langsung ke dalam Google Colab**
   
   Untuk memasukan data langsung ke dalam google colab dapat dilakukan dengan cara mengklik tombol folder > klik tombol upload file. 
![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Analytics%20Essentials/images/Cara%20memasukkan%20data%20langsung%20ke%20dalam%20Google%20Colab.png?raw=true)

Kalian akan melihat file kalian di dalam file explorer. Selanjutnya masukan file tersebut dengan cara seperti dibawah ini:
	(df = pd.read_csv(‘nama_file’, sep='separator yang digunakan pada file .csv’))
![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Analytics%20Essentials/images/data-fileExplorer.png?raw=true)


**3. Cara membaca data**

a. Melihat data awal

  Untuk melihat data awal, kalian bisa menggunakan fungsi .head() yang sudah disediakan oleh library pandas. Cara menggunakan nya seperti dibawah ini:

***Prints 10 first Row***
	
```
 df.head(10)
```

b. Melihat data akhir
  
  Untuk melihat data akhir, kalian bisa menggunakan fungsi .tail() yang sudah disediakan oleh library pandas. Cara menggunakan nya seperti dibawah ini:

***Prints 5 last Row***

```
 df.tail(5)
```

c. Melihat jumlah kolom dan baris
  Untuk melihat jumlah kolom dan baris kalian bisa menggunakan fungsi .shape yang sudah disediakan oleh library pandas. Cara menggunakan nya seperti dibawah ini:

***Prints the amount of rows and column numbers***

```
df.shape
```

d. Melihat informasi tipe data
  Untuk melihat informasi tipe data, kalian bisa menggunakan fungsi .info() yang sudah disediakan oleh library pandas. Cara menggunakan nya seperti dibawah ini:

***Prints information about a DataFrame including the index dtype and column dtypes, non-null values and memory usage***

```
df.info()
```
 
**4. Pemusatan data (Central Tendency Measurement)**

a. Melihat mean data

Untuk melihat mean data, kalian bisa menggunakan fungsi .mean() yang sudah disediakan oleh library pandas. Seperti berikut:

***melihat mean data***

```
df_num = df[['Harga','Jumlah Terjual']]
df_num.mean()
```

b. Melihat median data

Untuk melihat median data, kalian bisa menggunakan fungsi .median() yang sudah disediakan oleh library pandas. Seperti berikut:

***melihat median data***

``` 
df_num.median()
```

c. Melihat mode data 

Untuk melihat mode data, kalian bisa menggunakan fungsi .mode() yang sudah disediakan oleh library pandas. Seperti berikut:

***melihat mode data***

``` 
df_num.mode()
```

**5. Statistika deskriptif**

 Statistik deskriptif merupakan bidang ilmu statistika yang mempelajari cara cara pengumpulan, penyusunan, dan penyajian data suatu penelitian. Statistik deskriptif adalah bagian dari ilmu statistik yang meringkas, menyajikan dan mendeskripsikan data dalam bentuk yang mudah dibaca sehingga memberikan informasi tersebut lebih lengkap. Statistik deskriptif hanya berhubungan dengan hal menguraikan atau memberikan keterangan-keterangan mengenai suatu data atau keadaan atau fenomena, dengan kata lain hanya melihat gambaran secara umum dari data yang didapatkan. 
 
**6. Cara korelasi data**
 
  Untuk mengetahui seberapa dekat hubungan antar semua kolom dalam tabel data, kalian bisa pakai fungsi .corr() dari Pandas. Cara menggunakan seperti dibawah ini:

***Melihat korelasi data menggunakan metode kendal***

``` 
correlation_matrix = df.corr(method='kendall')
```

***Print Correlation Matrix***

```
correlation_matrix
```

**4. Cara visualisasi data**

a. Scatterplot

Untuk visualisasi data menggunakan Scatterplot, kalian bisa menggunakan seperti dibawah ini

***visualisasi data menggunakan scatterplot***

```
sns.scatterplot(x='Harga', y='Jumlah Terjual', data= df)
```

## Data Preparation

**1. Cara menghapus baris yang memiliki nilai hilang**

Menghapus baris yang memiliki nilai yang hilang di beberapa kolom atau baris yang benar-benar kosong

```
df.dropna(subset=['Kategori'], inplace=True)
```

**2. Cara menghapus baris yang duplikat**

Merapikan dataset dengan menghapus baris duplikat (jika ada)

```
df.drop_duplicates(inplace=True)
```

**3. Cara mengganti nilai yang hilang**

Di sini, kita akan mengganti nilai yang hilang di kolom 'Harga' dan 'Jumlah Terjual' dengan 0 atau dengan yang sesuai

```
df['Harga'].fillna(0, inplace=True)
df['Jumlah Terjual'].fillna(0, inplace=True)
```

**4. Cara Menyimpan dataset**

Menyimpan dataset yang telah diolah ke dalam file CSV, Gantilah 'nama_file_cleaned.csv' dengan nama file yang sesuai

```
df.to_csv('nama_file_cleaned.csv', index=False)
```

