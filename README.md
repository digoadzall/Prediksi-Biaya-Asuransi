Laporan Proyek Machine Learning - [Nama Anda]

Domain Proyek

Asuransi kesehatan merupakan sektor penting yang membutuhkan prediksi biaya yang akurat. Banyak faktor yang mempengaruhi besarnya premi asuransi yang harus dibayarkan oleh individu, seperti usia, jenis kelamin, BMI, status merokok, jumlah anak, dan lokasi tempat tinggal. Perusahaan asuransi perlu mengestimasi biaya ini untuk menetapkan premi yang adil, sedangkan individu ingin mengetahui proyeksi biaya yang harus disiapkan.

Menurut penelitian Medical Expenditure Panel Survey (MEPS), faktor usia, obesitas, dan kebiasaan merokok menjadi faktor terbesar yang memengaruhi besarnya biaya perawatan kesehatan di Amerika Serikat.

Referensi:

The Medical Expenditure Panel Survey (MEPS) Overview. (Agency for Healthcare Research and Quality - ahrq.gov)

Business Understanding

Problem Statements

Bagaimana memprediksi biaya asuransi berdasarkan faktor usia, BMI, status merokok, dan variabel lainnya?

Algoritma apa yang paling baik dalam memodelkan prediksi biaya asuransi?

Goals

Membangun model machine learning yang mampu memprediksi biaya asuransi dengan akurasi yang baik.

Membandingkan beberapa model (Linear Regression, Random Forest, dan XGBoost) dan memilih model terbaik berdasarkan metrik evaluasi.

Solution Statements

Membangun model regresi linier sebagai baseline.

Melakukan pemodelan menggunakan Random Forest Regressor untuk menangkap pola non-linear.

Melakukan pemodelan menggunakan XGBoost sebagai advanced model.

Membandingkan hasil ketiga model berdasarkan MAE, MSE, dan R² Score.

Data Understanding

Dataset yang digunakan adalah Medical Cost Personal Dataset dari Kaggle, dengan total 1.338 sampel data.

Variabel-variabel dalam dataset:

age : usia pemegang asuransi

sex : jenis kelamin (male/female)

bmi : body mass index

children : jumlah anak

smoker : status merokok (yes/no)

region : wilayah tempat tinggal

charges : biaya klaim asuransi (target variabel)

Visualisasi data dilakukan untuk melihat korelasi antar variabel dan distribusi biaya asuransi.

Data Preparation

Mengecek missing values (tidak ditemukan missing values dalam dataset).

Melakukan encoding pada variabel kategorikal (sex, smoker, region) menggunakan pd.get_dummies.

Melakukan feature scaling pada variabel numerik dengan StandardScaler.

Memisahkan data menjadi data latih (80%) dan data uji (20%).

Alasan dilakukan data preparation:

Encoding diperlukan agar model dapat membaca variabel kategorikal.

Scaling membantu model convergen lebih baik, terutama pada model linear dan tree-based yang sensitif terhadap skala.

Modeling

Tiga algoritma yang digunakan:

Linear Regression

Kelebihan: Sederhana dan interpretatif.

Kekurangan: Tidak mampu menangkap pola non-linear.

Random Forest Regressor

Kelebihan: Dapat menangkap pola non-linear, tahan terhadap outlier.

Kekurangan: Memerlukan tuning parameter agar hasil optimal.

XGBoost Regressor

Kelebihan: Memiliki performa tinggi, dapat mengatasi overfitting dengan regularisasi.

Kekurangan: Lebih kompleks dan memerlukan waktu komputasi lebih lama.

Parameter yang digunakan:

Random Forest: default hyperparameters dengan random_state=42

XGBoost: default hyperparameters dengan random_state=42

Evaluation

Metrik yang digunakan:

MAE (Mean Absolute Error): rata-rata kesalahan absolut.

MSE (Mean Squared Error): rata-rata kuadrat dari kesalahan prediksi.

R² Score: seberapa baik model menjelaskan variasi dalam data.

Hasil evaluasi:

Model

MAE

MSE

R² Score

Linear Regression

(isi nilai)

(isi nilai)

(isi nilai)

Random Forest

(isi nilai)

(isi nilai)

(isi nilai)

XGBoost

(isi nilai)

(isi nilai)

(isi nilai)

Berdasarkan hasil evaluasi, model XGBoost dipilih sebagai model terbaik karena memberikan hasil R² Score tertinggi dan kesalahan prediksi paling kecil.

Kesimpulan

Model XGBoost dapat digunakan untuk memprediksi biaya asuransi secara lebih akurat dibanding model lain.

Model ini dapat menjadi alat bantu perusahaan asuransi dalam mengestimasi premi dengan lebih objektif.

Ke depannya, model dapat ditingkatkan dengan menambahkan variabel tambahan seperti riwayat kesehatan, aktivitas fisik, dan data genetik untuk akurasi yang lebih tinggi.
