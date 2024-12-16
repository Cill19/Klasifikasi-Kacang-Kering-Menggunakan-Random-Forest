# Klasifikasi Kacang Kering Menggunakan Random Forest

Proyek ini bertujuan untuk mengklasifikasikan tujuh jenis kacang kering berdasarkan fitur visual seperti bentuk dan dimensi yang diekstraksi dari gambar. Algoritma **Random Forest** digunakan untuk membangun model machine learning yang mampu mengklasifikasikan jenis kacang dengan akurasi tinggi.

---

## 📊 Dataset

Dataset yang digunakan adalah **Dry Bean Dataset** dari UCI Repository, yang terdiri dari:

- **Jumlah Data**: 13.611 sampel kacang kering
- **Jumlah Fitur**: 16 fitur (dimensi dan bentuk)
- **Target**: 7 kelas kacang
  - **Kelas**: Seker, Barbunya, Bombay, Cali, Dermosan, Horoz, Sira

## 🔄 Data Preprocessing dan Eksplorasi Data

### Preprocessing
- **Label Encoding**: Menggunakan `LabelEncoder` untuk mengubah label target menjadi numerik.
- **Pembagian Data**: Dataset dibagi menjadi 80% data pelatihan dan 20% data pengujian dengan stratifikasi untuk menjaga distribusi kelas.

### Eksplorasi Data
- **Distribusi Kelas**: Visualisasi distribusi kelas untuk memahami ketidakseimbangan data.
- **Korelasi Fitur**: Menggunakan heatmap untuk menunjukkan hubungan antar fitur yang berbeda.

## 🔍 Metode: Random Forest

### Model Dasar (Baseline)
- **Random Forest** digunakan dengan parameter default untuk mendapatkan model dasar.
  
### Hyperparameter Tuning
- Tuning dilakukan menggunakan **GridSearchCV** untuk menemukan parameter terbaik:
  - **n_estimators**: 100, 200, 300
  - **max_depth**: 10, 20, None
  - **max_features**: sqrt, log2, None

## 📈 Hasil dan Analisis

### Model Baseline
- **Akurasi**: 92.18%
- **Confusion Matrix**:
  - Kelas **Dermason** memiliki akurasi prediksi tertinggi (653 prediksi benar).
  - Kelas **Sira** menunjukkan kesalahan signifikan, banyak sampel salah diklasifikasikan.

### Model Terbaik (Setelah Tuning)
- **Parameter Terbaik**: `n_estimators=100`, `max_depth=20`, `max_features=None`
- **Akurasi**: 91.63%
- **Analisis**:
  - Kelas **Bombay** menunjukkan akurasi sempurna (tanpa kesalahan).
  - Kelas **Sira** masih menunjukkan kesalahan yang relatif tinggi, terutama diprediksi sebagai **Dermason**.

### Feature Importance
- **Fitur yang Paling Berpengaruh**:
  - **Area**
  - **Perimeter**
  - **MajorAxisLength**

## 🧑‍💻 Kesimpulan
Model Random Forest berhasil mengklasifikasikan jenis kacang kering dengan akurasi **91.63%** setelah dilakukan tuning parameter. Fitur seperti **Area** dan **Perimeter** terbukti memainkan peran penting dalam klasifikasi. Meskipun demikian, **ketidakseimbangan kelas** (seperti pada kelas **Sira**) masih memengaruhi hasil prediksi.

Untuk penelitian lebih lanjut, disarankan untuk menggunakan teknik **balancing data** seperti **SMOTE** untuk meningkatkan akurasi pada kelas minoritas.

## 📊 Visualisasi

1. **Distribusi Kelas**:  
   Grafik batang yang menunjukkan distribusi sampel per kelas.
   
2. **Confusion Matrix**:  
   Perbandingan antara prediksi dan aktual untuk model baseline dan model terbaik.
   
3. **Feature Importance**:  
   Diagram batang yang menunjukkan fitur-fitur paling berpengaruh dalam klasifikasi.

