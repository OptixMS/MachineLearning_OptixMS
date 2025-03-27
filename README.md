# MachineLearning_OptixMS

## 📚 Pengertian dan Fungsi
MachineLearning_OptixMS adalah bagian teknis dari OptixMS yang berfokus pada implementasi teknik Machine Learning untuk memprediksi dan menganalisis data alarm. Proyek ini dirancang untuk mengatasi masalah ketidakseimbangan data (class imbalance) pada dataset alarm dan melakukan prediksi menggunakan beberapa arsitektur model Machine Learning.

Proyek ini bertujuan untuk mengembangkan model prediksi yang andal dengan memanfaatkan model **LSTM (Long Short-Term Memory)**, **BiLSTM (Bidirectional LSTM)**, dan **LSTM + XGBoost**. Implementasi ini menggunakan data alarm dari berbagai sumber dan mempertimbangkan berbagai metrik evaluasi seperti akurasi, F1-score, dan confusion matrix.

---

## ⚙️ Teknologi yang Digunakan
- Python
- Jupyter Notebook
- Pandas dan NumPy
- Scikit-learn
- TensorFlow/Keras
- XGBoost
- SMOTE (Synthetic Minority Over-sampling Technique)

---

## 🗂️ Dataset
Sebelum menggunakan dataset **Cleaned_Merged_data_alarm.csv**, dilakukan pemrosesan awal pada file **Merged_data_alarm.csv** menggunakan skrip Jupyter Notebook yang terdapat pada file **data_processed.ipynb**. 

Pada tahap pemrosesan ini, dilakukan:
1. **Pembersihan Data**: Menghilangkan data yang tidak diperlukan dan memperbaiki data yang hilang.
2. **Encoding Fitur**: Mengonversi fitur kategorikal menjadi numerik.
3. **Normalisasi Data**: Melakukan normalisasi pada beberapa fitur yang memiliki skala berbeda.
4. **Handling Missing Values**: Menggunakan teknik imputasi pada data yang hilang.
5. **Pembuatan Fitur Baru**: Melakukan rekayasa fitur untuk meningkatkan performa model.

Dataset hasil pemrosesan disimpan dalam file **Cleaned_Merged_data_alarm.csv** yang memiliki fitur-fitur sebagai berikut:
- **alarm_description**: Hasil ubah dari kolom tanpa nama dan sudah dienkode [0-dst]
- **Severity**: Sudah dienkode [0-dst]
- **Alarm ID**: Identifikasi alarm (kolom alarm name dihapus karena sudah direpresentasikan oleh alarm id)
- **Alarm Source**: Sumber alarm (dienkode [0-dst])
- **Location Info**: Lokasi alarm (dienkode [0-dst])
- **Other Information**: Informasi tambahan (dienkode [0-dst])
- **Last Occurred & Acknowledged**: Waktu terakhir terjadi dan diakui (dienkode [0-dst])
- **Fiber/Cable Name**: Nama serat/kabel (dienkode [0-dst])
- **Cleared By & Acknowledged By**: Pihak yang menghapus dan mengakui alarm (dienkode [0-dst])
- **Clearance & Acknowledgement Status**: Status penghapusan dan pengakuan (dienkode [0-dst])
- **Alarm Serial Number**: Nomor seri alarm (dienkode [0-dst])

---

## 🧠 Model dan Arsitektur
Model utama yang digunakan adalah:
1. **LSTM (Long Short-Term Memory)**: 
   - Cocok untuk data time-series dengan banyak fitur.
   - Mampu menangani data urutan panjang dengan menjaga informasi kontekstual.
   - **Akurasi: 92.43%**

2. **BiLSTM (Bidirectional LSTM)**:
   - Memanfaatkan informasi dari kedua arah (forward dan backward).
   - Meningkatkan performa pada beberapa skenario data.
   - **Akurasi: 94.04%**

3. **LSTM + XGBoost**:
   - Menggabungkan kekuatan LSTM dalam menangani data sekuensial dan XGBoost untuk meningkatkan akurasi prediksi.
   - **Akurasi: 94.45%**

---

## 📝 Teknik dan Metodologi
1. **Pra-pemrosesan Data**:
   - Mengolah data awal dari **Merged_data_alarm.csv** menggunakan skrip di **data_processed.ipynb**.
   - Melakukan encoding fitur numerik menggunakan teknik standar [0-dst].
   - Mengatasi ketidakseimbangan kelas dengan **SMOTE**.

2. **Training dan Evaluasi**:
   - Data dibagi menjadi 80% training dan 20% testing.
   - Model dilatih menggunakan beberapa epoch dengan teknik regulasi.
   - Evaluasi menggunakan metrik akurasi, F1-score, dan confusion matrix.

---

## 🚀 Hasil dan Kesimpulan
1. **LSTM**:
   - Menghasilkan akurasi tinggi pada data time-series.
   - Rentan terhadap overfitting jika data tidak cukup banyak atau tidak terstruktur.
   - **Akurasi: 92.43%**

2. **BiLSTM**:
   - Peningkatan akurasi dari model LSTM standar.
   - Lebih baik dalam menangkap pola sekuensial dari dua arah.
   - **Akurasi: 94.04%**

3. **LSTM + XGBoost**:
   - Kombinasi model ini memberikan hasil terbaik dalam prediksi akurasi dan F1-score.
   - **Akurasi: 94.45%**

### 🔥 Kesimpulan Utama
- Metode LSTM cocok untuk data time-series dengan banyak fitur, tetapi model **BiLSTM** dan **LSTM + XGBoost** menunjukkan performa yang lebih baik pada dataset ini.
- Model **LSTM + XGBoost** menghasilkan prediksi yang lebih akurat dibandingkan dengan metode lainnya.

---

## 📝 Catatan
Untuk informasi lebih lanjut, cek dokumentasi dan file hasil percobaan pada folder **Viz** dan file Jupyter Notebook yang sudah disertakan.

---

## 📧 Kontak
Jika ada pertanyaan atau butuh bantuan lebih lanjut, jangan ragu untuk menghubungi kami di [OptixMS GitHub](https://github.com/OptixMS).
