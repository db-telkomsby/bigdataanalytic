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
Google Colaboratory (https://colab.research.google.com/) merupakan perangkat komputasi awan (cloud computing) yang dibuat oleh Google dengan tujuan untuk memudahkan kegiatan pembelajaran dan pengolahan data dengan mudah menggunakan antarmuka berbasis Jupyter Notebook atau iPython (interactive Python). Google Colab menyediakan sebuah platform komputasi gratis berupa komputer virtual untuk setiap penggunanya yang dilengkapi dengan kemampuan pengolahan data yang memadai. Dengan memanfaatkan Google Colab, pengguna tidak perlu melakukan instalasi atau pengaturan yang rumit untuk keperluan pengolahan data dengan menggunakan Python.

## Intro to Python & Colab
### 1. Cara menggunakan Google Colab
Kamu dapat menggunakan Google Colab dengan gratis dengan syarat kamu memiliki akun google ada 2 cara menggunakan Google colab : 
#### a. Cara yang pertama kalian bisa mengaksesnya melalui GDrive dengan klik New > More > Google Colaboratory.
![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Analytics%20Essentials/images/image17.png?raw=true)

#### b. Cara yang kedua kalian bisa mengakses dengan menuliskan alamat link berikut https://colab.research.google.com/?hl=id dan mengklik New Notebook
![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Analytics%20Essentials/images/image12.png?raw=true)
![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Analytics%20Essentials/images/image18.png?raw=true)

### 2. Cara menuliskan Kode Program pada Google Colab
Menulis kode program pada google colab yaitu dengan menuliskan syntax pada code cell yang telah disediakan
![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Analytics%20Essentials/images/image10.png?raw=true)

### 3. Run Kode Program
Cara menjalankan (Run) program ialah dengan mengklik tombol play di kanan code cell ataupun klik menu diatas bertuliskan runtime dengan menyesuaikan cell mana yang ingin dijalankan.
![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Analytics%20Essentials/images/image5.png?raw=true)
![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Analytics%20Essentials/images/image11.png?raw=true)

### 4. Cara Menambahkan Code Cell/ Text Cell
Untuk menambahkan code cell dapat dilakukan dengan cara mengklik tombol Code yang ada pada bagian kiri atas notebook atau dengan cara “Ctrl + M B”
![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Analytics%20Essentials/images/image8.png?raw=true)
![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Analytics%20Essentials/images/image9.png?raw=true)



## Data Exploration
Contoh data : 
https://drive.google.com/file/d/18Htoqg91o6Ej95tVK1K0wWCPOClulf4K/view?usp=sharing 
Import Data
	Ada banyak cara untuk mengimport data, salah satunya adalah menggunakan pandas, pandas merupakan salah satu library milik python yang biasa digunakan untuk data analytics. Import library pandas tersebut dengan cara sebagai berikut:
### import library
    import pandas as pd
   #### 1. Cara memasukkan data dari GDrive
   Untuk memasukan data dari Gdrive dapat dilakukan dengan cara mengklik tombol folder > klik tombol folder Gdrive

  kalian akan melihat folder Gdrive kalian  di dalam file explorer. Selanjutnya copy path file yang akan digunakan dan masukan file tersebut dengan cara seperti dibawah ini:
  (df = pd.read_csv(‘path-file-Gdrive’, sep='separator yang digunakan pada file .csv’))
  
   #### 2. Cara memasukkan data langsung ke dalam Google Colab
   Untuk memasukan data langsung ke dalam google colab dapat dilakukan dengan cara mengklik tombol folder > klik tombol upload file. 

  Kalian akan melihat file kalian di dalam file explorer. Selanjutnya masukan file tersebut dengan cara seperti dibawah ini:
  (df = pd.read_csv(‘nama_file’, sep='separator yang digunakan pada file .csv’))
  
   #### 3. Cara membaca data
* Melihat data awal
  Untuk melihat data awal, kalian bisa menggunakan fungsi .head() yang sudah disediakan oleh library pandas. Cara menggunakan nya seperti dibawah ini:
  # Prints 10 first Row ==>
  df.head(10)

* Melihat data akhir
  Untuk melihat data akhir, kalian bisa menggunakan fungsi .tail() yang sudah disediakan oleh library pandas. Cara menggunakan nya seperti dibawah ini:
  # Prints 5 last Row
  df.tail(5)

* Melihat jumlah kolom dan baris
  Untuk melihat jumlah kolom dan baris kalian bisa menggunakan fungsi .shape yang sudah disediakan oleh library pandas. Cara menggunakan nya seperti dibawah ini:
  # Prints the amount of rows and column numbers
  df.shape

* Melihat informasi tipe data
* Melihat mean data
* Melihat median data
* Melihat mode data 
   #### 4. Cara visualisasi data
* Scatterplot
* Pair relationship

   



## Data Preparation

