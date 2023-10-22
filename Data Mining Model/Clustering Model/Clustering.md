# Modul 5
# Clustering (K-Means Method))

# Tujuan : 

Mahasiswa dapat menyimpulkan konsep K-Means
Mahasiswa dapat mengimplementasikan K-Means
Mahasiswa dapat mengimplementasikan model K-Means menggunakan Python 

## Dasar Teori :
K-Means merupakan algoritma yang umum digunakan untuk clustering dokumen. Prinsip utama K-Means adalah menyusun k prototype atau pusat massa (centroid) dari sekumpulan data berdimensi. Sebelum diterapkan proses algoritma K-means, dokumen akan di preprocessing terlebih dahulu. Kemudian dokumen direpresentasikan sebagai vektor yang memiliki term dengan nilai tertentu. 
Algoritma k-means merupakan algoritma yang membutuhkan parameter input sebanyak k dan membagi sekumpulan n objek kedalam k cluster sehingga tingkat kemiripan antar anggota dalam satu cluster tinggi sedangkan tingkat kemiripan dengan anggota pada cluster lain sangat rendah. Kemiripan anggota terhadap cluster diukur dengan kedekatan objek terhadap nilai mean pada cluster atau dapat disebut sebagai centroid cluster.
- Konsep dasar dari K-Means adalah pencarian pusat cluster secara iteratif. 
- Pusat cluster ditetapkan berdasarkan jarak setiap data ke pusat cluster. 
- Proses clustering dimulai dengan mengidentifikasi data yang akan di cluster, xij (i=1,...,n; j=1,...,m) dengan n adalah jumlah data yang akan dicluster dan m adalah jumlah variabel. 
- Pada awal iterasi, pusat setiap cluster ditetapkan secara bebas (sembarang), ckj (k=1,...,K; j=1,...,m). 
- Kemudian dihitung jarak antara setiap data dengan setiap pusat cluster. 

Untuk melakukan penghitungan jarak data ke-i (Xi) pada pusat cluster ke-k (Ck), diberi nama (dik), dapat digunakan formula Euclidean, yaitu:

Suatu data akan menjadi anggota dari cluster ke-J apabila jarak data tersebut ke pusat cluster ke-J bernilai paling kecil jika dibandingkan dengan jarak ke pusat cluster lainnya. 
Selanjutnya, kelompokkan data-data yang menjadi anggota pada setiap cluster.
Nilai pusat cluster yang baru dapat dihitung dengan cara mencari nilai rata-rata dari data yang menjadi anggota pada cluster tersebut, dengan rumus:

## Algoritma K-Means 
 
- Tentukan jumlah cluster (K), tetapkan pusat cluster sembarang. 
- Hitung jarak setiap data ke pusat cluster. 
- Kelompokkan data ke dalam cluster yang dengan jarak yang paling pendek. 
- Hitung pusat cluster. 
- Ulangi langkah 2 - 4 hingga sudah tidak ada lagi data yang berpindah ke cluster yang lain.

Contoh Soal:

Diketahui data nilai mahasiswa sebagai berikut:

----------------------------------------------------------------------
      NO     NAMA MAHASISWA       UTS        TUGAS        UAS
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
      10      Christian 	60	    55		48
      11      Justin		45	    60		58
      12      Jesika		60	    70		72
      13      Ayu		85	    90		88
      14      Siska		52	    68		55
      15      Reitama		40	    60		70
----------------------------------------------------------------------

Tentukan ada berapa cluster (k) yang akan diajukan?
Diambil 3 cluster -> pintar, sedang dan kurang
Tentukan centroid (nilai tengah) dari masing-masing cluster. Random (Boleh diambil dari salah satu data atau menghitung rata-rata).

Cluster
UTS
TUGAS
UAS
Cluster 1
96
98
83
Cluster 2
70
75
80
Cluster 3
60
55
48


Hitung Euclidean distance (jarak Euclidean) antara data dengan masing-masing cluster. Data akan masuk ke cluster dengan nilai terendah.
Contoh: perhitungan pada data 1 (Roy).
Jarak ke cluster 1:
d(1,1)= 89-962 + 90-982+ 75-832=12,57
Jarak ke cluster 2:
d(1,2)= 89-702 + 90-752+ 75-802=24,72
Jarak ke cluster 3:
d(1,3)= 89-602 + 90-552+ 75-482=52,87
Karena jarak terkecil data 1 (Roy) adalah terhadap cluster 1 (12,57), maka data 1 akan dimasukan ke dalam cluster 1.
Ulangi perhitungan sampai data ke-15, maka akan didapati hasil berikut ini:



	
No
Nama Mahasiswa
Jarak Ke Cluster
Hasil
Cluster 1
Cluster 2
Cluster 3
1.
Roy
12,57
24,72
52,87
1
2.
Sintia
24,90
25,32
58,01
1
3.
Iqbal
32,02
0,00
39,04
2
4.
Dilan
63,73
34,15
21,12
3
5.
Ratna
48,05
27,46
21,21
3
6.
Merry
29,75
12,25
36,80
2
7.
Rudi
10,77
22,38
53,75
1
8.
Hafiz
36,73
8,60
30,82
2
9.
Gede
0,00
32,02
64,10
1
10.
Christian
64,10
39,04
0,00
3
11.
Justin
66,48
36,52
18,71
3
12.
Jesika
44,65
13,75
28,30
2
13.
Ayu
11,79
22,67
58,74
1
14.
Siska
58,83
31,59
16,79
3
15.
Reitama
66,71
35,00
30,15
3





















Hitung ulang centroid dengan menghitung rata-rata data dari satu cluster.
Contohnya, didapat data-data yang masuk ke cluster 1:

Nama Mahasiswa
UTS
TUGAS
UAS
Roy
89
90
75
Sintia
90
71
95
Rudi
90
85
81
Gede
96
93
85
Ayu
85
90
88
Average:
90 🡪 91.25
85,8 🡪 84,75
84,8 🡪 84


Maka dari perhitungan ini didapat centroid cluster 1 berubah dari (96,98,83) menjadi (90, 85.8, 84.8)

Centroid cluster 2 yang baru: (70, 71.25, 75)
Centroid cluster 3 yang baru: (51.16, 63.83, 57.16)

Apabila nilai centroid masih berubah atau ada data yang berpindah cluster, ulangi ke langkah 4.

Karena di langkah 4 masih terjadi perubahan centroid, maka dilakukan perhitungan iterasi ke-2 yang mengulang langkah ke-4, menghitung masing-masing data terhadap centroidnya. Pada perhitungan kedua, didapatkan hasil sebagaimana berikut ini:

No
Nama Mahasiswa
Jarak Ke Cluster
Hasil
C1
C2
C3
1.
Roy
10,71
26,69
49,34
1
2.
Sintia
17,97
28,29
54,69
1
3.
Iqbal
23,23
6,25
31,63
2
4.
Dilan
55,89
30,33
6,54
3
5.
Ratna
41,87
22,87
18,26
3
6.
Merry
21,11
10,08
34,46
2
7.
Rudi
3,88
25,00
50,24
1
8.
Hafiz
28,09
2,36
25,37
2
9.
Gede
9,37
35,34
60,29
1
10.
Christian
56,59
33,06
15,49
3
11.
Justin
58,39
32,26
7,31
3
12.
Jesika
36,24
10,51
18,33
2
13.
Ayu
7,27
27,30
52,73
1
14.
Siska
51,47
27,10
4,77
3
15.
Reitama
58,18
32,43
17,44
3


Karena masing-masing data tetap berada di cluster yang sama dengan tahapan perhitungan pertama, maka iterasi dihentikan. Umumnya, iterasi dihentikan pada saat:
Tidak ada data yang berpindah cluster, atau
Nilai centroid tidak berubah, atau
Telah berada di maksimum iterasi 🡪 biasanya digunakan untuk data yang besar. 
