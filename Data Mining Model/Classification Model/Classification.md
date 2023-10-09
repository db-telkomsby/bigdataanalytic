# Modul 3
# Klasifikasi (Decision Tree)

# Tujuan : 

1. Mahasiswa dapat menyimpulkan konsep Klasifikasi
2. Mahasiswa dapat menyimpulkan konsep Decision Tree
3. Mahasiswa dapat mengimplementasikan Decision Tree
4. Mahasiswa dapat mengimplementasikan model Klasifikasi menggunakan Python 

# Dasar Teori :

Klasifikasi secara singkat sebuah proses menemukan definisi kesamaan karakteristik dalam suatu kelompok atau kelas (class).
Kelas, merupakan variabel tak bebas yang merupakan label dari hasil klasifikasi. Sebagai contoh adalah kelas loyalitas pelanggan, kelas badai atau gempa bumi, dan lain-lain.
Prediktor, merupakan variabel bebas suatu model berdasarkan dari karakteristik atribut data yang diklasifikasi, misalnya merokok, minum-minuman alkohol, tekanan darah, status perkawinan, dan sebagainya.

Set data pelatihan, merupakan sekumpulan data lengkap yang berisi kelas dan prediktor untuk dilatih agar model dapat mengelompokan ke dalam kelas yang tepat. Contohnya adalah grup pasien pelanggan di suatu supermarket dan sebagainya
Set data uji, berisi data-data baru yang akan dikelompokan oleh model guna mengetahui akurasi dari model yang telah dibuat.

Algoritma klasifikasi yang sudah umum  digunakan antara lain :

    * Decision tree.
    * Naives Bayes
    * Support Vector Machine
    * k-Nearest Neighbor

Decision Tree merupakan salah satu cara data processing dalam memprediksi masa depan dengan cara membangun klasifikasi atau regresi model dalam bentuk struktur pohon. Hal tersebut dilakukan dengan cara memecah terus ke dalam himpunan bagian yang lebih kecil lalu pada saat itu juga sebuah pohon keputusan secara bertahap dikembangkan. Hasil akhir dari proses tersebut adalah pohon dengan node keputusan dan node daun. Sebuah node keputusan (misalnya, Cuaca/ Outlook) memiliki dua atau lebih cabang (misalnya, Panas, Berawan dan Hujan).

Decision Tree juga berguna untuk dieksplorasi data, menemukan hubungan antara sejumlah calon variabel input dengan sebuah variabel target. Pohon keputusan eksplorasi data dan pemodelan yang salah langkah pertama yang sangat baik dalam proses pemodelan yang digunakan sebagai model akhir untuk beberapa teknik lainnya.
Kelebihan lain dari metode ini adalah mampu mengeliminasi perhitungan atau data-data yang tidak diperlukan. Karena sampel yang ada biasanya hanya diuji berdasarkan kriteria atau kelas tertentu. Meski memiliki banyak kelebihan, namun bukan berarti ini tidak memiliki kekurangan. Pohon keputusan ini mungkin tumpang tindih, terutama jika kelas dan kriteria yang digunakan sangat sering dapat meningkatkan waktu pengambilan keputusan sesuai dengan kapasitas memori yang diperlukan.

Root node (akar): tujuan akhir atau keputusan besar yang ingin diambil.
Branches (ranting): berbagai pilihan tindakan.
Leaf node (daun): kemungkinan hasil atas setiap tindakan.
Entropi adalah nilai informasi yang menyatakan ukuran ketidakpastian (impurity) dari atribut dari suatu kumpulan objek data dalam satuan bit.

Information Gain adalah ukuran efektivitas suatu atribut dalam mengklasifikasikan data.

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

*Set Feature and Target

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

## Decision Tree

A decision tree is a flowchart-like tree structure where an internal node represents feature(or attribute), the branch represents a decision rule, and each leaf node represents the outcome. The topmost node in a decision tree is known as the root node. It learns to partition on the basis of the attribute value. It partitions the tree in recursively manner call recursive partitioning. This flowchart-like structure helps you in decision making.

*Modeling Decision Tree*

```
# Import Module
from sklearn import tree

# Modeling Decision Tree
dtc = tree.DecisionTreeClassifier(min_impurity_decrease=0.01)
dtc.fit(X_train, y_train)

# Predict to Test Data
y_pred_dtc = dtc.predict(X_test)
```



```
# Visualize Tree

from six import StringIO
from IPython.display import Image
from sklearn.tree import export_graphviz
import pydotplus

dot_data = StringIO()
export_graphviz(dtc, out_file=dot_data,
                filled=True, rounded=True,
                special_characters=True,
                class_names=['notchurn', 'churn'],
                feature_names=['SeniorCitizen',	'Partner',	'Dependents', 'tenure',	'PhoneService', 'OnlineSecurity',	'OnlineBackup',	'DeviceProtection',
                               'TechSupport',	'StreamingTV',	'StreamingMovies',	'PaperlessBilling',	'MonthlyCharges', 'gender_Female',
                               'gender_Male',	'InternetService_DSL', 'InternetService_Fiber optic', 'InternetService_No',	'Contract_Month-to-month',
                               'Contract_One year',	'Contract_Two year',	'PaymentMethod_Bank transfer (automatic)', 'PaymentMethod_Credit card (automatic)',
                               'PaymentMethod_Electronic check',	'PaymentMethod_Mailed check'])
graph = pydotplus.graph_from_dot_data(dot_data.getvalue())
Image(graph.create_png())
```

*Model Evaluation*
```
# Import Module
from sklearn import metrics

# Show the Confussion Matrix
cm_dtc = metrics.confusion_matrix(y_test, y_pred_dtc)
cm_dtc
```

```
# Show the Accuracy, Precision, Recall
acc_dtc = metrics.accuracy_score(y_test, y_pred_dtc)
prec_dtc = metrics.precision_score(y_test, y_pred_dtc)
rec_dtc = metrics.recall_score(y_test, y_pred_dtc)
f1_dtc = metrics.f1_score(y_test, y_pred_dtc)
kappa_dtc = metrics.cohen_kappa_score(y_test, y_pred_dtc)

print("Accuracy:", acc_dtc)
print("Precision:", prec_dtc)
print("Recall:", rec_dtc)
print("F1 Score:", f1_dtc)
print("Cohens Kappa Score:", kappa_dtc)
```

```
# Import Visualization Package
import matplotlib.pyplot as plt
import warnings
warnings.filterwarnings('ignore')

# Set Size and Style
plt.rcParams['figure.figsize'] = (10, 10)
plt.style.use('ggplot')

# Visualize ROC Curve
y_pred_dtc_proba = dtc.predict_proba(X_test)[::,1]
fprdtc, tprdtc, _ = metrics.roc_curve(y_test,  y_pred_dtc_proba)
aucdtc = metrics.roc_auc_score(y_test, y_pred_dtc_proba)
plt.plot(fprdtc,tprdtc,label="Decision Tree, auc="+str(aucdtc))
plt.title('ROC Curve - Decision Tree')
plt.xlabel('false positive rate')
plt.ylabel('true positive rate')
plt.legend(loc=4)
plt.show()
```

