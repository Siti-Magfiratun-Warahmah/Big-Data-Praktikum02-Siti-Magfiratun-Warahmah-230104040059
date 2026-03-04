# PRAKTIKUM 2 – Batch Data Ingestion & Processing with Spark

**Proyek:** BIGDATA-SPARK-230104040059

Program ini dibuat untuk memenuhi instruksi **Praktikum 2 mata kuliah Big Data Technology**.
Praktikum ini berfokus pada implementasi **Batch Data Pipeline menggunakan Apache Spark** untuk melakukan proses ingestion, pembersihan data, transformasi, serta analisis data transaksi e-commerce.

---

# 👩‍🎓 Identitas Mahasiswa

Nama : **Siti Magfiratun Warahmah**
NIM : **230104040059**

---

# 🚀 Deskripsi Program

Program ini merupakan implementasi **batch data processing menggunakan Apache Spark dengan PySpark**.

Pipeline yang dibuat bertujuan untuk melakukan pemrosesan data transaksi e-commerce secara terstruktur melalui beberapa tahapan pemrosesan data.

Proses yang dilakukan dalam pipeline ini meliputi:

✔ Membaca dataset mentah (raw data)
✔ Membersihkan data (data cleaning)
✔ Melakukan transformasi data
✔ Menghitung metrik bisnis
✔ Menyimpan hasil pemrosesan ke dalam beberapa layer data

Dataset yang diproses merupakan **dataset transaksi e-commerce** yang berisi informasi produk, kategori, jumlah penjualan, serta nilai transaksi.

---

# 🛠️ Teknologi yang Digunakan

Lingkungan pengembangan program:

* Python 3.12
* Apache Spark 4.1.1
* PySpark
* Visual Studio Code
* WSL Ubuntu

---

# 📊 Dataset

Dataset yang digunakan dalam praktikum ini adalah:

**ecommerce_raw.csv**

Dataset ini berisi data transaksi e-commerce yang digunakan untuk melakukan analisis penjualan produk.

Hasil proses pipeline menunjukkan bahwa:

* Total Raw Records : **122400**
* Total Cleaned Records : **113274**
* Data Removed : **9126**

Data yang tidak memenuhi kriteria kualitas akan dihapus pada tahap **data cleaning**.

---

# ⚙️ Cara Kerja Program

Program berjalan melalui beberapa tahapan utama dalam pipeline.

---

## 1️⃣ Inisialisasi SparkSession

Program dimulai dengan membuat **SparkSession** sebagai entry point Apache Spark.

SparkSession digunakan untuk menjalankan proses pemrosesan data menggunakan Spark.

---

## 2️⃣ Membaca Dataset

Dataset mentah dibaca dari file:

```
data/raw/ecommerce_raw.csv
```

Data kemudian dimuat ke dalam **DataFrame Spark** untuk diproses lebih lanjut.

---

## 3️⃣ Data Cleaning

Pada tahap ini dilakukan proses pembersihan data untuk memastikan kualitas dataset.

Proses ini meliputi:

* Menghapus data yang tidak valid
* Menghapus nilai kosong
* Memastikan format data sesuai

Setelah proses cleaning selesai, jumlah data yang tersisa menjadi:

**113274 baris data**

---

## 4️⃣ Transformasi Data

Setelah data dibersihkan, pipeline melakukan proses transformasi untuk menyiapkan data yang akan digunakan dalam analisis bisnis.

Transformasi ini dilakukan menggunakan operasi DataFrame pada Apache Spark.

---

## 5️⃣ Perhitungan Business Metrics

Pada tahap ini pipeline melakukan agregasi data untuk menghasilkan metrik bisnis penting, yaitu:

* **Top 5 Products**
* **Category Revenue**

Operasi agregasi dilakukan menggunakan fungsi Spark seperti:

```
groupBy()
sum()
```

---

## 6️⃣ Penyimpanan Data

Hasil pemrosesan data disimpan ke dalam beberapa layer penyimpanan data, yaitu:

### Clean Layer

```
data/clean/parquet/
data/clean/partitioned_by_category/
```

### Curated Layer

```
data/curated/top_products/
data/curated/category_revenue/
```

Data disimpan dalam format **Parquet** untuk meningkatkan efisiensi penyimpanan dan performa query.

---

# 📂 Struktur Folder Output

Struktur folder hasil pipeline adalah sebagai berikut:

```
data
 ├── clean
 │   ├── parquet
 │   └── partitioned_by_category
 │
 ├── curated
 │   ├── avg_transaction
 │   ├── category_revenue
 │   └── top_products
 │
 └── raw
     └── ecommerce_raw.csv
```

Struktur ini menunjukkan pembagian data berdasarkan layer pemrosesan yaitu **raw layer, clean layer, dan curated layer**.

---

# 📊 Hasil Analisis

## Top 5 Products

| Product    | Total Quantity |
| ---------- | -------------- |
| Tablet     | 40898          |
| Laptop     | 40654          |
| Monitor    | 40629          |
| Headphones | 40506          |
| Phone      | 40314          |

Produk **Tablet** merupakan produk dengan jumlah penjualan tertinggi.

---

## Category Revenue

Kategori dengan pendapatan tertinggi berasal dari kategori **Electronics dan Computing**, yang menunjukkan bahwa produk teknologi memiliki kontribusi besar terhadap total transaksi e-commerce.

---

# ✅ Hasil Eksekusi Pipeline

Pipeline berhasil dijalankan dengan hasil berikut:

* Spark Version : **4.1.1**
* Raw Records : **122400**
* Cleaned Records : **113274**
* Data Removed : **9126**
* Execution Time : **26.48 seconds**

Program berhasil dijalankan tanpa error dengan pesan:

```
PIPELINE COMPLETED SUCCESSFULLY
```

---

# 🎯 Kesimpulan

Praktikum ini menunjukkan bahwa:

✔ Apache Spark dapat digunakan untuk memproses data dalam jumlah besar secara efisien
✔ Proses batch pipeline dapat digunakan untuk melakukan data ingestion dan transformasi data
✔ Format Parquet lebih efisien untuk penyimpanan data dibandingkan CSV
✔ Analisis data dapat menghasilkan insight bisnis seperti produk terlaris dan pendapatan per kategori

---

# ▶️ Cara Menjalankan Program

Pastikan PySpark telah terinstall:

```
pip install pyspark
```

Kemudian jalankan pipeline dengan perintah:

```
python scripts/batch_pipeline_enterprise.py
```

Jika pipeline berhasil dijalankan, maka terminal akan menampilkan pesan:

```
PIPELINE COMPLETED SUCCESSFULLY
```

