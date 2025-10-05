# Capstone Project Data Classification and Summarization Using IBM Granite : Analisis Sentimen Pengguna Aplikasi Maxim Menggunakan SVM dan IBM Granite

## Project Overview

Proyek ini merupakan bagian dari Capstone Project program IBM Skillbuild: Data Classification and Summarization Using IBM Granite.
Tujuan proyek ini adalah untuk menganalisis sentimen pengguna aplikasi Maxim dengan membandingkan performa model tradisional machine learning (SVM) dan model foundation AI dari IBM, yaitu Granite-3.3-8b-instruct.

Analisis dilakukan untuk menggali persepsi pengguna terhadap layanan Maxim, sekaligus melihat bagaimana kedua pendekatan AI ini mengklasifikasikan sentimen dan memberikan insight yang bermakna dari data ulasan pengguna.

## Raw Dataset Link

Dataset mentah hasil scraping berisi 20.000 ulasan pengguna aplikasi Maxim yang diambil langsung dari Google Play Store menggunakan teknik web scraping.
Data ini berisi teks ulasan, rating, serta tanggal ulasan yang digunakan untuk analisis sentimen.

https://github.com/Rahmat-Ramadhan15/maxim-sentiment-comparison-ibm-vs-svm/blob/0f2ee1d1b945547e83d75921511086e7217f6247/maxim_reviews.csv

## Insight and Finding

Setelah melakukan analisis sentimen terhadap ulasan pengguna aplikasi Maxim di Google Play Store menggunakan dua pendekatan berbeda — SVM (Support Vector Machine) 
dan IBM Granite 3.3-8B-Instruct — diperoleh beberapa temuan menarik:

1. Hasil Analisis Menggunakan IBM Granite

   Model IBM Granite 3.3-8B-Instruct menunjukkan kemampuan yang sangat baik dalam memahami konteks kalimat dan nuansa emosi pengguna, bahkan pada kalimat ambigu atau mengandung campuran sentimen.
Temuan ini dihasilkan dari 70 ulasan yang dianalisis menggunakan model IBM Granite 3.3-8B Instruct:
  
- Dominasi Krisis Sentimen Negatif 🚨
    
    Distribusi sentimen menunjukkan bahwa sebagian besar pengguna mengalami ketidakpuasan terhadap layanan Maxim.
    
   - Negatif	82.9%	Menunjukkan tingginya tingkat frustrasi dan ketidakpuasan pengguna.
    
   - Positif	11.4%	Titik terang yang perlu dipertahankan dan diperkuat.
    
   - Netral/Campuran	5.7%	Area sensitif yang dapat beralih menjadi negatif jika tidak ditangani.
    
    💬 Insight: Dominasi ulasan negatif menandakan adanya masalah mendasar yang perlu segera ditangani, khususnya pada aspek teknis dan interaksi pengguna.

- Lima Fokus Kritis (Top 5 Pain Points)

  Analisis mendalam terhadap ulasan negatif mengungkap lima aspek utama yang menjadi sumber keluhan pengguna:

  - Aplikasi (41 Kasus): Masalah teknis yang dominan, termasuk bug, waktu loading yang lambat, kesalahan peta (navigasi), dan kendala pada proses login atau verifikasi.
  - Driver (24 Kasus): Isu-isu operasional yang melibatkan mitra pengemudi, seperti sering terjadi penolakan order dan komunikasi yang buruk.
  - Pembayaran (19 Kasus): Kendala finansial, terutama masalah saldo, transaksi gagal, dan kurangnya transparansi mengenai biaya tidak terduga.
  - Waktu (17 Kasus): Keluhan tentang keterlambatan yang bersumber dari dua sisi: waktu tunggu pengemudi yang lama dan waktu proses sistem aplikasi yang lambat.
  - Layanan Pelanggan (15 Kasus): Kualitas layanan dukungan yang buruk, ditandai dengan respons yang lambat atau tidak efektif dalam penanganan keluhan.
 
- Keunggulan

  Meskipun didominasi sentimen negatif, beberapa aspek tetap mendapat apresiasi positif dari pengguna.

  - Harga (6 Kasus): Harga kompetitif dan adanya promosi menarik adalah faktor utama pendorong kepuasan pengguna.
  - Driver (2 Kasus): Pengemudi yang dinilai sopan dan profesional mendapat apresiasi yang tinggi dari pengguna.
  - Aplikasi (2 Kasus): Pengalaman positif terkait kemudahan penggunaan dan tampilan atau antarmuka aplikasi.
 
2. Perbandingan Singkat dengan Model SVM

   Sebagai pembanding, model SVM mencapai akurasi 81,9%, tetapi hanya mampu melakukan klasifikasi positif dan negatif tanpa memahami konteks.
   
    Sebaliknya, IBM Granite mampu menggali dimensi opini pengguna secara lebih mendalam, termasuk aspek spesifik penyebab ketidakpuasan, sehingga menghasilkan insight yang lebih bernilai untuk pengambilan keputusan bisnis.

   ## AI Support Explanation

   Model IBM Granite-3.3-8B-Instruct digunakan untuk mendukung proses insight generation melalui analisis semantik dan klasifikasi sentimen pada ulasan pengguna aplikasi Maxim.

   Kelebihan model ini antara lain:

   - Memahami konteks bahasa Indonesia secara mendalam.
   - Mengidentifikasi aspek spesifik dalam ulasan (misalnya: layanan, driver, aplikasi).
   - Membantu menemukan tema utama dari keluhan dan apresiasi pelanggan.
  
   Model ini dijalankan melalui API Replicate yang diintegrasikan ke dalam Google Colab Notebook.
Setiap ulasan dikirim ke model secara bergantian (batch processing), dan hasilnya berupa klasifikasi sentimen serta konteks topik utama dari setiap ulasan.

### Data dan Resource Pendukung

Kamus Slag: https://www.kaggle.com/datasets/fornigulo/kamus-slag

InSet (Indonesia Sentiment Lexicon): https://github.com/fajri91/InSet
