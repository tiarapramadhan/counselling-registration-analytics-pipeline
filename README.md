# 🧠 Counselling Registration Analytics Pipeline

Transformasi data pendaftaran layanan konseling dari format semi-terstruktur menjadi **analytics-ready dataset** melalui proses eksplorasi, normalisasi, standarisasi, hingga visualisasi dashboard menggunakan Microsoft Excel dan Google Sheets.

---

# 🏢 Business Context

Sebuah platform layanan konseling B2B mengumpulkan data pendaftaran konseling melalui formulir online yang telah mengalami beberapa kali revisi.

Akibatnya, hasil ekspor data memiliki struktur **Question / Response** dengan urutan pertanyaan yang berbeda-beda, variasi penulisan label, penggunaan dua bahasa (Indonesia & Inggris), serta banyak nilai kosong (missing value).

Kondisi tersebut menyebabkan data tidak dapat langsung digunakan untuk proses analisis maupun pembuatan dashboard sehingga diperlukan proses transformasi data secara menyeluruh.

---

# 🎯 Project Objectives

Project ini bertujuan untuk:

- Mengidentifikasi seluruh variasi label pertanyaan yang muncul pada dataset.
- Menyusun kamus mapping untuk standarisasi label pertanyaan.
- Mengubah struktur data dari format **Wide** menjadi **Tidy Data**.
- Membersihkan dan menyeragamkan nilai data agar konsisten.
- Menghasilkan dataset yang siap digunakan untuk analisis.
- Membangun dashboard sebagai media visualisasi insight.

---

# 📂 Dataset Overview

Dataset merupakan hasil ekspor formulir pendaftaran layanan konseling perusahaan.

| Informasi | Nilai |
| --- | --- |
| Jumlah Data | 7.270 pendaftaran |
| Struktur Awal | Wide Format |
| Kolom Pertanyaan | 10 pasang Question / Response |
| Bahasa | Indonesia & Inggris |
| Missing Value | Ya |
| Format Awal | Semi-terstruktur |

---

# ⚠️ Problem Statement

Beberapa tantangan utama pada dataset antara lain:

- Label pertanyaan tidak konsisten meskipun memiliki makna yang sama.
- Urutan pertanyaan berbeda pada setiap responden.
- Terdapat kombinasi Bahasa Indonesia dan Bahasa Inggris.
- Banyak nilai kosong (missing value).
- Struktur data belum mengikuti prinsip **Tidy Data**.
- Dataset belum siap digunakan untuk analisis maupun dashboard.

---

# 🔄 Data Processing Workflow

```text
📥 Raw Dataset
        │
        ▼
🔍 Data Exploration
        │
        ▼
🗂 Mapping Dictionary
        │
        ▼
🔄 Data Normalization
        │
        ▼
📋 Tidy Transformation
        │
        ▼
🧹 Data Cleaning
        │
        ▼
🧩 Data Standardization & Categorization
        │
        ▼
✨ Analytics-ready Dataset
        │
        ▼
📊 Pivot Tables
        │
        ▼
📈 Dashboard & Insights
```

---

# 📖 Data Processing Pipeline

## 1. Raw Dataset

Tahap awal menggunakan dataset mentah hasil ekspor formulir registrasi konseling.

Karakteristik data:

- 7.270 data pendaftaran.
- Struktur Question & Response.
- Label pertanyaan tidak konsisten.
- Campuran Bahasa Indonesia dan Bahasa Inggris.
- Banyak nilai kosong (missing value).

---

## 2. Data Exploration

Melakukan eksplorasi seluruh kolom **Question 1–10** untuk mengidentifikasi seluruh variasi label pertanyaan yang muncul.

Tahap ini menghasilkan daftar label unik yang menjadi dasar proses standarisasi.

---

## 3. Mapping Dictionary

Menyusun kamus mapping untuk mengelompokkan berbagai variasi label pertanyaan menjadi satu kategori standar.

Contoh:

| Label Asli | Standarisasi |
|------------|--------------|
| Company Code | Perusahaan |
| Nama Perusahaan | Perusahaan |
| Business Entity | Perusahaan |
| Kode Perusahaan | Perusahaan |

Pendekatan yang sama diterapkan pada seluruh variasi label lainnya sehingga seluruh atribut memiliki nama yang konsisten.

---

## 4. Data Normalization

Mengubah struktur data dari format:

```
Question 1
Response 1

Question 2
Response 2
...
```

menjadi format yang lebih mudah diproses dengan menempatkan setiap pasangan **Question–Response** pada satu baris.

Tahapan ini menjadi fondasi proses transformasi berikutnya.

---

## 5. Tidy Transformation

Melakukan transformasi sehingga:

- setiap baris merepresentasikan satu pendaftaran,
- setiap kolom merepresentasikan satu atribut.

Hasil transformasi mengikuti prinsip **Tidy Data** sehingga siap digunakan pada proses analisis.

---

## 6. Data Cleaning & Standardization

Melakukan proses pembersihan dan standarisasi nilai agar lebih konsisten.

Proses yang dilakukan meliputi:

- standarisasi gender,
- standarisasi perusahaan,
- standarisasi divisi/departemen,
- pengelompokan kategori usia,
- standarisasi layanan konseling,
- standarisasi informed consent,
- penanganan missing value,
- penyederhanaan kategori untuk dashboard.

Tahapan ini bertujuan meningkatkan kualitas data sekaligus mempermudah proses analisis dan visualisasi.

---

## 7. Analytics-ready Dataset

Menghasilkan dataset akhir yang telah:

- bersih,
- konsisten,
- mudah dibaca,
- siap dianalisis,
- siap digunakan pada dashboard.

Dataset akhir tersedia pada folder:

```
data/cleaned/
```

---

## 8. Dashboard

Dataset akhir digunakan untuk membangun dashboard menggunakan **Pivot Table** dan **Chart** di Microsoft Excel.

Dashboard menyajikan berbagai ringkasan informasi yang memudahkan stakeholder memahami karakteristik pendaftaran konseling.

---

# 📊 Dashboard Overview

Dashboard menampilkan beberapa insight utama, antara lain:

- Jumlah pendaftaran per perusahaan.
- Distribusi usia responden.
- Distribusi gender responden.
- Topik permasalahan yang paling sering dibahas.
- Perbandingan jenis layanan konseling.
- Tren jumlah pendaftaran dari waktu ke waktu.

---

# 🖼 Dashboard Preview

<p align="center">
<img src="assets/dashboard-preview.png" width="100%">
</p>

---

# 📁 Workbook Documentation

Seluruh proses transformasi didokumentasikan dalam satu workbook sehingga setiap tahapan dapat ditelusuri secara berurutan.

Workbook terdiri dari beberapa sheet berikut.

| Sheet | Deskripsi |
|--------|-----------|
| Raw Data | Dataset mentah hasil ekspor |
| Eksplorasi Data | Identifikasi variasi label pertanyaan |
| Kamus Mapping | Standarisasi label pertanyaan |
| Normalized Raw | Transformasi awal Question–Response |
| Tidy Data | Dataset hasil transformasi |
| Grouping | Pengelompokan kategori |
| Cleaned Data | Dataset final |
| Pivot Table | Agregasi data |
| Dashboard | Visualisasi insight |

Workbook tersedia pada folder:

```
workbook/
```

---

# 📂 Project Structure

```text
.
├── assets/
│   └── dashboard-preview.png
│
├── data/
│   ├── raw/
│   │   └── Anonymized_Study_Case_Data.csv
│   │
│   └── cleaned/
│       └── counselling_registration_cleaned.csv
│
├── workbook/
│   └── counselling-registration-analytics-pipeline.xlsx
│
├── .gitignore
├── LICENSE
└── README.md
```

---

# 🛠 Tools

| Category | Tools |
| --- | --- |
| Spreadsheet | Google Sheets |
| Spreadsheet | Microsoft Excel |
| Formula | QUERY |
| Formula | FILTER |
| Formula | UNIQUE |
| Formula | IF, INDEX, MATCH, REGEX, dll. |
| Data Preparation | Data Cleaning & Transformation |
| Visualization | Pivot Table & Excel Charts |
| Version Control | Git & GitHub |

---

# 💼 Skills Demonstrated

### 📊 Data Analysis

- Exploratory Data Analysis (EDA)
- Data Profiling
- Business Analysis
- Dashboard Reporting
- Data Visualization

### ⚙️ Data Engineering

- Data Cleaning
- Data Transformation
- Data Normalization
- Data Standardization
- ETL Thinking
- Analytics-ready Dataset

### 📈 Business Intelligence

- Dashboard Development
- KPI Reporting
- Pivot Table Analysis
- Insight Presentation

---

# 🚀 Conclusion

Project ini menunjukkan bagaimana data pendaftaran layanan konseling yang awalnya berbentuk **semi-terstruktur** dapat diproses menjadi **analytics-ready dataset** melalui tahapan eksplorasi, pemetaan, normalisasi, transformasi, pembersihan, dan standarisasi data.

Selain menghasilkan dashboard sebagai media visualisasi insight, seluruh proses transformasi juga terdokumentasi secara transparan dalam satu workbook sehingga setiap tahapan dapat ditelusuri kembali dengan mudah. Pendekatan ini mencerminkan alur kerja seorang Data Analyst dalam mempersiapkan data sebelum memasuki tahap analisis dan pelaporan.
