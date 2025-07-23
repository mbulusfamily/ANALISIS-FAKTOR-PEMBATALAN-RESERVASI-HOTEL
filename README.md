# 📊 Analisis Faktor Pembatalan Reservasi Hotel  
_Studi Komparatif antara City Hotel dan Resort Hotel_

---

## 📖 Gambaran Umum

Repositori ini berisi notebook analisis lengkap: **DATA SET HOTEL 1.ipynb** yang mengulas secara sistematis faktor-faktor utama pembatalan reservasi hotel melalui pendekatan akademik dan praktis. Analisis dilakukan dengan eksplorasi data, pembersihan, statistik deskriptif, komparasi, korelasi, dan visualisasi berbasis dataset _Hotel Bookings_ (119.390 records, 2015–2017, sumber Kaggle).  
Penekanan penelitian pada perbedaan serta strategi mitigasi pembatalan _City Hotel_ vs _Resort Hotel_.

---

## 🏢 Ruang Lingkup Analisis

- **Studi komparatif**: City Hotel vs Resort Hotel.
- **Fokus variabel utama**:  
  - Lead time (jarak hari antara booking dan check-in)
  - Average Daily Rate (harga per malam)
  - Special requests (permintaan khusus)
  - Booking changes (perubahan pesanan)
  - Segmentasi market & customer type
- **Metode**:  
  - Pembersihan data (handling missing values & duplikat)
  - Statistik deskriptif & komparatif
  - Korelasi (Pearson)
  - Visualisasi (matplotlib, seaborn)
  - Rekomendasi bisnis berbasis data

---

## 📚 Rangkaian Analisis dan Isi Notebook

### 1. BAB I. PENDAHULUAN

- **Latar Belakang**  
  Dampak pembatalan reservasi pada revenue, profit, dan perencanaan operasional hotel.
- **Rumusan Masalah**  
  Faktor signifikan, perbedaan pola pembatalan antar tipe hotel, dan strategi mitigasi.
- **Tujuan Penelitian**  
  Identifikasi faktor utama, komparasi pola pembatalan, serta strategi manajemen berbasis data.

### 2. BAB II. TINJAUAN PUSTAKA & METODOLOGI

- **Landasan Teori**:  
  - Teori perilaku konsumen (Consumer Behavior)
  - Revenue management hotel
- **Metodologi:**
  - Tipe penelitian: deskriptif-kuantitatif, komparatif dan cross-sectional
  - Sumber data: dataset Kaggle Hotel Bookings 2015–2017
  - Tahapan:
    1. Data loading & overview
    2. Data cleaning: deteksi & penanganan missing value, duplikasi
    3. Feature engineering (grouping lead time, ADR banding, dsb)
    4. Analisis statistik (deskriptif, t-test, chi-square, korelasi)
    5. Visualisasi
    6. Formulasi rekomendasi berdasarkan evidence

### 3. BAB III. ANALISIS DATA DAN PEMBAHASAN

#### A. _Data Preparation_ & _Cleaning_
- Import data dari ZIP, info struktur, tipe data, dan data sample
- Deteksi & visualisasi missing value (bar chart)
- Penghapusan duplikat, _drop column_ dengan missing >80% (company)
- Imputasi median (numerik), modus (kategorikal)
- Finalisasi dataset bebas missing value & duplikat

#### B. Statistik Deskriptif & Komparatif
- **Tingkat pembatalan keseluruhan**:  
  Pie chart, bar chart, insight jumlah booking batal, completed, rasio pembatalan
- **Perbandingan City Hotel vs Resort Hotel**:  
  - Jumlah booking, pembatalan, completed, rata-rata ADR, lead time
  - Visualisasi perbandingan (bar, boxplot, dsb)
  - Penekanan pada market focus & segmentasi pelanggan

#### C. Analisis Faktor Pembatalan
- **Lead Time**:
  - Grouping (0–7, 8–30, 31–90, 91–365, >365 hari)
  - Korelasi dengan pembatalan, visualisasi bar, scatter, boxplot hotel type
  - Analisis _correlation strength_ & insight
- **Average Daily Rate (ADR)**:
  - Statistik ADR booking batal vs tidak, per tipe hotel
  - Analisis _price sensitivity_, banding harga (ADR band), korelasi ADR-cancellation
  - Visualisasi: distribusi, boxplot, bar chart
- **Special Requests & Faktor Lain**:
  - Analisis jumlah permintaan khusus & dampak pada pembatalan
  - Korelasi numerik utama: lead_time, adr, special_requests, booking_changes dsb
  - Analisis _market segment_ dan _customer type_ (bar chart), korelasi heatmap

#### D. Insight Bisnis
- Ringkasan temuan komparatif, faktor dominan, serta potensi revenue loss akibat pembatalan

### 4. BAB IV. KESIMPULAN DAN REKOMENDASI

- **Ringkasan Temuan**:
  - City Hotel: tingkat pembatalan lebih tinggi (~30%) dibanding Resort Hotel (~23%)
  - Faktor prediktif utama: lead time (+), ADR (+), special requests (-), booking changes (+)
  - Market segment _Online TA_ dan _Groups_ mendominasi pembatalan
- **Rekomendasi Strategis**:
  - **City Hotel:** dynamic pricing, graduated deposit policy, engagement program, overbooking strategy, flexible cancellation
  - **Resort Hotel:** premium experience, overbooking agresif, loyalty program, seasonal pricing
- **Ekspor Hasil**:
  - Ekspor dataset bersih & ringkasan analisis ke Excel (multi-sheet)
  - Panduan ekspor ke PDF untuk kebutuhan laporan formal

---

## 📦 Dataset

- **Sumber**: [Kaggle - Hotel Booking Demand](https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand)
- **File**: hotel_bookings.csv (ZIP)
- **Periode**: 2015–2017
- **Jumlah records**: 119.390
- **Kolom kunci**:  
  - hotel, is_canceled, lead_time, adr, total_of_special_requests, booking_changes, market_segment, customer_type, deposit_type, dsb.

---

## 🏷️ Fitur Notebook

- **Automasi data cleaning**:  
  Duplikasi & missing value diatasi otomatis, dataset siap eksplorasi
- **Eksplorasi statistik & visualisasi**:  
  Pie, bar, boxplot, distribusi, heatmap korelasi
- **Komparasi City Hotel vs Resort Hotel**:  
  Statistik terpisah & visualisasi khusus
- **Analisis faktor utama**:  
  Korelasi variabel, segmentasi pasar, price sensitivity
- **Insight bisnis**:  
  Rekomendasi actionable berbasis temuan data
- **Ekspor hasil**:  
  File Excel multi-sheet (data bersih, ringkasan hotel, analisis lead time, matriks korelasi)

---

## 🚀 Petunjuk Penggunaan

1. **Instal dependensi**  
    ```bash
    pip install pandas numpy matplotlib seaborn openpyxl
    ```
2. **Download dataset**  
   [hotel_bookings.csv.zip dari Kaggle](https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand)
3. **Ubah path file** di cell data loading notebook sesuai lokasi Anda.
4. **Jalankan notebook** secara berurutan di Jupyter Notebook/Lab/VSCode.
5. **Ekspor hasil**  
   - Gunakan cell ekspor untuk hasil ke Excel (tersedia di bagian akhir notebook)
   - Untuk PDF: File → Export As → PDF atau Print ke PDF

---

## 📊 Hasil Kunci & Temuan

- **Tingkat pembatalan total**: ±27%
- **City Hotel**: tingkat pembatalan ~30%, Resort Hotel ~23%
- **Faktor paling signifikan**:  
  - _Lead time_ (semakin lama, makin besar kemungkinan batal; r ≈ +0,18)
  - _ADR_ (harga tinggi → kecenderungan batal naik; r ≈ +0,11)
  - _Special requests_ (semakin banyak permintaan, makin kecil peluang batal; r ≈ -0,18)
  - _Booking changes_ juga berpengaruh positif pada risiko batal
- **Segmentasi market**:  
  - _Online TA_ & _Groups_ paling tinggi tingkat pembatalannya
  - Booking dengan deposit _Non Refund_ hampir pasti batal
- **Potensi revenue loss**:  
  - Dihitung berdasarkan rata-rata ADR × jumlah pembatalan
- **Dataset setelah cleaning**:  
  - Bebas duplikasi, missing value, siap analisis statistik dan machine learning
- **Strategi bisnis berbeda** untuk City Hotel dan Resort Hotel menyesuaikan karakteristik pelanggan dan pola pembatalan

---

## 📄 Deliverables

- Notebook analisis terstruktur sesuai standar laporan penelitian (BAB I–IV)
- Visualisasi & tabel ringkasan utama
- File Excel multi-sheet hasil ekspor
- Panduan ekspor ke PDF
- Rekomendasi manajerial dan _insight_ berbasis data

---

## 💡 Catatan

- Cocok untuk skripsi, tugas akhir, praktisi revenue management hotel, dan pembelajaran EDA prediktif
- Semua kode, visualisasi, dan insight dapat dimodifikasi untuk pengembangan lebih lanjut (misal: prediksi pembatalan dengan machine learning)
- Struktur dan dokumentasi sudah _reproducible_, mudah diperluas

---

## 👨‍💻 Author

> Disusun oleh: **mbulusfamily**  
> Tahun: 2025

---
