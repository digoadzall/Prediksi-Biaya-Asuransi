# Laporan Proyek Machine Learning - Muhammad Faizal Pratama

## Domain Proyek

Asuransi kesehatan merupakan sektor penting yang membutuhkan prediksi biaya yang akurat. Banyak faktor yang mempengaruhi besarnya premi asuransi yang harus dibayarkan oleh individu, seperti usia, jenis kelamin, BMI, status merokok, jumlah anak, dan lokasi tempat tinggal. Perusahaan asuransi perlu mengestimasi biaya ini untuk menetapkan premi yang adil, sedangkan individu ingin mengetahui proyeksi biaya yang harus disiapkan.
Menurut penelitian Medical Expenditure Panel Survey (MEPS), faktor usia, obesitas, dan kebiasaan merokok menjadi faktor terbesar yang memengaruhi besarnya biaya perawatan kesehatan di Amerika Serikat.

Referensi:The Medical Expenditure Panel Survey (MEPS) Overview. (Agency for Healthcare Research and Quality - ahrq.gov)

## Business Understanding

Perusahaan asuransi ingin mengetahui model terbaik yang dapat memprediksi biaya asuransi berdasarkan data pelanggan. Prediksi yang akurat dapat membantu menetapkan premi yang adil dan menghindari kerugian.

Bagian laporan ini mencakup:

### Problem Statements
1. Bagaimana memprediksi biaya asuransi berdasarkan faktor usia, BMI, status merokok, dan variabel lainnya?
2. Algoritma apa yang paling baik dalam memodelkan prediksi biaya asuransi?

### Goals
1. Membangun model machine learning yang mampu memprediksi biaya asuransi dengan akurasi yang baik.
2. Membandingkan beberapa model (Linear Regression, Random Forest, dan XGBoost) dan memilih model terbaik berdasarkan metrik evaluasi.

Solution Statements

- Membangun model regresi linier sebagai baseline.
- Melakukan pemodelan menggunakan Random Forest Regressor untuk menangkap pola non-linear.
- Melakukan pemodelan menggunakan XGBoost sebagai advanced model.
- Membandingkan hasil ketiga model berdasarkan MAE, MSE, dan R² Score.

## Data Understanding
Dataset yang digunakan adalah Medical Cost Personal Dataset dari Kaggle, dengan total 1.338 sampel data.

Variabel-variabel dalam dataset:

- age : usia pemegang asuransi
- sex : jenis kelamin (male/female)
- bmi : body mass index
- children : jumlah anak
- smoker : status merokok (yes/no)
- region : wilayah tempat tinggal
- charges : biaya klaim asuransi (target variabel)
- Visualisasi data dilakukan untuk melihat korelasi antar variabel dan distribusi biaya asuransi.
- Selanjutnya uraikanlah seluruh variabel atau fitur pada data. Sebagai contoh:  

## Data Preparation
- Mengecek missing values (tidak ditemukan missing values dalam dataset).
- Melakukan encoding pada variabel kategorikal (sex, smoker, region) menggunakan pd.get_dummies.
- Melakukan feature scaling pada variabel numerik dengan StandardScaler.
- Memisahkan data menjadi data latih (80%) dan data uji (20%).

  Alasan dilakukan data preparation:
- Encoding diperlukan agar model dapat membaca variabel kategorikal.
- Scaling membantu model convergen lebih baik, terutama pada model linear dan tree-based yang sensitif terhadap skala.

## Modeling
Tiga algoritma yang digunakan:
1. Linear Regression
   Kelebihan: Sederhana dan interpretatif.
   Kekurangan: Tidak mampu menangkap pola non-linear.

2. Random Forest Regressor
   Kelebihan: Dapat menangkap pola non-linear, tahan terhadap outlier.
   Kekurangan: Memerlukan tuning parameter agar hasil optimal.

3. XGBoost Regressor
   Kelebihan: Memiliki performa tinggi, dapat mengatasi overfitting dengan regularisasi.
   Kekurangan: Lebih kompleks dan memerlukan waktu komputasi lebih lama.

- Parameter yang digunakan:
  1. Random Forest: default hyperparameters dengan random_state=42
  2. XGBoost: default hyperparameters dengan random_state=42

## Evaluation
| Model              | MAE       | MSE            | R² Score |
|--------------------|-----------|----------------|----------|
| Linear Regression  | 4181.19   | 33,596,915.85  | 0.7836   |
| Random Forest      | 2545.21   | 20,866,223.20  | 0.8656   |
| XGBoost            | 2765.75   | 23,434,704.62  | 0.8491   |

- Model Random Forest menunjukkan performa terbaik dengan R² tertinggi dan kesalahan prediksi paling kecil.
- Model ini dapat digunakan untuk membantu estimasi biaya asuransi bagi perusahaan maupun individu.
- Dapat ditingkatkan dengan menambahkan fitur eksternal seperti riwayat medis dan faktor risiko tambahan.



