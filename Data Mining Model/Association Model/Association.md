# Modul 6
# Association Rule (Apriori)


## Tujuan : 

Mahasiswa dapat menyimpulkan konsep 
Mahasiswa dapat mengimplementasikan 
Mahasiswa dapat mengimplementasikan model  

## Table of Contents
1. [Dasar Teori](#dasar-teori)
2. [Flowchart Algoritma Apriori](#flowchart-algoritma-apriori)
4. [Contoh Soal](#contoh-soal)


## Dasar Teori
Algoritma Apriori adalah algoritma pencarian pola pada teknik data mining untuk menemukan aturan asosiatif antara suatu kombinasi item-set yang memiliki nilai keseringan tertentu sesuai dengan kriteria atau filter yang diinginkan. 

- Algoritma Apriori dikembangkan oleh R. Agrawal dan R. Srikant tahun 1994. 

- Nama Algoritma Apriori diambil dari frequent itemset mining pada ilmu prior knowledge. 

- Algoritma Apriori termasuk pada jenis aturan asosiasi pada data mining.

- Algoritma Apriori merupakan pendekatan iteratif dimana k-itemset digunakan untuk mengeksplorasi (k + 1)-itemset.

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
Diketahui basis data transaksi peminjaman buku di suatu perpustakaan, dengan iketahui minimum support = 18% sebagai berikut:
![alt text]()  

Inisiasi

![alt text]()  

Diketahui minimum support = 18%

Iterasi ke-1

![alt text]()  

![alt text]()  


Iterasi ke-2

![alt text]()  

![alt text]()  

Iterasi ke-3

![alt text]()  

![alt text]() 

Aturan asosiatif


Jika meminjam buku x, maka direkomendasikan buku y.

Misalkan: Jika meminjam buku statistics dan linear algebra, maka seberapa direkomendasikan buku intro to data mining?

x dan y = statistics, linear algebra, dan intro to data mining = 18.42%

statistics dan linear algebra	= 34.21% 
          
Confidence = 53.84%

Maka tingkat rekomendasi buku intro to data mining adalah 53.84%.


## Import Library
```
import pandas as pd
import numpy as np
import seaborn as sns
from mlxtend.frequent_patterns import apriori
from mlxtend.frequent_patterns import association_rules
```

## Import dataset
```
retail_df = pd.read_excel("https://github.com/rc-dbe/bigdatacertification/blob/master/dataset/Online%20Retail.xlsx?raw=true")
retail_df.head()
```

```
# Remove additional spaces
retail_df['Description'] = retail_df['Description'].str.strip()

# Remove NA values
retail_df.dropna(axis=0, subset=['InvoiceNo'], inplace=True)

# Remove cancelled orders
retail_df['InvoiceNo'] = retail_df['InvoiceNo'].astype('str')
retail_df = retail_df[~retail_df['InvoiceNo'].str.contains('C')]
```

```
# Create Encode Function
def encode_units(x):
    if x <= 0:
        return 0
    if x >= 1:
        return 1

def create_basket(country_filter):
    basket = (retail_df[retail_df['Country'] == country_filter]
          .groupby(['InvoiceNo', 'Description'])['Quantity']
          .sum().unstack().reset_index().fillna(0)
          .set_index('InvoiceNo'))
    return basket
```

```
country_filter = "France"
basket_french = create_basket("France")
basket_sets = basket_french.applymap(encode_units)
basket_sets.drop('POSTAGE', inplace=True, axis=1)
```

```
frequent_itemsets = apriori(basket_sets, min_support=0.05, use_colnames=True)
```

```
# Generate Rules
rules = association_rules(frequent_itemsets, metric="lift", min_threshold=1.2)
rules.head()
```

```
# Sorting
rules.sort_values(["confidence"], axis=0,
                 ascending=False, inplace=True)
rules
```
