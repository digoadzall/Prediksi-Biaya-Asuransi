# Laporan Proyek Machine Learning - Muhammad Faizal Pratama

## Domain Proyek

Asuransi kesehatan merupakan sektor penting yang membutuhkan prediksi biaya yang akurat. Banyak faktor yang mempengaruhi besarnya premi asuransi yang harus dibayarkan oleh individu, seperti usia, jenis kelamin, BMI, status merokok, jumlah anak, dan lokasi tempat tinggal. Perusahaan asuransi perlu mengestimasi biaya ini untuk menetapkan premi yang adil, sedangkan individu ingin mengetahui proyeksi biaya yang harus disiapkan.
Menurut penelitian Medical Expenditure Panel Survey (MEPS), faktor usia, obesitas, dan kebiasaan merokok menjadi faktor terbesar yang memengaruhi besarnya biaya perawatan kesehatan di Amerika Serikat.

Referensi:The Medical Expenditure Panel Survey (MEPS) Overview. (Agency for Healthcare Research and Quality - ahrq.gov)

## Business Understanding

Perusahaan asuransi ingin mengetahui model terbaik yang dapat memprediksi biaya asuransi berdasarkan data pelanggan. Prediksi yang akurat dapat membantu menetapkan premi yang adil dan menghindari kerugian.

Bagian laporan ini mencakup:

### Problem Statements

Bagaimana memprediksi biaya asuransi berdasarkan faktor usia, BMI, status merokok, dan variabel lainnya?

### Goals

Menentukan algoritma machine learning terbaik yang dapat memodelkan prediksi biaya asuransi dengan akurasi tinggi.

## Data Understanding
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

Selanjutnya uraikanlah seluruh variabel atau fitur pada data. Sebagai contoh:  

### Variabel-variabel pada Restaurant UCI dataset adalah sebagai berikut:
- accepts : merupakan jenis pembayaran yang diterima pada restoran tertentu.
- cuisine : merupakan jenis masakan yang disajikan pada restoran.
- dst

**Rubrik/Kriteria Tambahan (Opsional)**:
- Melakukan beberapa tahapan yang diperlukan untuk memahami data, contohnya teknik visualisasi data atau exploratory data analysis.

## Data Preparation
Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan proses data preparation yang dilakukan
- Menjelaskan alasan mengapa diperlukan tahapan data preparation tersebut.

## Modeling
Tahapan ini membahas mengenai model machine learning yang digunakan untuk menyelesaikan permasalahan. Anda perlu menjelaskan tahapan dan parameter yang digunakan pada proses pemodelan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan kelebihan dan kekurangan dari setiap algoritma yang digunakan.
- Jika menggunakan satu algoritma pada solution statement, lakukan proses improvement terhadap model dengan hyperparameter tuning. **Jelaskan proses improvement yang dilakukan**.
- Jika menggunakan dua atau lebih algoritma pada solution statement, maka pilih model terbaik sebagai solusi. **Jelaskan mengapa memilih model tersebut sebagai model terbaik**.

## Evaluation
Pada bagian ini anda perlu menyebutkan metrik evaluasi yang digunakan. Lalu anda perlu menjelaskan hasil proyek berdasarkan metrik evaluasi yang digunakan.

Sebagai contoh, Anda memiih kasus klasifikasi dan menggunakan metrik **akurasi, precision, recall, dan F1 score**. Jelaskan mengenai beberapa hal berikut:
- Penjelasan mengenai metrik yang digunakan
- Menjelaskan hasil proyek berdasarkan metrik evaluasi

Ingatlah, metrik evaluasi yang digunakan harus sesuai dengan konteks data, problem statement, dan solusi yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan formula metrik dan bagaimana metrik tersebut bekerja.

**---Ini adalah bagian akhir laporan---**

_Catatan:_
- _Anda dapat menambahkan gambar, kode, atau tabel ke dalam laporan jika diperlukan. Temukan caranya pada contoh dokumen markdown di situs editor [Dillinger](https://dillinger.io/), [Github Guides: Mastering markdown](https://guides.github.com/features/mastering-markdown/), atau sumber lain di internet. Semangat!_
- Jika terdapat penjelasan yang harus menyertakan code snippet, tuliskan dengan sewajarnya. Tidak perlu menuliskan keseluruhan kode project, cukup bagian yang ingin dijelaskan saja.

