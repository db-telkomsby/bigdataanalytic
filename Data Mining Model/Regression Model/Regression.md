# Modul 2
# Regression Model

## Tujuan : 
- Mahasiswa dapat menyimpulkan konsep regression model 
- Mahasiswa dapat mengimplementasikan persamaan regression model
- Mahasiswa dapat mengimplementasikan regression model menggunakan Python

## Table of Contents
1. [Dasar Teori](#dasar-teori)
2. [Intro to Python & Colab](#intro-to-python--colab)
3. [Data Exploration](#data-exploration)
4. [Data Preparation](#data-preparation)

## Dasar Teori :

Regresi linier adalah jenis algoritma pembelajaran mesin terawasi yang berfokus pada hubungan antara variabel dependen (y) dan satu atau lebih variabel independen (x). Tujuan dari regresi linier adalah untuk menemukan garis yang paling sesuai yang mewakili titik-titik data dan memprediksi nilai variabel dependen berdasarkan variabel independen yang diberikan. Hubungan antara variabel-variabel tersebut dinyatakan melalui persamaan y = mx + c, di mana y adalah output yang diprediksi, x adalah input, m adalah kemiringan atau gradien garis, dan c adalah intersep y.

Terdapat berbagai jenis teknik regresi, masing-masing cocok untuk skenario yang berbeda. Beberapa teknik regresi yang umum digunakan meliputi:
1. Regresi Linier: Bentuk regresi yang paling dasar, yang mengasumsikan hubungan linier antara variabel.
2. Regresi Ridge dan Lasso: Ini adalah teknik regularisasi yang digunakan untuk pemilihan fitur dan untuk mencegah overfitting. Regresi Ridge memperkenalkan istilah regularisasi ||w||, di mana w mewakili koefisien persamaan regresi. Hal ini membantu mengurangi dampak dari fitur yang tidak relevan atau berkorelasi tinggi dalam model. Regresi Lasso, juga dikenal sebagai regularisasi L1, menambahkan istilah penalti yang dapat mengecilkan koefisien menjadi nol, secara efektif memilih fitur dan meningkatkan kemampuan interpretasi.
3. Regresi Elastis: Teknik ini menggabungkan sifat-sifat regresi Ridge dan Lasso. Teknik ini memungkinkan pemilihan variabel seperti Lasso dengan tetap mempertahankan sifat regularisasi regresi Ridge.
4. Regresi Logistik: Digunakan ketika variabel dependen adalah kategorikal atau biner, regresi logistik memprediksi probabilitas hasil tertentu daripada nilai kontinu.
5. Regresi Polinomial: Teknik ini memperluas regresi linier dengan menambahkan istilah polinomial ke dalam persamaan. Teknik ini dapat menangkap hubungan non-linear antar variabel.

- Rumus Linear Regression

- Contoh soal dan pengerjaan

Data disajikan dalam bentuk tabel dimana X merupakan lama penayangan iklan dalam satuan minggu sedangkan Y adalah penjualan produk Internet Of Think tersebut sebagaimana terlihat dibawah ini:

-----------------------------------------------------------------
      No           Lama Iklan            Penjualan Produk (Y)
                dalam Minggu (x)
    -------   --------------------    ---------------------------
       1               20                          30           
       2               40                          60 
       3               20                          40  
       4               30                          60
       5               10                          30
       6               10                          40
       7               20                          40
       8               20                          50
       9               20                          30
       10              30                          70
-----------------------------------------------------------------

Hitunglah berapa banyak penjualan dengan iklan selama 25 hari?
1. Hitung rata-rata dari variabel X atau ![alt text](?raw=true) dan variabel Y atau ![alt text](?raw=true)

![alt text](?raw=true)

2. Hitung ![alt text](?raw=true)

![alt text](?raw=true)

![alt text](?raw=true)

![alt text](?raw=true)

3. Hitung b dan a

![alt text](?raw=true)            ![alt text](?raw=true)

5. Bentuk Model Regresi Linier Sederhana

![alt text](?raw=true)

5. Hitung Jumlah Produk Internet of Think yang Terjual bila penayangan iklan selama 25 hari

![alt text](?raw=true)

Jumlah prediksi Produk Internet Of Think yang terjual adalah sebanyak 49 buah.


6. Hitung Koefisien Korelasi (r) antara Waktu tayang iklan dengan Jumlah Produk yang Terjual.

![alt text](?raw=true)

Kriteria Koefisien Korelasi

----------------------------------
      Nilai r          Korelasi
   -------------    --------------
    0,0 – 0,29       Sangat Lemah
    0,3 – 0,49          Lemah
    0,5 – 0,69          Cukup
    0,7 – 0,79           Kuat
    0,8 – 1,00        Sangat Kuat
----------------------------------

r = 0,76 

Nilainya r positif artinya terdapat korelasi searah antara waktu penayangan iklan dengan jumlah penjualan produk IoT yang terjual. Hubungan searah berarti jika terdapat kenaikan lama penayangan iklan maka akan menaikan jumlah penjualan produk IoT.

7. Hitung Koefisian Determinasi (r2) 

![alt text](?raw=true)

Nilainya r2 = 0,5776 atau 57,76% menjelaskan besarnya pengaruh atau kontribusi dari waktu penayangan iklan terhadap nilai jumlah penjualan produk IoT. Sedangkan 42,24% nya dipengaruhi oleh variable lainnya.


