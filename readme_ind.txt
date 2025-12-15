Judul Project:
Gojek App User Satisfaction Overview-Based On User Reviews & NLP Sentiment Analysis

Deskripsi:
Proyek ini menganalisis user satisfaction dan user sentiment berdasarkan lebih dari 215.000 ulasan pengguna aplikasi mobile Gojek yang ditulis dalam Bahasa Indonesia.
Tujuan analisis ini adalah untuk anaisis berbasis rating dengan mengekstraksi sentimen implisit dari teks ulasan, lalu mengombinasikannya dengan rating eksplisit guna mengungkap ketidakpuasan tersembunyi, permasalahan pengalaman pengguna (UX), serta risiko terhadap kualitas produk.
Sebuah pipeline analitik end-to-end dibangun menggunakan PostgreSQL, Python (NLP), dan Power BI untuk mentransformasi teks mentah yang tidak terstruktur menjadi insight bisnis yang dapat ditindaklanjuti melalui dashboard tingkat eksekutif.

Tools:
1. PostgreSQL: data storage, cleaning, and modeling
2. Python: NLP-based sentiment analysis. Pandas, SQLAlchemy, NLTK (stopwords)
3. Power BI: data modeling, DAX measures, and dashboard visualization

Insight:
1. Rating masih relatif tinggi, namun sentimen dari teks ulasan menunjukkan tingkat kepuasan emosional yang lebih lemah.
2. Terdapat korelasi yang kuat antara rating dan sentimen, yang memvalidasi efektivitas pendekatan NLP yang digunakan.
3. Feedback negatif didominasi oleh isu yang berulang, seperti pembatalan pesanan, perilaku driver, dan error sistem. Permasalahan ini bukan merupakan kejadian terpisah, melainkan indikasi adanya masalah sistemik pada UX dan kebijakan, sehingga memerlukan intervensi di level produk dan kebijakan, bukan hanya penanganan oleh customer service.
4. Beberapa versi aplikasi menunjukkan lonjakan ulasan negatif yang ekstrem. Pada versi tertentu, persentase ulasan negatif melebihi 20%, bahkan mencapai 100% (meskipun kemungkinan dengan volume ulasan yang kecil). Hal ini menjadi indikasi kuat bahwa proses quality control pada rilis aplikasi belum stabil.

Dataset:
https://www.kaggle.com/datasets/ucupsedaya/gojek-app-reviews-bahasa-indonesia

1. Data Ingestion & Profiling (PostgreSQL)
- Load data raw ke PostgreSQL
- Lakukan data validation: Konsistensi jumlah baris, Cek missing value, Analisis Rating distribution, Analisis review text length
- Tambahkan unique review_id sebagai primary key

2. Data Cleaning & Preparation
- Standardisasi format text:Lowercase. Hapus URL, simbol, dan tanda baca
- Menhapus stopwords Bahasa Indonesia
- Menerapkan proses stemming menggunakan Sastrawi
- Menyiapkan teks ulasan yang telah dibersihkan untuk proses penilaian sentimen

3. Sentiment Analysis (Python NLP)
- Mengimplementasikan metode penilaian sentimen berbasis leksikon yang disesuaikan dengan Bahasa Indonesia
- Mendefinisikan kamus kata positif dan negatif
- Mengonversi teks ulasan menjadi: Skor sentimen numerik, Label sentimen (positif / netral / negatif)
- Mengoptimalkan pemrosesan teks untuk menangani data berskala besar secara efisien
- Menyimpan hasil analisis sentimen yang telah diperkaya kembali ke PostgreSQL

4. Data Modeling & Feature Engineering
- Menggabungkan rating, skor sentimen, label sentimen, dan versi aplikasi ke dalam satu tampilan data analitik terkurasi
- Membuat kategori tingkat kepuasan berdasarkan ambang batas rating
- Menyiapkan data untuk analisis deret waktu, korelasi, dan segmentasi

Selanjutnya PowerBI import data tersebut untuk dibuat dashboard dengan struktur:
1. Executive Overview
2. Sentiment & Rating Deep Dive
3. Negative Feedback Analysis
