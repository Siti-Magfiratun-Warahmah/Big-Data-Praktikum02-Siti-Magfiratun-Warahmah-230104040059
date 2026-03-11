# PRAKTIKUM 3 – Batch Data Analytics & Visualization Layer

**Proyek:** BIGDATA-SPARK-230104040059

Program ini dibuat untuk memenuhi instruksi **Praktikum 3 mata kuliah Big Data Technology**. Praktikum ini berfokus pada implementasi **Analytics Layer dan Visualization Layer** menggunakan **Apache Spark (PySpark)** dan **Power BI** untuk menghasilkan metrik bisnis dari dataset transaksi e-commerce.

---

# 👩‍🎓 Identitas Mahasiswa

Nama : **Siti Magfiratun Warahmah**
NIM : **230104040059**

---

# 🚀 Deskripsi Program

Program ini merupakan implementasi **batch data analytics menggunakan Apache Spark dengan PySpark**.

Pipeline yang dibuat bertujuan untuk menganalisis dataset transaksi e-commerce yang telah dibersihkan pada praktikum sebelumnya dan menghasilkan beberapa **Key Performance Indicator (KPI)** yang dapat digunakan dalam analisis bisnis.

Proses yang dilakukan dalam pipeline ini meliputi:

✔ Membaca dataset clean data
✔ Melakukan agregasi data menggunakan PySpark
✔ Menghitung metrik bisnis dari transaksi e-commerce
✔ Menyimpan hasil analisis ke dalam serving layer
✔ Menampilkan hasil analisis melalui dashboard Power BI

Dataset yang diproses berisi informasi produk, kategori produk, jumlah transaksi, serta nilai penjualan.

---

# 🛠️ Teknologi yang Digunakan

* Python 3.12
* Apache Spark / PySpark
* Visual Studio Code
* WSL Ubuntu
* Power BI Desktop

---

# 📊 Dataset

Dataset yang digunakan merupakan dataset transaksi e-commerce yang telah melalui proses pembersihan data pada praktikum sebelumnya.

Lokasi dataset:

```
data/clean/parquet/
```

Dataset ini digunakan untuk menghitung beberapa metrik bisnis seperti total revenue, produk terlaris, dan pendapatan berdasarkan kategori produk.

---

# ⚙️ Cara Kerja Program

Program berjalan melalui beberapa tahapan utama dalam analytics pipeline.

## 1️⃣ Load Clean Dataset

Dataset yang telah dibersihkan dibaca dari folder:

```
data/clean/parquet/
```

Data kemudian dimuat ke dalam **Spark DataFrame** untuk dilakukan proses analisis.

## 2️⃣ Perhitungan Total Revenue

Pipeline menghitung **total revenue dari seluruh transaksi** menggunakan fungsi agregasi Spark:

```
sum()
```

Hasil analisis disimpan pada:

```
data/serving/total_revenue
```

## 3️⃣ Top Products Analysis

Program menghitung **10 produk dengan jumlah penjualan tertinggi** menggunakan operasi:

```
groupBy()
sum()
orderBy()
```

Hasil analisis disimpan pada:

```
data/serving/top_products
```

## 4️⃣ Revenue per Category

Pipeline menghitung **pendapatan berdasarkan kategori produk** untuk mengetahui kontribusi setiap kategori terhadap total penjualan.

Hasil analisis disimpan pada:

```
data/serving/category_revenue
```

## 5️⃣ Average Transaction per Customer

Program juga menghitung **rata-rata nilai transaksi pelanggan** menggunakan fungsi:

```
avg()
```

Hasil analisis disimpan pada:

```
data/serving/avg_transaction
```

---

# 📂 Struktur Folder Output

```
data
 ├── clean
 │   └── parquet
 │
 └── serving
     ├── total_revenue
     ├── top_products
     ├── category_revenue
     └── avg_transaction
```

Folder **serving** berisi dataset hasil analisis yang siap digunakan untuk proses visualisasi.

---

# 📊 Visualization Layer

Dataset yang dihasilkan pada **serving layer** kemudian diimport ke **Power BI Desktop** untuk membuat dashboard analitik yang menampilkan:

* **Total Revenue (KPI)**
* **Top Products**
* **Revenue per Category**

Dashboard ini membantu pengguna memahami performa penjualan secara visual dan lebih mudah dianalisis.

---

# 🎯 Kesimpulan

Praktikum ini menunjukkan bagaimana proses analisis data dalam arsitektur Big Data dilakukan melalui beberapa tahapan pipeline mulai dari pemrosesan data hingga visualisasi informasi. PySpark digunakan untuk melakukan agregasi data dan menghasilkan metrik bisnis seperti total revenue, produk terlaris, serta revenue per kategori. Hasil analisis tersebut kemudian disimpan pada serving layer dan diintegrasikan dengan Power BI untuk membangun dashboard analitik yang mampu menyajikan informasi secara visual sehingga memudahkan pengguna memperoleh insight dan mendukung pengambilan keputusan berbasis data.

---

# ▶️ Cara Menjalankan Program

Pastikan PySpark telah terinstall:

```
pip install pyspark
```

Jalankan analytics layer dengan perintah:

```
python scripts/analytics_layer.py
```

Jika program berhasil dijalankan maka terminal akan menampilkan pesan:

```
ANALYTICS LAYER COMPLETED SUCCESS
```
