# Predict Customer Personality To Boost Marketing Campaign

## Created By:
**Name:** Oknardo Budi Setiawan Tulung  
**Email:** oknardotulung@gmail.com  
**LinkedIn:** [www.linkedin.com/in/oknardo-tulung](https://www.linkedin.com/in/oknardo-tulung)  
**GitHub:** [https://github.com/oknardo](https://github.com/oknardo)

## Dataset
Dataset diperoleh dari Rakamin Academy, berisi data historical marketing campaign pada suatu perusahaan.

## Latar Belakang dan Objektif
### Latar Belakang
Sebuah perusahaan dapat berkembang dengan pesat saat mengetahui perilaku customer personality nya, sehingga dapat memberikan layanan serta manfaat lebih baik
kepada customers yang berpotensi menjadi loyal customers. Dengan mengolah data historical marketing campaign guna menaikkan performa dan menyasar customers yang tepat
agar dapat bertransaksi di platform perusahaan, dari insight data tersebut fokus kita adalah membuat sebuah model prediksi kluster sehingga memudahkan 
perusahaan dalam membuat keputusan 


### Objektif
- Meningkatkan performa marketing campaign
- Menyasar customer yang tepat untuk meningkatkan transaksi di platform perusahaan

## Batasan Masalah
- Analisis dilakukan berdasarkan data historical marketing campaign yang diberikan
- Fokus pada peningkatan conversion rate dan segmentasi customer

## Data dan Asumsi
### Data
- Data berisi informasi tentang pengunjung website dan tindakan yang mereka lakukan selama mengunjungi situs
- Data meliputi umur, penghasilan, pengeluaran, dan variabel lainnya yang relevan

### Asumsi
- Data yang disediakan lengkap dan representatif untuk analisis
- Tidak ada bias yang signifikan dalam data

## Data Preprocessing
1. **Handling Missing Value**: Menghapus nilai null pada kolom `income`.
2. **Handling Outlier**: Filtering outlier dengan IQR.
3. **Handling Inappropriate Value**: Mengubah tipe data pada feature `Dt_Customer` menjadi datetime64.
4. **Feature Selection**: Menghapus fitur yang tidak diperlukan seperti `Unnamed: 0`, `ID`, `Z_CostContact`, `Z_Revenue`, `Year_Birth`, dll.
5. **Feature Encoding**: Label encoding pada feature `Education`.
6. **Feature Transformation**: Standarisasi feature numerik.
7. **Feature Engineering**: Membuat feature baru seperti `conversion rate`, `customer age`, `total child`, `total transaction`, `total spending`, `total accepted campaign`.

## Analisis Data
### Proses Analisis
1. **Melakukan feature engineering: conversion rate**
2. **Menghitung dan mengelompokkan 'umur' menjadi beberapa kelompok**
3. **Membuat plot yang menunjukkan hubungan antara conversion rate dan jenis user**
4. **Interpretasi plot untuk menemukan hubungan antara umur customer dan conversion rate**

### Hasil Analisis
1. **Analisis conversion rate dengan variabel lain seperti umur, penghasilan, pengeluaran**
2. **Pencarian pola perilaku konsumen berdasarkan conversion rate**

## Data Modeling
### Elbow Method

![image](https://github.com/user-attachments/assets/e6d80593-f910-4cb0-8cf6-2cac6ea24ad3)

### Distortion score 

![image](https://github.com/user-attachments/assets/9990174f-c5fc-4cda-9171-eb9f7e46db6b)

### Silhoutte score 

![image](https://github.com/user-attachments/assets/1ef38f42-75d3-40bf-91d9-c847df685664)

dari analisis ini di dapatkan value terbaik untuk clustering berada di k=4.

### Model Evaluation
- **Elbow Method**: Optimal number of clusters (k=4).
- **Silhouette Score**: 0.470 untuk 2 clusters hingga 0.218 untuk 9 clusters.

## Customer Personality Analysis for Marketing Retargeting

### Total USer

![image](https://github.com/user-attachments/assets/45479382-0b2e-4842-9462-d59188a60a13)

### Distribusi Total SPending, Total Transaction, COnversion Rate, Total Visit

![image](https://github.com/user-attachments/assets/4040b099-e460-4b1c-aa8e-588a1ef4314b)

![image](https://github.com/user-attachments/assets/34204dec-7c65-41ec-b725-1e12e652ec40)

Pembagian kelompok hasil klasterisasi dibagi dengan empat kategori:
1. **Risk to Churn**: Total income dan total spending paling rendah.
2. **Low Spender**: Rata-rata pendapatan diatas `risk to churn` dengan total spending dibawah `medium spender`.
3. **Mid Spender**: Pendapatan rata-rata dan total spending dibawah `high spender`.
4. **High Spender**: Rata-rata pendapatan dan total pengeluaran paling besar.

### Insight dan Rekomendasi

![Table Potential Saving](https://github.com/user-attachments/assets/630b0a6d-e43e-41c4-b81f-dba35dd30295)

1. **Risk of Churn**: Tingkatkan minat pembelian user dengan promosi, voucher, atau rekomendasi produk personal.
2. **Low Spender**: Fokus pada peningkatan penawaran melalui promosi yang dipersonalisasi.
3. **High Spender**: Berikan layanan premium dan program loyalitas untuk mempertahankan pelanggan.

## Potensi Dampak
- **Potential GMV**: High Spender (176 juta) dan Mid Spender (668 juta).
- **Potential Savings**: Reduksi cost sebesar IDR 40.58 Juta dengan optimasi promo pada Mid Spender.

## Kesimpulan
- Perusahaan dapat meningkatkan performa marketing campaign dengan menyasar customer yang tepat berdasarkan hasil analisis.

## Saran
- Optimalkan marketing campaign dengan retargeting pada cluster customer yang memiliki conversion rate tinggi.
- Lakukan evaluasi berkala untuk memastikan efektivitas strategi yang diterapkan.
