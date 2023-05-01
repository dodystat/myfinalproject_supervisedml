# TOPIK : Prediksi Terjadinya Transaksi Pembelian Oleh Pengunjung Pada Sebuah Toko Belanja Online
Topik ini dilakukan terhadap sebuah dataset yang diperoleh dari www.kaggle.com yang bernama "Online Shoppers Purchasing Intention". Dari dataset tersebut ingin diketahui apakah pengunjung sebuah toko online diprediksi melakukan pembelian atau tidak. Penjelasan dataset dan kolom target dijelaskan pada bagian berikutnya.
# Dataset "Online Shoppers Purchasing Intention"
Sumber: www.kaggle.com
Sebuah website toko belanja online menawarkan suatu produk kepada pengunjung. Pengunjung mengakses website tersebut kemudian melakukan berbagai aktivitas seperti mengakses beberapa halaman web, melihat produk, melakukan transaksi atau tidak dan lain sebagainya. Setiap pengunjung yang mengakses toko online tersebut dicatat dalam database setiap aktivitasnya seperti berapa kali mengunjungi suatu halaman tertentu, berapa lama durasinya, apakah melakukan transaksi atau tidak, dan lain sebgaainya. 
Dataset terdiri dari:
- 12.330 baris
- 18 kolom
dimana:
- baris mewakili setiap pengunjung pada sebuah toko online
- kolom mewakili atribut/aktifitas pengunjung
Kolom target (yang akan diprediksi) adalah kolom Revenue yang berisi True dan False dimana:
- True adalah pengunjung yang melakukan transaksi atau pembelian
- False adalah pengunjung yang tidak melakukan transaksi/pembelian
# Latar Belakang (Background)
## Masalah
Pengunjung banyak namun transaksi pembelian sangat sedikit
## Goal
Meningkatkan Pendapatan/Omset
## Objectivitas
- Memprediksi pengunjung apakah melakukan transaksi atau tidak
- Membuat rekomendasi sesuai prediksi
## Business Metric
Convertion Rate (meningkatkan rate transaksi)
## Solusi
Membuat model Machine Learning terbaik untuk memprediksi terjadinya pembelian atau tidak
# Flowchart atau Langkah-Langkah Membuat Model
## 1. Deskripsi Statistik
## 2. Exploration Data Analys (EDA)
- Univariate
- Bivariate
- Multivariate
## 3. Data Preprocessing
- Drop kolom tidak relevant
- Handling Missing Value
- Drop Duplicate
- Drop Outlier
- Format tipe data
- Feature Transformation
- Encoding
- Train Test Split
- Handling Class Imbalance
## 4. Pengujian Model Prediksi dan Evaluasi Model
- Log Regression
- Knn
- Decision Tree
- Random Foret
## 5. Menentukan model prediksi terbaik
## 6. Insight bisnis
# Deskripsi Statistik
![Deskripsi Tipe Numeric](https://github.com/dodystat/myfinalproject_supervisedml/blob/main/image/deskripsinum.png)



