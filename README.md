# CreditShield: Deteksi Fraud Kartu Kredit Menggunakan Algoritma Random Forest dengan Pendekatan CRISP-DM

## 1. Business Understanding
* **Masalah:** Penipuan kartu kredit mengakibatkan kerugian finansial yang masif bagi institusi keuangan dan nasabah setiap tahunnya. Deteksi manual sangat lambat dan rawan kesalahan.
* **Tujuan Proyek:** Membangun sistem klasifikasi otomatis yang mampu mendeteksi transaksi kartu kredit palsu (Fraud) secara real-time dengan akurasi dan recall yang tinggi untuk meminimalkan false negatives.

## 2. Data Understanding
* **Dataset:** Dataset terdiri dari total 284.807 transaksi kartu kredit (Full Dataset).
* **Karakteristik:** Data memiliki tingkat ketidakseimbangan yang sangat ekstrem (*Highly Imbalanced Data*), di mana kelas Normal (0) sebanyak 284.315 transaksi, sedangkan kelas Fraud (1) hanya sebesar 492 transaksi.

### Visualisasi Distribusi Kelas:
![Distribusi Kelas](distribusi_kelas.png)

## 3. Data Preparation
* **Feature Scaling:** Melakukan standardisasi dan normalisasi fitur `Amount` menggunakan `StandardScaler`.
* **Handling Imbalanced Data:** Mengimplementasikan teknik **SMOTE (Synthetic Minority Over-sampling Technique)** pada data training untuk menyeimbangkan jumlah sampel kelas Fraud secara sintetis agar model tidak bias.

## 4. Modeling
* Menggunakan algoritma **Random Forest Classifier** (`n_estimators=10`, `max_depth=10`) yang dilatih menggunakan data hasil resampling SMOTE untuk menangani ketimbang data secara otomatis dan efisien.

## 5. Evaluation
Model dievaluasi menggunakan *Confusion Matrix* dan skor *Recall* pada data testing:

### Visualisasi Confusion Matrix:
![Confusion Matrix](confusion_matrix.png)

### Performance Metrics:
* **Precision (Kelas 1 / Fraud):** 0.34
* **Recall (Kelas 1 / Fraud):** 0.80 (Model sukses mendeteksi 80% dari total transaksi fraud yang ada)
* **ROC AUC Score:** 0.9583 (Membuktikan ketangguhan model dalam memisahkan transaksi normal dan fraud).

## 6. Deployment
* Model dideploy menggunakan web dashboard interaktif berbasis **Streamlit** untuk simulasi deteksi transaksi real-time.
