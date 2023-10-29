# Modul 5
# Clustering (K-Means Method))

# Tujuan : 

Mahasiswa dapat menyimpulkan konsep K-Means
Mahasiswa dapat mengimplementasikan K-Means
Mahasiswa dapat mengimplementasikan model K-Means menggunakan Python 

## Table of Contents
1. [Dasar Teori](#dasar-teori)
2. [Algoritma K-Means](#algoritma-k-means)
3. [Contoh Soal](#contoh-soal)
4. [Clustering](#clustering)
5. [Import Libraries](#import-libraries)
6. [Import Raw Dataset](#import-raw-dataset)
7. [Data Preprocessing](#data-preprocessing)
8. [Naive Bayes](#naive-bayes)


## Dasar Teori
K-Means merupakan algoritma yang umum digunakan untuk clustering dokumen. Prinsip utama K-Means adalah menyusun k prototype atau pusat massa (centroid) dari sekumpulan data berdimensi. Sebelum diterapkan proses algoritma K-means, dokumen akan di preprocessing terlebih dahulu. Kemudian dokumen direpresentasikan sebagai vektor yang memiliki term dengan nilai tertentu. 
Algoritma k-means merupakan algoritma yang membutuhkan parameter input sebanyak k dan membagi sekumpulan n objek kedalam k cluster sehingga tingkat kemiripan antar anggota dalam satu cluster tinggi sedangkan tingkat kemiripan dengan anggota pada cluster lain sangat rendah. Kemiripan anggota terhadap cluster diukur dengan kedekatan objek terhadap nilai mean pada cluster atau dapat disebut sebagai centroid cluster.
- Konsep dasar dari K-Means adalah pencarian pusat cluster secara iteratif. 
- Pusat cluster ditetapkan berdasarkan jarak setiap data ke pusat cluster. 
- Proses clustering dimulai dengan mengidentifikasi data yang akan di cluster, xij (i=1,...,n; j=1,...,m) dengan n adalah jumlah data yang akan dicluster dan m adalah jumlah variabel. 
- Pada awal iterasi, pusat setiap cluster ditetapkan secara bebas (sembarang), ckj (k=1,...,K; j=1,...,m). 
- Kemudian dihitung jarak antara setiap data dengan setiap pusat cluster. 

Untuk melakukan penghitungan jarak data ke-i (Xi) pada pusat cluster ke-k (Ck), diberi nama (dik), dapat digunakan formula Euclidean, yaitu:

![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Mining%20Model/Clustering%20Model/images/gambar1.png?raw=true) 

Suatu data akan menjadi anggota dari cluster ke-J apabila jarak data tersebut ke pusat cluster ke-J bernilai paling kecil jika dibandingkan dengan jarak ke pusat cluster lainnya. 
Selanjutnya, kelompokkan data-data yang menjadi anggota pada setiap cluster.
Nilai pusat cluster yang baru dapat dihitung dengan cara mencari nilai rata-rata dari data yang menjadi anggota pada cluster tersebut, dengan rumus:

![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Mining%20Model/Clustering%20Model/images/gambar2.png?raw=true) 

## Algoritma K-Means 
 
- Tentukan jumlah cluster (K), tetapkan pusat cluster sembarang. 
- Hitung jarak setiap data ke pusat cluster. 
- Kelompokkan data ke dalam cluster yang dengan jarak yang paling pendek. 
- Hitung pusat cluster. 
- Ulangi langkah 2 - 4 hingga sudah tidak ada lagi data yang berpindah ke cluster yang lain.

## Contoh Soal

*1. Diketahui data nilai mahasiswa sebagai berikut:*

----------------------------------------------------------------------
      NO     NAMA MAHASISWA        UTS        TUGAS        UAS
     ----   ----------------      -----      -------      -----
      1	     Roy		89	    90		75
      2	     Sintia		90	    71		95
      3	     Iqbal		70	    75		80
      4	     Dilan		45	    65		59
      5	     Ratna		65	    75		53
      6	     Merry		80	    70		75
      7	     Rudi		90	    85		81
      8	     Hafiz		70	    70		73
      9	     Gede		96	    93		85
     10        Christian 		60	    55		48
     11        Justin		45	    60		58
     12        Jesika		60	    70		72
     13        Ayu			85	    90		88
     14        Siska		52	    68		55
     15        Reitama		40	    60		70
----------------------------------------------------------------------

*2. Tentukan ada berapa cluster (k) yang akan diajukan?*

Diambil 3 cluster -> pintar, sedang dan kurang

*3. Tentukan centroid (nilai tengah) dari masing-masing cluster.*
Random (Boleh diambil dari salah satu data atau menghitung rata-rata).

----------------------------------------------------------------------
	Cluster 	UTS 	TUGAS 	UAS
 	--------	----	-----	---
	Cluster 1	96	98	83
	Cluster 2	70	75	80
	Cluster 3	60	55	48
----------------------------------------------------------------------

*4. Hitung Euclidean distance (jarak Euclidean) antara data dengan masing-masing cluster.*
Data akan masuk ke cluster dengan nilai terendah.
Contoh: perhitungan pada data 1 (Roy).

- Jarak ke cluster 1:

![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Mining%20Model/Clustering%20Model/images/cluster1.png?raw=true) 

- Jarak ke cluster 2:

![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Mining%20Model/Clustering%20Model/images/cluster2.png?raw=true) 

- Jarak ke cluster 3:

![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Mining%20Model/Clustering%20Model/images/cluster3.png?raw=true) 

Karena jarak terkecil data 1 (Roy) adalah terhadap cluster 1 (12,57), maka data 1 akan dimasukan ke dalam cluster 1.
Ulangi perhitungan sampai data ke-15, maka akan didapati hasil berikut ini:

![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Mining%20Model/Clustering%20Model/images/tabel-iterasi1.png?raw=true) 

*5. Hitung ulang centroid dengan menghitung rata-rata data dari satu cluster.*
Contohnya, didapat data-data yang masuk ke cluster 1:

![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Mining%20Model/Clustering%20Model/images/tabel-cluster1.png?raw=true) 

Maka dari perhitungan ini didapat centroid cluster 1 berubah dari (96,98,83) menjadi (90, 85.8, 84.8)

- Centroid cluster 2 yang baru: (70, 71.25, 75)
- Centroid cluster 3 yang baru: (51.16, 63.83, 57.16)

*6. Apabila nilai centroid masih berubah atau ada data yang berpindah cluster, ulangi ke langkah 4.*

Karena di langkah 4 masih terjadi perubahan centroid, maka dilakukan perhitungan iterasi ke-2 yang mengulang langkah ke-4, menghitung masing-masing data terhadap centroidnya. Pada perhitungan kedua, didapatkan hasil sebagaimana berikut ini:

![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Mining%20Model/Clustering%20Model/images/tabel%20hasil.png?raw=true) 

Karena masing-masing data tetap berada di cluster yang sama dengan tahapan perhitungan pertama, maka iterasi dihentikan. Umumnya, iterasi dihentikan pada saat:
- Tidak ada data yang berpindah cluster, atau
- Nilai centroid tidak berubah, atau
- Telah berada di maksimum iterasi 🡪 biasanya digunakan untuk data yang besar. 

# Clustering

Analisis klaster atau pengelompokan adalah tugas mengelompokkan sekumpulan objek sedemikian rupa sehingga objek-objek dalam kelompok yang sama (disebut klaster) lebih mirip (dalam beberapa hal) satu sama lain dibandingkan dengan objek-objek dalam kelompok (cluster) lainnya.

Di sini kami memodelkan pengelompokan dari data pendapatan dan pengeluaran pelanggan. Kami menggunakan model ini untuk melakukan segmentasi pelanggan. Kami membedakan pelanggan ke dalam jumlah kelompok yang optimal berdasarkan pendapatan dan pengeluaran mereka.

## Import Libraries

```
from sklearn.cluster import KMeans
import pandas as pd
from sklearn.preprocessing import MinMaxScaler
from matplotlib import pyplot as plt
#%matplotlib inline
```

## Import Raw Dataset
```
path = 'https://raw.githubusercontent.com/db-telkomsby/bigdataanalytic/main/Data%20Mining%20Model/Clustering%20Model/clustering.csv'
df = pd.read_csv(path, sep = ",")
df.head
```

## Determining SSE and SME
```
k_rng = range(1,10)
sse = []
for k in k_rng:
  km=KMeans(n_clusters=k)
  km.fit(df[['INCOME','SPEND']])
  sse.append(km.inertia_)
```

```
sse
```

```
plt.xlabel('k')
plt.ylabel('Sum of squared error')
plt.plot(k_rng,sse)
```

```
plt.scatter(df['INCOME'],df['SPEND'])
plt.xlabel('INCOME')
plt.ylabel('SPEND')
```

```
km = KMeans(n_clusters=3, random_state=42)
km
```

```
y_predicted = km.fit_predict(df[['INCOME','SPEND']])
y_predicted
```

```
df['cluster'] = y_predicted
df.head()
```

```
df1 = df[df.cluster==0]
df2 = df[df.cluster==1]
df3 = df[df.cluster==2]
plt.scatter(df1.INCOME,df1['SPEND'], color='green')
plt.scatter(df2.INCOME,df2['SPEND'], color='yellow')
plt.scatter(df3.INCOME,df3['SPEND'], color='red')
plt.xlabel('INCOME')
plt.ylabel('SPEND')
plt.legend
```

```
scaler = MinMaxScaler()

scaler.fit(df[['INCOME']])
df['INCOME'] = scaler.transform(df[['INCOME']])

scaler.fit(df[['SPEND']])
df['SPEND'] = scaler.transform(df[['SPEND']])
df.head
```

```
km=KMeans(n_clusters=3, random_state=42)
y_predicted=km.fit_predict(df[['INCOME','SPEND']])
y_predicted
```

```
df['cluster']=y_predicted
df
```

```
km.cluster_centers_
```

```
df1 = df[df.cluster==0]
df2 = df[df.cluster==1]
df3 = df[df.cluster==2]
plt.scatter(df1.INCOME,df1['SPEND'], color='green')
plt.scatter(df2.INCOME,df2['SPEND'], color='yellow')
plt.scatter(df3.INCOME,df3['SPEND'], color='red')
plt.scatter(km.cluster_centers_[:,0],km.cluster_centers_[:,1],color='black',marker='*',label='centroid')
plt.xlabel('INCOME')
plt.ylabel('SPEND')
plt.legend
```

```
df
```
