# Predict-Customer-Personality-to-Boost-Marketing-Campaign-by-Using-Machine-Learning

**Tool** : Jupyter Notebook

**Libraries** : Numpy, Pandas , Matplotlib, Seaborn, Sklearn

**Dataset** : <a href="Dataset">Link Dataset</a>


## Problem Statement ##

### Introduction & Goal ###

Sebuah perusahaan dapat berkembang dengan pesat saat mengetahui perilaku customer personality nya, sehingga dapat memberikan layanan serta manfaat lebih baik kepada customers yang berpotensi menjadi loyal customers. Dengan mengolah data historical marketing campaign guna menaikkan performa dan menyasar customers yang tepat agar dapat bertransaksi di platform perusahaan, dari insight data tersebut fokus kita adalah membuat sebuah model prediksi kluster sehingga memudahkan perusahaan dalam membuat keputusan.

### Objective ###

1. Membuat model machine learning untuk mengelompokan pelanggan berdasarkan karakteristik dan perilaku mereka
2. Membuat insight dan rekomendasi bisnis dari hasil pembuatan model machine learning

## Stage 0 - EDA & Data Preparation ##

<img src="Stage 0/dataset info.PNG" />

1. Dataset ini berisikan data marketing campaign dan terdiri dari 2240 baris data dengan jumlah kolom sebanyak 30 ( 27 kolom numerik dan 3 kolom kategorikal ) . 

2. Terdapat satu kolom yaitu income dengan missing value sebanyak 24.

## Feature Engineering ##

Membuat beberapa kolom baru untuk mendapatkan insight lebih dengan fungsi sebagai berikut :

1. Menghitung umur customer.
2. Menghitung lama waktu customer bergabung.
3. Menghitung total anak.
4. Menentukan bahwa customer sudah menjadi orang tua atau tidak.
5. Melakukan segmentasi customer berdasarkan umur.
6. Menghitung total pengeluaran yang di lakukan customer.
7. Menghitung total campaign yang di setujui oleh customer.
8. Menghitung total transaksi yang dilakukan customer.
9. Menghitung Conversion Rate

### Matriks Korelasi Antar Feature

<img src="Stage 0/Correlation Matrix.PNG" />

Dengan adanya korelasi matrik , fitur yang berkolerasi kuat nantinya akan di gunakan sebagai fitur utama untuk membuat model dan mendapatkan insight baru.

Fitur convertion rate memiliki korelasi positif terhadap fitur income, total amount spending dan age, selanjutnya fitur ini digunakan sebagai acuan untuk melakukan analisis.

## Stage 1 - Data Exploration ##

<img src="Stage 0/CVR Rate Analysis Based of Income, Total Amount Spend , and Age.PNG" />

### Insight analisis : 

Berdasarkan visualisasi diatas dapat disimpulkan bahwa semakin besar income yang dimiliki customer, terdapat kecendurungan untuk melakukan transaksi pengeluaran yang lebih banyak.

## Stage 2 - Modeling

Setelah tahap pre-processing selesai, tahap berikutnya adalah melakukan PCA atau Principal Component Analysis, PCA sangat cocok untuk masalah multicolinearity antar fitur. Dalam hal ini elbow method digunakan untuk memilih jumlah cluster yang optimal dengan nilai yang berada pada silhoute score

<img src="Stage 2/Elbow Method with K.PNG" /> <img src="Stage 2/Silhoute.PNG" />

1. Pada proses modeling menggunakan K-Means ini dapatkan hasil dari Elbow Method dan Silhoute Score yaitu nilai K atau nilai cluster.

2. Menurut grafik diatas jumlah cluster adalah sebanyak 4 cluster berdasarkan Elbow Method dan Silhoute Score.

## Stage 3 - Summary 

<img src="Stage 3/Category Customer.PNG" />

Berdasarkan statisik diatas dapat disimpulkan sebagai berikut :

1. Cluster 3 dinyatakan sebagai high spender dan income tertinggi diantara cluster yang lain.
2. Cluster 0 dinyatakan sebagai middle spender dan income tertinggi ke 2 dibandingkan dengan cluster 1 dan 2.
3. Cluster 2 dinyatakan sebagai low spender dan income tertinggi ke 3 dibandingkan dengan cluster 1
4. Cluster 1 dinyatakan sebagai risk of churn customer dan income terendah dari cluster lain.


<img src="Stage 3/Distribution Age and Kids.PNG" />

<img src="Stage 3/Income and Spending Customer.PNG" />

**Insight** : semakin tinggi income maka semakin tinggi juga total spending dari tiap customer 

<img src="Stage 3/Number Visit Web & CVR.PNG" />

**Insight** : Total visit number yang banyak cenderung menentukan sebuah customer untuk melakukan purchase.

### Conclusion 

- Low Spender/Cluster 2 : 
  
  Cluster ini didominasi oleh customer older adults (>= 55 tahun) dan middle adults ( 36 - 55 tahun ) yang dominan memiliki jumlah anak sebanyak 1 orang.
  Cluster ini terpantau mengunjung website lebih dari 5 kali tiap bulannya, cluster ini memiliki penghasilan lebih tinggi di bandingkan cluster 1
  
- Risk of Churn/Cluster 1 :
  
  Cluster ini didominasi oleh customer older adults (>= 55 tahun) dan middle adults ( 36 - 55 tahun ) yang dominan memiliki jumlah anak sebanyak 1 - 2 orang.
  Cluster ini terpantau mengunjung website lebih dari 5 kali tiap bulannya, cluster ini memiliki penghasilan paling rendah di bandingkan cluster lainnya.
  
- Middle Spender/Cluster 0 :
  
  Cluster ini didominasi oleh customer older adults (>= 55 tahun) dan middle adults ( 36 - 55 tahun ) yang dominan tidak memiliki anak .
  Cluster ini terpantau rata rata mengunjung website kurang dari 3 kali tiap bulannya, cluster ini  memiliki penghasilan paling tinggi kedua setelah cluster 3.
  
- High Spender/Cluster 3 :

  Cluster ini didominasi oleh customer older adults (>= 55 tahun) dan middle adults ( 36 - 55 tahun ) yang dominan tidak memiliki anak .
  Cluster ini terpantau rata rata mengunjung website 3 kali tiap bulannya, cluster ini  memiliki penghasilan paling tinggi  diantara cluster lainnya.






























