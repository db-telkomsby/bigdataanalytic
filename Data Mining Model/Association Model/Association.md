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

![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Mining%20Model/Association%20Model/images/Support%20(A).png?raw=true)

Persamaan (2) adalah rumus untuk mendapatkan nilai support dari suatu kombinasi item.

![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Mining%20Model/Association%20Model/images/Support%20(A,B).png?raw=true)

- Confidence e (nilai kepastian) adalah kuat hubungan antara item dalam aturan asosiasi.
  
Rumus untuk mendapatkan nilai confidence:

![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Mining%20Model/Association%20Model/images/Confidence%20(A,B).png?raw=true)

Atau,

![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Mining%20Model/Association%20Model/images/Confidence(A=B).png?raw=true)

Sedangkan rumus mendapatkan nilai persentase confidence adalah:

![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Mining%20Model/Association%20Model/images/Confidence(A=B)%20x%20100%25.png?raw=true)

Dua proses penting Algoritma Apriori:
-  Join (Penggabungan) : Pada proses ini satu item dikombinasikan dengan item lain sampai tidak ada lagi kombinasi yang bisa terbentuk.
-  Pruning (Pemangkasan) : Pada proses ini dilakukan pemangkasan terhadap kombinasi sesuai dengan minimum support yang sebelumnya telah ditetapkan.
 

## Flowchart Algoritma Apriori 
 
![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Mining%20Model/Association%20Model/images/Flowchart%20Algoritma%20Apriori.png?raw=true)  

## Contoh Soal
