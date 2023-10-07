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
  a. Decision tree.
  b. Naives Bayes
  c. Support Vector Machine
  d. k-Nearest Neighbor

Decision Tree merupakan salah satu cara data processing dalam memprediksi masa depan dengan cara membangun klasifikasi atau regresi model dalam bentuk struktur pohon. Hal tersebut dilakukan dengan cara memecah terus ke dalam himpunan bagian yang lebih kecil lalu pada saat itu juga sebuah pohon keputusan secara bertahap dikembangkan. Hasil akhir dari proses tersebut adalah pohon dengan node keputusan dan node daun. Sebuah node keputusan (misalnya, Cuaca/ Outlook) memiliki dua atau lebih cabang (misalnya, Panas, Berawan dan Hujan).

Decision Tree juga berguna untuk dieksplorasi data, menemukan hubungan antara sejumlah calon variabel input dengan sebuah variabel target. Pohon keputusan eksplorasi data dan pemodelan yang salah langkah pertama yang sangat baik dalam proses pemodelan yang digunakan sebagai model akhir untuk beberapa teknik lainnya.
Kelebihan lain dari metode ini adalah mampu mengeliminasi perhitungan atau data-data yang tidak diperlukan. Karena sampel yang ada biasanya hanya diuji berdasarkan kriteria atau kelas tertentu. Meski memiliki banyak kelebihan, namun bukan berarti ini tidak memiliki kekurangan. Pohon keputusan ini mungkin tumpang tindih, terutama jika kelas dan kriteria yang digunakan sangat sering dapat meningkatkan waktu pengambilan keputusan sesuai dengan kapasitas memori yang diperlukan.

Root node (akar): tujuan akhir atau keputusan besar yang ingin diambil.
Branches (ranting): berbagai pilihan tindakan.
Leaf node (daun): kemungkinan hasil atas setiap tindakan.
Entropi adalah nilai informasi yang menyatakan ukuran ketidakpastian (impurity) dari atribut dari suatu kumpulan objek data dalam satuan bit.

Information Gain adalah ukuran efektivitas suatu atribut dalam mengklasifikasikan data.


