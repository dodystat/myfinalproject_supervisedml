## TOPIK : Prediksi Terjadinya Transaksi Pembelian Oleh Pengunjung Pada Sebuah Toko Belanja Online
Topik ini dilakukan terhadap sebuah dataset yang diperoleh dari www.kaggle.com yang bernama "Online Shoppers Purchasing Intention". Dari dataset tersebut ingin diketahui apakah pengunjung sebuah toko online diprediksi melakukan pembelian atau tidak. Penjelasan dataset dan kolom target dijelaskan pada bagian berikutnya.
## Dataset "Online Shoppers Purchasing Intention"
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
## Latar Belakang (Background)
### Masalah
Pengunjung banyak namun transaksi pembelian sangat sedikit
### Goal
Meningkatkan Pendapatan/Omset
### Objectivitas
- Memprediksi pengunjung apakah melakukan transaksi atau tidak
- Membuat rekomendasi sesuai prediksi
### Business Metric
Convertion Rate (meningkatkan rate transaksi)
### Solusi
Membuat model Machine Learning terbaik untuk memprediksi terjadinya pembelian atau tidak.
Model Machine Leraning yang digunkan adalah Supervised - Clasification.
## Flowchart atau Langkah-Langkah Membuat Model
### 1. Exploration Data Analys (EDA)
- Deskripsi Statistik
- Univariate
- Bivariate
- Multivariate
### 3. Data Preprocessing
### 4. Pengujian Model Prediksi dan Evaluasi Model
- Log Regression
- Knn
- Decision Tree
- Random Foret
### 5. Menentukan model prediksi terbaik
### 6. Insight bisnis
## EDA
### Deskripsi Statistika
![Deskripsi Tipe Numeric](https://github.com/dodystat/myfinalproject_supervisedml/blob/main/image/deskripsinum.png)
![Deskripsi Tipe Kategori](https://github.com/dodystat/myfinalproject_supervisedml/blob/main/image/deskripsicat.png)
### Univariate Analysis
![Cek Outlier](https://github.com/dodystat/myfinalproject_supervisedml/blob/main/image/unioutlier.png)
![Cek Distribusi](https://github.com/dodystat/myfinalproject_supervisedml/blob/main/image/unidistribusi.png)
![Univariate Tipe Kategori](https://github.com/dodystat/myfinalproject_supervisedml/blob/main/image/unikategori.png)
![Univariate Kolom Target](https://github.com/dodystat/myfinalproject_supervisedml/blob/main/image/unirevenue.png)
### Bivariate Analysis
![Kolom tipe kategori vs kolom target (Revenue)](https://github.com/dodystat/myfinalproject_supervisedml/blob/main/image/bivariate.png)
### Multivariate Analysis
![Multivariate Analysis](https://github.com/dodystat/myfinalproject_supervisedml/blob/main/image/multivariate.png)

- Semua kolom numeric mempunyai Distribusi Positive Skewed atau Miring Kanan. Kolom-kolom tersebut akan dilakukan Logaritma Transformation agar berdistribusi normal.
- Semua kolom numeric mempunyai mempunyai outlier. Kolom atau baris yang mengandung outlier akan di hapus atau di drop. 
- Terdapat korelasi antar feature yang memiliki korelasi lebih dari 0,7 yaitu: ProductRelated vs ProductRelated_Duration, BounceRates vs Exitrates. Salah satu kolom tersebut akan dihapus yaitu yang mempunyai nilai korelasi dengan revenue yang lebih kecil.
- PageValues, ExitRates, BounceRates, ProductRelated_Duration, ProductRelated memberikan pengaruh paling besar terhadap kolom target (kolom Revenue).
- Terjadi imbalance di kolom target yaitu kolom Revenue dimana nilai False jauh lebih banyak dibanding True.
- Nilai pagevalues yang tinggi mempunyai peluang untuk melakukan transaksi.
## Data Preprocessing
Proses yang dilakukan dalam tahap preprocessing ini yaitu:
- Drop kolom tidak relevant
- Handling Missing Value
- Drop Duplicate
- Drop Outlier
- Format tipe data
- Feature Transformation
- Encoding
- Train Test Split
- Handling Class Imbalance
