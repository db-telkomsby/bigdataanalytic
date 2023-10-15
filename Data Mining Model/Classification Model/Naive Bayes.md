# Modul 4
# Klasifikasi (Naive Bayes)

# Tujuan : 

1. Mahasiswa dapat menyimpulkan 
2. Mahasiswa dapat menyimpulkan 
3. Mahasiswa dapat mengimplementasikan 
4. Mahasiswa dapat mengimplementasikan model Klasifikasi menggunakan Python 

## Table of Contents
1. [Dasar Teori](#dasar-teori)
2. [Classification](#classification)
3. [Import Libraries](#import-libraries)
4. [Import Raw Dataset](#import-raw-dataset)
5. [Data Preprocessing](#data-preprocessing)
6. [Decision Tree](#decision-tree)

   
## Dasar Teori :
**Klasifikasi** secara singkat sebuah proses menemukan definisi kesamaan karakteristik dalam suatu kelompok atau kelas (class).
Kelas, merupakan variabel tak bebas yang merupakan label dari hasil klasifikasi. Sebagai contoh adalah kelas loyalitas pelanggan, kelas badai atau gempa bumi, dan lain-lain.

**Prediktor**, merupakan variabel bebas suatu model berdasarkan dari karakteristik atribut data yang diklasifikasi, misalnya merokok, minum-minuman alkohol, tekanan darah, status perkawinan, dan sebagainya.

**Set data pelatihan**, merupakan sekumpulan data lengkap yang berisi kelas dan prediktor untuk dilatih agar model dapat mengelompokan ke dalam kelas yang tepat. Contohnya adalah grup pasien pelanggan di suatu supermarket dan sebagainya

**Set data uji**, berisi data-data baru yang akan dikelompokan oleh model guna mengetahui akurasi dari model yang telah dibuat.
Algoritma klasifikasi yang sudah umum  digunakan antara lain :
* Decision tree
* **Naives Bayes**
* Support Vector Machine
* k-Nearest Neighbor


**Probability-based learning** merupakan pembelajaran menggunakan teori probabilitas atau suatu kemungkinan yang akan terjadi untuk membuat prediksi atau keputusan. Cara ini digunakan untuk memodelkan ketidakpastian data.

**Teorema Bayes**, teorema ini menyatakan seberapa jauh derajat kepercayaan subjektif seseorang harus berubah secara rasional ketika ada petunjuk atau informasi baru.
Rumus Teorema Bayes
![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Mining%20Model/Classification%20Model/images/Rumus%20Teorema%20Bayes.png?raw=true) 

Contoh sederhana 
Aris yang ngobrol sama orang di cafe. Anggaplah kita adalah Kinan yang lagi bikin asumsi-asumsi tentang sosok yang ngobrol sama Aris. Berapa sih kemungkinan Aris ngobrol sama wanita? Gitu kan ya.

Nah, kita pakai teorema Bayes untuk menentukan berapa peluang Aris ngobrol sama wanita.

Kita tulis asumsi bahwa besar peluang Aris ngobrol sama wanita dari informasi pertama adalah 50%. Angka ini hanya asumsi bahwa populasi wanita di bumi adalah setengah dari populasi.

P(W) = 50% = 0,5
P(P) = 50% = 0,5

Setelah Aris bilang kalau orang yang ngobrol bareng sama dia memakai baju pink, maka kita punya informasi tambahan nih. Peluang orang berbaju pink adalah wanita itu kan besar ya, katakanlah 75%. Sedangkan, peluang pria memakai baju berwarna pink tentu lebih kecil, karena mayoritas pria nggak suka pakai warna pink, katakanlah jumlahnya 30%.

P(BP|W) = 75% = 0,75
P(BP|P) = 30% = 0,3

Nah, sekarang kita mencari tahu, berapakah kemungkinan wanita berbaju pink?
![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Mining%20Model/Classification%20Model/images/P(AB).png?raw=true) 


Dari aturan Bayes di atas, kita bisa substitusi kategorinya sesuai dengan yang akan kita cari.
![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Mining%20Model/Classification%20Model/images/P(WBP).png?raw=true) 

Bingung nggak gimana cara mencari P(BP), karena di asumsi belum diketahui besaran peluangnya? nggak usah bingung, masih ingat tentang materi probabilitas total nggak? Nah, bisa mencarinya menggunakan rumus probabilitas total.

P(BP) = P(BP|W).P(W) + P(BP|P).P(P) = (0,75)(0,5) + (0,3)(0,5) = 0,525

Kita masukkan ke dalam formula aturan Bayes, sehingga:
![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Mining%20Model/Classification%20Model/images/P(WBP)%202.png?raw=true) 

Jadi, dengan asumsi bahwa peluang Aris ngobrol sama wanita adalah 50% (berdasarkan setengah populasi). Tapi, dengan adanya informasi tambahan berupa baju pink, maka keyakinan Kinan bisa bertambah menjadi 71,4%.

**Naïve Bayes** adalah metode pengklasifikasian paling sederhana dari model pengklasifikasian yang ada dengan menggunakan konsep peluang, dimana diasumsikan bahwa setiap atribut contoh (data sampel) bersifat saling lepas satu sama lain berdasarkan atribut kelas.

**Flowchart Naives Bayes:**
![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Mining%20Model/Classification%20Model/images/Flowchart.png?raw=true) 


**Contoh Penerapan:**
Pengklasifikasi kualitas kadar air kolam ikan
Fitur: pH, TDS, suhu air, dsb.
Kelas: kolam layak atau tidak layak
Pengklasifikasi opini positif atau negatif terhadap suatu produk
Fitur: kamus kata yang termasuk positif dan negatif
Kelas: opini positif atau negatif
Pengklasifikasi kepribadian (personality) terhadap karakter seseorang
Fitur: kamus kata yang termasuk sanguinis, plegmatis, melankolis, koleris
Kelas: sanguinis, plegmatis, melankolis, koleris 

Contoh Soal:
1.   Diketahui data orang-orang yang membeli laptop dan tidak sebagai berikut ini:
![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Mining%20Model/Classification%20Model/images/tabel.png?raw=true) 

Kemudian jika ada data lagi yang masuk dengan kriteria: usia <= 30 dan memiliki income “medium”, maka akan diklasifikasikan dengan label apa?

Maka perlu menghitung P(X) dengan X = “usia <=30” dan income ==”medium”

2.   Hitung probabilitas masing-masing kelas. 
C1 → Kelas 1 untuk beli_komputer=”yes” 
C2 → Kelas 1 untuk beli_komputer=”no”
![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Mining%20Model/Classification%20Model/images/gambar1-PCi.png?raw=true) 

3.   Perhitungan P(X|Ci) → Probabilitas karakteristik terhadap suatu label
X 1→ age <=30
![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Mining%20Model/Classification%20Model/images/gambar2_X1.png?raw=true) 
X2→ income==’medium’ 
![alt text](https://github.com/db-telkomsby/bigdataanalytic/blob/main/Data%20Mining%20Model/Classification%20Model/images/gambar3_x2.png?raw=true)

5.   Menghitung PX terhadap masing-masing kelas.
𝑃(𝑋|𝐶1) = 𝑃(𝑋𝑛𝐶1) = 0.22 ∗ 0.44 = 0.09 
𝑃(𝑋|𝐶2) = 𝑃(𝑋𝑛𝐶2) = 0.60 ∗ 0.40 = 0.24

6.   Perhitungan akhir untuk menentukan data X akan dikelompokan ke kelas yang mana:
𝑃1 = 𝑃(𝑋|𝐶1 )𝑃(𝐶1 ) = 0.09 ∗ 0.64 = 0.063 
𝑃2 = 𝑃(𝑋|𝐶2 )𝑃(𝐶2 ) = 0.24 ∗ 0.36 = 0.085 
Karena P2 > P1, maka data x masuk ke dalam Kelas dengan label beli_komputer = “no” 


## Classification

Here we model the classification model from telco customer churn data (https://www.kaggle.com/blastchar/telco-customer-churn). This data is consist of customer profile, customer subscription history, and their churn information.

Each row represents a customer, each column contains customer’s attributes described below:

1.   customerID : Customer ID
2.   gender : Whether the customer is a male or a female
3.   SeniorCitizen : Whether the customer is a senior citizen or not (1, 0)
4.   Partner : Whether the customer has a partner or not (Yes, No)
5.   Dependents : Whether the customer has dependents or not (Yes, No)
6.   tenure : Number of months the customer has stayed with the company
7.   PhoneService : Whether the customer has a phone service or not (Yes, No)
8.   MultipleLines : Whether the customer has multiple lines or not (Yes, No, No phone service)
9.   InternetService : Customer’s internet service provider (DSL, Fiber optic, No)
10.   OnlineSecurity: Whether the customer has online security or not (Yes, No, No internet service)
11.   OnlineBackup: Whether the customer has online backup or not (Yes, No, No internet service)
12.   DeviceProtection: Whether the customer has device protection or not (Yes, No, No internet service)
13.   TechSupport : Whether the customer has tech support or not (Yes, No, No internet service)
14.   StreamingTV : Whether the customer has streaming TV or not (Yes, No, No internet service)
15.   StreamingMovies : Whether the customer has streaming movies or not (Yes, No, No internet service)
16.   Contract : The contract term of the customer (Month-to-month, One year, Two year)
17.   PaperlessBilling : Whether the customer has paperless billing or not (Yes, No)
18.   PaymentMethod : The customer’s payment method (Electronic check, Mailed check, Bank transfer (automatic), Credit card (automatic))
19.   MonthlyCharges : The amount charged to the customer monthly
20.   TotalCharges : The total amount charged to the customer
21.   Churn Whether: the customer churned or not (Yes or No)

We will predict customer behavior to retain customers. You can analyze all relevant customer data and develop focused customer retention programs." [IBM Sample Data Sets]

## Import Libraries

```
# Import Library
import pandas as pd
```

## Import Raw Dataset

```
# Import Data to Google Colab
df_churn = pd.read_csv('https://raw.githubusercontent.com/dianrdn/data/master/customer_churn.csv', sep = ';')
df_churn

# Show 10 first Row
df_churn.head()
```

```
# Prints the Dataset Information
df_churn.info()
```

```
# Prints Descriptive Statistics
df_churn.describe().transpose()
```

## Data Preprocessing

*Handling Missing Values*

```
# Check for Missing Values
df_churn.isnull().sum()
```

```
# Search for Median Value
median = df_churn['TotalCharges'].median()

# Use Median to Replace Missing Values
df_churn['TotalCharges'].fillna(median, inplace=True)

# Check for Missing Values
df_churn.isnull().sum()
```

*Encode Categorical Data*

```
# Import Module
from sklearn.preprocessing import OneHotEncoder

# Encoder
encoder = OneHotEncoder(sparse=False)

# Encode Categorical Data
df_encoded = pd.DataFrame(encoder.fit_transform(df_churn[['gender', 'InternetService', 'Contract', 'PaymentMethod']]))
df_encoded.columns = encoder.get_feature_names_out(['gender', 'InternetService', 'Contract', 'PaymentMethod'])

# Replace Categotical Data with Encoded Data
df_churn.drop(['gender', 'InternetService', 'Contract', 'PaymentMethod'] ,axis=1, inplace=True)
df_encoded= pd.concat([df_churn, df_encoded], axis=1)

# Show Encoded Dataframe
df_encoded
```

*Set Feature and Target*

```
# Select Features
feature = df_encoded.drop(['customerID', 'TotalCharges', 'Churn'], axis=1)
feature
```

```
# Select Target
target = df_encoded['Churn']
target
```

*Set Training and Testing Data*

```
# Set Training and Testing Data (70:30)
from sklearn.model_selection import train_test_split, cross_val_score
X_train, X_test, y_train, y_test  = train_test_split(feature , target, shuffle = True, test_size=0.3, random_state=1)

# Show the Training and Testing Data
print(X_train.shape)
print(X_test.shape)
print(y_train.shape)
print(y_test.shape)
```

```
X_test
```

## Naive Bayes


*Modeling Naive Bayes*

```

```



```
# Visualize Tree




```

*Model Evaluation*
```
```

```
```

```
```
