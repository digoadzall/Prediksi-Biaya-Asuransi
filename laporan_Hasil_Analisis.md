# Laporan Proyek Machine Learning - Muhammad Faizal Pratama

## Domain Proyek

Asuransi kesehatan merupakan sektor penting yang membutuhkan prediksi biaya yang akurat. Banyak faktor yang memengaruhi besarnya premi asuransi yang harus dibayarkan oleh individu, seperti usia, jenis kelamin, BMI, status merokok, jumlah anak, dan lokasi tempat tinggal.

Dengan menggunakan model machine learning, perusahaan asuransi dapat memproses data historis dan mempelajari pola hubungan antara faktor-faktor tersebut dengan biaya asuransi. Hasil dari model ini akan membantu perusahaan menentukan premi asuransi yang lebih adil dan akurat, sekaligus membantu individu memperkirakan biaya yang akan mereka keluarkan.

Model machine learning yang dibangun dapat digunakan untuk mengotomatisasi proses prediksi, mempercepat pengambilan keputusan, serta mengurangi risiko kesalahan perhitungan yang selama ini mungkin terjadi dengan metode manual.

Referensi: The Medical Expenditure Panel Survey (MEPS) Overview. (Agency for Healthcare Research and Quality - ahrq.gov)

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
Dataset yang digunakan adalah **Medical Cost Personal Dataset** dari **Kaggle**, dengan total **1.338 baris dan 7 kolom**.  
**Sumber data:** [Medical Cost Personal Dataset - Kaggle](https://www.kaggle.com/datasets/mirichoi0218/insurance)  

Variabel dalam dataset:
1. **age** : Usia pemegang asuransi  
2. **sex** : Jenis kelamin (male/female)  
3. **bmi** : Body mass index (BMI)  
4. **children** : Jumlah anak  
5. **smoker** : Status merokok (yes/no)  
6. **region** : Wilayah tempat tinggal  
7. **charges** : Biaya klaim asuransi (target variabel)  

Kondisi Data:
- **Jumlah data:** 1.338 baris dan 7 kolom  
- **Missing values:** Tidak ditemukan missing values dalam dataset.  
- **Duplikat data:** Tidak ditemukan data duplikat.  
- **Outlier:**  
  - Ditemukan beberapa **outlier pada variabel `charges`** (biaya asuransi).  
  - Outlier terutama berasal dari **individu dengan BMI tinggi dan perokok**, yang cenderung memiliki biaya asuransi jauh lebih tinggi.  

Insight Awal dari Visualisasi:
- **Smoker dan BMI tinggi memiliki pengaruh besar** terhadap biaya asuransi.  
- **Usia memiliki korelasi positif dengan `charges`**, artinya semakin tua seseorang, semakin tinggi biaya asuransi.  
- **Variabel `region` tidak menunjukkan pengaruh signifikan** terhadap biaya asuransi.  

Hasil ini menunjukkan bahwa faktor risiko kesehatan seperti **status perokok dan obesitas** berkontribusi besar terhadap biaya asuransi yang harus dibayarkan.
  
## Data Preparation
- Melakukan encoding pada variabel kategorikal (sex, smoker, region) menggunakan pd.get_dummies.
- Melakukan feature scaling pada variabel numerik dengan StandardScaler.
- Memisahkan data menjadi data latih (80%) dan data uji (20%).

  Alasan dilakukan data preparation:
- Encoding diperlukan agar model dapat membaca variabel kategorikal.
- Scaling membantu model convergen lebih baik, terutama pada model linear dan tree-based yang sensitif terhadap skala.

## Modeling
Dalam proyek ini, digunakan tiga algoritma machine learning untuk memodelkan prediksi biaya asuransi, yaitu Linear Regression, Random Forest Regressor, dan XGBoost Regressor.

1. Linear Regression
Linear Regression bekerja dengan mencari garis lurus terbaik yang memetakan hubungan antara variabel input (fitur) dan output (target). Model ini menghitung koefisien pada setiap fitur sehingga persamaan linear dapat memprediksi target. Model akan meminimalkan selisih (error) antara nilai prediksi dan nilai aktual dengan metode Ordinary Least Squares (OLS).
- Model ini cocok jika hubungan antar variabel bersifat linear.

2. Random Forest Regressor
Random Forest adalah algoritma ensemble yang membangun banyak decision tree dari subset data yang diambil secara acak (bootstrapping), lalu hasil dari semua pohon digabungkan (rata-rata) untuk memberikan prediksi akhir.
- Model ini dapat menangkap hubungan non-linear, mengurangi overfitting dibandingkan satu decision tree, dan bekerja baik pada data yang kompleks.

3. XGBoost Regressor
XGBoost (Extreme Gradient Boosting) adalah algoritma boosting yang bekerja dengan membuat model secara bertahap (sekuensial). Setiap model baru berusaha memperbaiki kesalahan model sebelumnya dengan memfokuskan pada residual errors (error yang belum bisa diprediksi dengan baik).
- Model ini menggunakan teknik regularization dan pruning untuk menghindari overfitting, serta dikenal cepat dan akurat.

Parameter
Random Forest: digunakan dengan default hyperparameters, random_state=42
XGBoost: digunakan dengan default hyperparameters, random_state=42

## Evaluasi

Pada bagian ini, kita mengevaluasi performa model menggunakan tiga metrik utama:

1. **Mean Absolute Error (MAE)**  
   - Mengukur rata-rata selisih absolut antara nilai aktual dan prediksi.  
   - Nilai lebih kecil menunjukkan model yang lebih akurat.  

2. **Mean Squared Error (MSE)**  
   - Menghitung rata-rata selisih kuadrat antara nilai aktual dan prediksi.  
   - Lebih sensitif terhadap outlier karena selisih dikuadratkan.  

3. **R² Score (Koefisien Determinasi)**  
   - Mengukur seberapa baik model menjelaskan variasi data.  
   - Nilai mendekati 1 berarti model memiliki performa yang baik.  

### Hasil Evaluasi Model

| Model              | MAE       | MSE            | R² Score |
|--------------------|-----------|----------------|----------|
| Linear Regression  | 4181.19   | 33,596,915.85  | 0.7836   |
| Random Forest      | 2545.21   | 20,866,223.20  | 0.8656   |
| XGBoost            | 2765.75   | 23,434,704.62  | 0.8491   |

### Analisis Hasil

- **Random Forest** memiliki **R² Score tertinggi (0.8656)** serta **MAE dan MSE terendah**, sehingga menjadi model terbaik dalam memprediksi biaya asuransi.  
- **Linear Regression** menunjukkan performa paling rendah karena model ini hanya menangkap hubungan linear antara fitur dan target.  
- **XGBoost** juga memberikan hasil yang baik, tetapi sedikit lebih rendah dibandingkan Random Forest. Dengan tuning lebih lanjut, performanya bisa meningkat.  

Dari hasil ini, **Random Forest** direkomendasikan sebagai model utama untuk prediksi biaya asuransi. Model ini dapat dikembangkan lebih lanjut dengan menambahkan fitur tambahan seperti riwayat medis dan faktor risiko lainnya.  
