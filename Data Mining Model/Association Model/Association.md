# Modul 6
# Association Rule (Apriori)


# Tujuan : 

Mahasiswa dapat menyimpulkan konsep 
Mahasiswa dapat mengimplementasikan 
Mahasiswa dapat mengimplementasikan model  

## Table of Contents
1. [Dasar Teori](#dasar-teori)
2. [Flowchart Algoritma Apriori](#flowchart-algoritma-apriori)
4. [Contoh Soal](#contoh-soal)


## Dasar Teori
Algoritma Apriori adalah algoritma pencarian pola pada teknik data mining untuk menemukan aturan asosiatif antara suatu kombinasi item-set yang memiliki nilai keseringan tertentu sesuai dengan kriteria atau filter yang diinginkan. 

Algoritma Apriori dikembangkan oleh R. Agrawal dan R. Srikant tahun 1994. 

Nama Algoritma Apriori diambil dari frequent itemset mining pada ilmu prior knowledge. 

Algoritma Apriori termasuk pada jenis aturan asosiasi pada data mining.

Algoritma Apriori merupakan pendekatan iteratif dimana k-itemset digunakan untuk mengeksplorasi (k + 1)-itemset.

Pada penerapannya, Algoritma Apriori digunakan untuk mencari aturan-aturan yang memenuhi minimum support dan confidence. Untuk memperoleh ketentuan asosiatif dibutuhkan pencarian ketentuan yang mempunyai pola frekuensi besar (PFT). PFT dicari dengan cara mencari ketentuan yang penuhi nilai support minimum.

Aturan asosiatif memiliki dua parameter/tolak ukur yaitu:
- support (nilai penunjang) adalah suatu persentase kombinasi item dalam database.
  
Persamaan (1) adalah rumus untuk mendapatkan nilai support

![alt text]()

Persamaan (2) adalah rumus untuk mendapatkan nilai support dari suatu kombinasi item.

![alt text]()

- Confidence e (nilai kepastian) adalah kuat hubungan antara item dalam aturan asosiasi.
  
Rumus untuk mendapatkan nilai confidence:

![alt text]()

Atau,

![alt text]()

Sedangkan rumus mendapatkan nilai persentase confidence adalah:

![alt text]()

Dua proses penting Algoritma Apriori:
-  Join (Penggabungan) : Pada proses ini satu item dikombinasikan dengan item lain sampai tidak ada lagi kombinasi yang bisa terbentuk.
-  Pruning (Pemangkasan) : Pada proses ini dilakukan pemangkasan terhadap kombinasi sesuai dengan minimum support yang sebelumnya telah ditetapkan.
 

## Flowchart Algoritma Apriori 
 
![alt text]()  

## Contoh Soal
