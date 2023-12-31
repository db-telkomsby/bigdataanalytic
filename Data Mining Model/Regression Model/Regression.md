# Modul 2
# Regression Model

## Tujuan : 
- Mahasiswa dapat menyimpulkan konsep regression model 
- Mahasiswa dapat mengimplementasikan persamaan regression model
- Mahasiswa dapat mengimplementasikan regression model menggunakan Python

## Table of Contents
1. [Dasar Teori](#dasar-teori)
2. [Rumus Linear Regression](#rumus-linear-regression)
3. [Contoh Soal dan Pengerjaan](#contoh-soal-dan-pengerjaan)
4. [Import Libraries](#import-libraries)
5. [Load Dataset](#load-dataset)
6. [Data Preparation](#data-preparation)
7. [OLS Regression Results](#ols-regression-results)
8. [Linear Regression Model](#linear-regression-model)
9. [Prediction results](#prediction-results)
10. [Scatter Plots](#scatter-plots)
11. [New Prediction](#new-prediction)

## Dasar Teori :

Regresi linier adalah salah satu metode dalam pembelajaran mesin yang fokusnya adalah mencari hubungan antara variabel dependen (y) dengan satu atau lebih variabel independen (x). Dasarnya, regresi linier bertujuan untuk menemukan garis yang paling cocok untuk menggambarkan data dan kemudian digunakan untuk memprediksi nilai variabel dependen berdasarkan variabel independen yang kita miliki. Hubungan antara variabel-variabel tersebut dinyatakan melalui persamaan y = mx + c, di mana y adalah output yang diprediksi, x adalah input, m adalah kemiringan atau gradien garis, dan c adalah intersep y.

Terdapat berbagai jenis teknik regresi, masing-masing cocok untuk skenario yang berbeda. Beberapa teknik regresi yang umum digunakan meliputi:
1. Simple Linear Regression (Regresi Linier Sederhana) adalah jenis regresi digunakan untuk memahami hubungan antara dua variabel: satu variabel dependen (biasanya disebut Y) dan satu variabel independen (biasanya disebut X). Tujuannya adalah untuk menemukan garis lurus (linier) yang paling sesuai untuk mewakili data sehingga kita dapat memprediksi nilai Y berdasarkan nilai X.
2. Multiple Linear Regression (Regresi Linier Berganda) adalah perkembangan dari simple linear regression yang memungkinkan kita untuk memahami hubungan antara satu variabel dependen (Y) dengan dua atau lebih variabel independen (X1, X2, X3, dll). Tujuannya adalah untuk menemukan model matematis yang memadai untuk menggambarkan hubungan kompleks antara variabel dependen dan independen sehingga kita dapat memprediksi nilai Y berdasarkan kombinasi nilai X.
3. Logistic Regression (Regresi Logistik) adalah jenis regresi yang digunakan ketika variabel dependen adalah biner atau kategorikal, yaitu memiliki dua kategori seperti "Ya/Tidak" atau "Berhasil/Gagal". Tujuannya adalah untuk memahami hubungan antara variabel independen (X) dan probabilitas bahwa variabel dependen akan masuk ke dalam salah satu kategori. Ini digunakan terutama dalam klasifikasi.

## Rumus Linear Regression

![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Mining%20Model/Regression%20Model/images/image16.png?raw=true)

## Contoh Soal dan Pengerjaan

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
1. Hitung rata-rata dari variabel X dan variabel Y 
![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Mining%20Model/Regression%20Model/images/image12.png?raw=true)
![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Mining%20Model/Regression%20Model/images/image4.png?raw=true)

2. Hitung S<sub>xx</sub> , S<sub>yy</sub> , S<sub>xy</sub>

![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Mining%20Model/Regression%20Model/images/image8.png?raw=true)

![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Mining%20Model/Regression%20Model/images/image6.png?raw=true)

![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Mining%20Model/Regression%20Model/images/image1.png?raw=true)

3. Hitung b dan a

![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Mining%20Model/Regression%20Model/images/image7.png?raw=true)            
![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Mining%20Model/Regression%20Model/images/image2.png?raw=true)

4. Bentuk Model Regresi Linier Sederhana

![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Mining%20Model/Regression%20Model/images/image9.png?raw=true)

5. Hitung Jumlah Produk Internet of Think yang Terjual bila penayangan iklan selama 25 hari

![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Mining%20Model/Regression%20Model/images/image17.png?raw=true)

Jumlah prediksi Produk Internet Of Think yang terjual adalah sebanyak 49 buah.


6. Hitung Koefisien Korelasi (r) antara Waktu tayang iklan dengan Jumlah Produk yang Terjual.

![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Mining%20Model/Regression%20Model/images/image14.png?raw=true)

Kriteria Koefisien Korelasi

-----------------------------------
      Nilai r          Korelasi
     ---------        ----------
    0,0 – 0,29       Sangat Lemah
    0,3 – 0,49          Lemah
    0,5 – 0,69          Cukup
    0,7 – 0,79           Kuat
    0,8 – 1,00        Sangat Kuat
-----------------------------------

r = 0,76 

Nilainya r positif artinya terdapat korelasi searah antara waktu penayangan iklan dengan jumlah penjualan produk IoT yang terjual. Hubungan searah berarti jika terdapat kenaikan lama penayangan iklan maka akan menaikan jumlah penjualan produk IoT.

7. Hitung Koefisian Determinasi (r2) 

![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Mining%20Model/Regression%20Model/images/image13.png?raw=true)

Nilainya r2 = 0,5776 atau 57,76% menjelaskan besarnya pengaruh atau kontribusi dari waktu penayangan iklan terhadap nilai jumlah penjualan produk IoT. Sedangkan 42,24% nya dipengaruhi oleh variable lainnya.


## Import Libraries

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

from sklearn.linear_model import LinearRegression
from sklearn.model_selection import train_test_split
from sklearn import metrics
from sklearn.metrics import classification_report
from sklearn.metrics import r2_score
import statsmodels.formula.api as smf

import warnings
warnings.filterwarnings('ignore')
```


## Load Dataset

```
df = pd.read_csv('Modul2Tambahan.csv')
df
```

```
df.head(5)
```

```
df.tail(5)
```

```
df.sample(10)
```

```
df.columns
```

```
df.info()
```

```
df.describe()
```

## Data Preparation

```
obj=df.select_dtypes(include=['object'])
num=df.select_dtypes(exclude=['object'])
```

```
obj
```

```
num
```

```
num.isna().sum()
```

```
num.isna().any().sum()
```

```
num.duplicated().value_counts()
```

```
num.duplicated().sum()
```

## OLS Regression Results

```
statMDL=smf.ols('Gaji~Divisi+Usia+LamaKerja',data=num).fit()
print(statMDL.summary())
```

```
x=df[['Usia','LamaKerja']]
y=df['Gaji']
```

## Linear Regression Model

```
x_train, x_test, y_train, y_test = train_test_split(x,y,test_size=0.50,random_state=42)
l = LinearRegression()
l.fit(x_train,y_train)
```

```
predictions=l.predict(x_test)
```

## Prediction results
```
print('Coefficients: ',l.coef_)
print('Intercept: ',l.intercept_)
print('MAS: ',metrics.mean_absolute_error(y_test,predictions))
print('MSE: ',metrics.mean_squared_error(y_test,predictions))
print('RMSE: ',np.sqrt(metrics.mean_squared_error(y_test,predictions)))
accuracy=l.score(x_test,y_test)
print('AccuracyII: ', accuracy*100, '%')
print('R2: ', r2_score(y_test, predictions))
```

```
print('Train set accuracy: ', r2_score(y_train,l.predict(x_train)), '%')
print('Test set accuracy: ', r2_score(y_test,predictions), '%')
```

```
df2 = pd.DataFrame({'Actual':y_test,'Predicted':predictions})
df2['Eror']=df2['Actual']-df2['Predicted']
df2
```

## Scatter Plots

```
sns.regplot(x=y_test, y=predictions)
```

```
df2=pd.DataFrame({'Actual':y_test, 'Predicted':predictions})

df2.plot(kind='bar', figsize=(60,10))
plt.grid(which='major',linestyle='-',linewidth='0.5',color='green')
plt.grid(which='major',linestyle=':',linewidth='0.5',color='red')
plt.show
```

## New Prediction

```
new_observation=[[30,5]]
l.predict(new_observation)
```
