### Penjelasan 
Project ini merupakan final project tugas akhir Bootcampt Data Science di Rakain Academy
### TOPIK : Prediksi Terjadinya Transaksi Pembelian Oleh Pengunjung Pada Sebuah Toko Belanja Online
Topik ini dilakukan terhadap sebuah dataset yang diperoleh dari www.kaggle.com yang bernama "Online Shoppers Purchasing Intention". Dari dataset tersebut ingin diketahui apakah pengunjung sebuah toko online diprediksi melakukan pembelian atau tidak. Penjelasan dataset dan kolom target dijelaskan pada bagian berikutnya.
### Dataset "Online Shoppers Purchasing Intention"
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
### Latar Belakang (Background)
#### Masalah
Pengunjung banyak namun transaksi pembelian sangat sedikit
#### Goal
Meningkatkan Pendapatan/Omset
#### Objectivitas
- Memprediksi pengunjung apakah melakukan transaksi atau tidak
- Membuat rekomendasi sesuai prediksi
#### Business Metric
Convertion Rate (meningkatkan rate transaksi)
#### Solusi
Membuat model Machine Learning terbaik untuk memprediksi terjadinya pembelian atau tidak.
Model Machine Leraning yang digunkan adalah Supervised - Clasification.
### Flowchart atau Langkah-Langkah Membuat Model
#### 1. Exploration Data Analys (EDA)
#### 2. Data Preprocessing
### 3. Pengujian Model Prediksi dan Evaluasi Model
- Log Regression
- Knn
- Decision Tree
- Random Forest
#### 4. Menentukan model prediksi terbaik
#### 5. Insight bisnis
### EDA
#### Deskripsi Statistika
![Deskripsi Tipe Numeric](https://github.com/dodystat/myfinalproject_supervisedml/blob/main/image/deskripsinum.png)
![Deskripsi Tipe Kategori](https://github.com/dodystat/myfinalproject_supervisedml/blob/main/image/deskripsicat.png)
#### Univariate Analysis
![Cek Outlier](https://github.com/dodystat/myfinalproject_supervisedml/blob/main/image/unioutlier.png)
![Cek Distribusi](https://github.com/dodystat/myfinalproject_supervisedml/blob/main/image/unidistribusi.png)
![Univariate Tipe Kategori](https://github.com/dodystat/myfinalproject_supervisedml/blob/main/image/unikategori.png)
![Univariate Kolom Target](https://github.com/dodystat/myfinalproject_supervisedml/blob/main/image/unirevenue.png)
#### Bivariate Analysis
![Kolom tipe kategori vs kolom target (Revenue)](https://github.com/dodystat/myfinalproject_supervisedml/blob/main/image/bivariate.png)
#### Multivariate Analysis
![Multivariate Analysis](https://github.com/dodystat/myfinalproject_supervisedml/blob/main/image/multivariate.png)

- Semua kolom numeric mempunyai Distribusi Positive Skewed atau Miring Kanan. Kolom-kolom tersebut akan dilakukan Logaritma Transformation agar berdistribusi normal.
- Semua kolom numeric mempunyai mempunyai outlier. Kolom atau baris yang mengandung outlier akan di hapus atau di drop. 
- Terdapat korelasi antar feature yang memiliki korelasi lebih dari 0,7 yaitu: ProductRelated vs ProductRelated_Duration, BounceRates vs Exitrates. Salah satu kolom tersebut akan dihapus yaitu yang mempunyai nilai korelasi dengan revenue yang lebih kecil.
- PageValues, ExitRates, BounceRates, ProductRelated_Duration, ProductRelated memberikan pengaruh paling besar terhadap kolom target (kolom Revenue).
- Terjadi imbalance di kolom target yaitu kolom Revenue dimana nilai False jauh lebih banyak dibanding True.
- Nilai pagevalues yang tinggi mempunyai peluang untuk melakukan transaksi.
### Data Preprocessing
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
Hasil preprocessing:
- Terdapat 6 kolom feature yang di drop karena redundant dan korelasi dengan target mendekati 0 sehingga feature tersebut tidak berpengaruh
- Data tidak mempunyai missing value sehingga tidak perlu dilakukan penanganan
- Terdapat data duplikat dimana data duplikat tersebut dihapus menggunakan metode keep=‘first’ (baris pertama yang dipertahankan)
- Terdapat data outlier. Data outlier di hapus menggunakan metode IQR
- Tipe kolom weekend di rubah dari float menjadi integer
- Menghapus baris yang mempunyai nilai Other pada kolom VisitorType
- Telah dilakukan pemisahan antara kolom feature dan target
- Feature transformation menggunakan StandardScaler
- Kolom feature tipe kategori dilakukan encoding menjadi tipe numerik
- Selanjutnya lakukan Train Test Split menggunakan library Train Test Split untuk memisahkan data train dan data test
- Melakukan handling class imbalance menggunakan over sampling dengan metode SMOTE
### Pengujian Model Machine Learning dan Evaluasi Model
Model yang digunakan adalah Supervised Machine Learning - Classification dikarenakan kolom target yang akan diprediksi mempunyai tipe non numerik. Adapun beberapa model classifikasi yang digunakan untuk algoritma yaitu:
- Log Regression
- Knn
- Decision Tree
- Random Forest
Setiap model machine learning diatas dibuat algoritma model, evaluasi, melakukan tuning hyperparameter dan learning curve untuk memperoleh nilai parameter dengan evaluasi terbaik setiap modelnya. Keempat parameter tersebut dibandingkan nilai evaluasinya untuk diperoleh model yang terbaik untuk prediksi. Setelah dilakukan pengujian diperoleh perbandingan keempat model sebagai berikut:
![perbandingan Model](https://github.com/dodystat/myfinalproject_supervisedml/blob/main/image/model.png)
### Model Prediksi Terbaik
Berdasarkan perbandingan keempat model diatas diperoleh Model Machine Learning Terbaik untuk prediksi adalah model Random Forest dengan parameter n_estimators=25, max_depth=4, criterion='gini dikarenakan model ini fit dan mempunyai nilai evaluasi yang paling besar. Berikut hasil algoritmanya:
![Model Random Forest](https://github.com/dodystat/myfinalproject_supervisedml/blob/main/image/rf.png)
![Model Random Forest](https://github.com/dodystat/myfinalproject_supervisedml/blob/main/image/rf2.png)

Berdasarkan model random forest diperoleh feature importance atau feature yang berpengaruh terhadap target beserta korelasinya yaitu:
![Feature Importance](https://github.com/dodystat/myfinalproject_supervisedml/blob/main/image/featureimportance.png)
![Feature Importance](https://github.com/dodystat/myfinalproject_supervisedml/blob/main/image/shape1.png)
![Feature Importance](https://github.com/dodystat/myfinalproject_supervisedml/blob/main/image/shape2.png)

### Insight
- Model Random Forest dengan parameter n_estimators=25, max_depth=4, criterion='gini adalah model terbaik untuk prediksi dalam kasus ini
- PageValues, Month, ExitRates, VisitorType, Administrative, ProductRelated, Administrative_duration, weekend, Informational_duration dan SpecialDay memberikan kontribusi terhadap hasil prediksi
- 6 fitur yang paling berkontribusi yaitu PageValues, Month, ExitRates, VisitorType, Administrative, ProductRelated. 
- 	Fitur PageValues, Month, Administrative dan ProductRelated mempunyai pengaruh positif terhadap terjadinya transaksi.
- Fitur ExitRates, VisitorType mempunyai pengaruh negatif terhadap terjadinya transaksi.
- PageValues memiliki pengaruh paling besar terhadap kecendurangan pengunjung melakukan transaksi serta memberikan pengaruh positif dimana semakin tinggi nilai pagevalue maka pengunjung cenderung membeli dan sebaliknya

### Keterangan
Algoritma lengkap mengenai keseluruhan proses atau langkah-langkah dari awal sampai akhir untuk memperoleh model MAchine Learning dapat dilihat pada file ipynb.

