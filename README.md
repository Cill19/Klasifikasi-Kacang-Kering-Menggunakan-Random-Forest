# Klasifikasi-Kacang-Kering-Menggunakan-Random-Forest
Dalam proyek ini, 7 jenis kacang kering diklasifikasikan berdasarkan fitur visual seperti bentuk dan dimensi yang diekstraksi dari gambar. Tujuan penelitian ini adalah membangun model machine learning yang mampu mengklasifikasikan jenis kacang dengan akurasi tinggi menggunakan algoritma Random Forest.

1. Dataset
Dataset Dry Bean dari UCI Repository digunakan, yang terdiri dari:

Jumlah Data: 13.611 sampel kacang kering
Jumlah Fitur: 16 fitur (dimensi dan bentuk)
Target: 7 kelas kacang (Seker, Barbunya, Bombay, Cali, Dermosan, Horoz, Sira)
2. Data Preprocessing dan Eksplorasi Data
Preprocessing:
Encoding label target menggunakan LabelEncoder
Pembagian dataset menjadi 80% data pelatihan dan 20% data pengujian
Stratifikasi dilakukan untuk menjaga distribusi kelas.
Eksplorasi Data:
Distribusi kelas divisualisasikan untuk menunjukkan ketidakseimbangan data.
Korelasi antar fitur divisualisasikan menggunakan heatmap untuk memahami hubungan antar variabel.
3. Metode: Random Forest
Baseline Model: Random Forest dengan parameter default.
Hyperparameter Tuning: Dilakukan menggunakan GridSearchCV untuk mencari parameter terbaik:
n_estimators: 100, 200, 300
max_depth: 10, 20, None
max_features: sqrt, log2, None


Hasil dan Analisis
1. Model Baseline
Akurasi: 92.18%
Hasil Confusion Matrix:
Kelas Dermason memiliki prediksi paling akurat (653 prediksi benar).
Kelas Sira menunjukkan kesalahan signifikan, dengan beberapa sampel salah diklasifikasikan.
2. Model Terbaik (Setelah Tuning)
Parameter Terbaik:
n_estimators=100, max_depth=20, max_features=None
Akurasi Model Terbaik: 91.63%
Analisis Hasil:
Kelas Bombay memiliki akurasi sempurna (tanpa kesalahan).
Kelas Sira masih menunjukkan kesalahan yang relatif tinggi, terutama diprediksi sebagai kelas Dermason.
Feature Importance:
Fitur Area, Perimeter, dan MajorAxisLength memiliki kontribusi terbesar dalam klasifikasi.
Kesimpulan
Model Random Forest berhasil mengklasifikasikan jenis kacang kering dengan akurasi mencapai 91.63% setelah dilakukan tuning parameter. Fitur dimensi seperti Area dan Perimeter memainkan peran penting dalam prediksi. Meskipun model memiliki performa yang baik, ketidakseimbangan kelas (seperti pada kelas Sira) masih memengaruhi hasil prediksi. Penelitian lanjutan dapat menggunakan teknik balancing data seperti SMOTE untuk meningkatkan akurasi pada kelas minoritas.

Visualisasi Tambahan
Distribusi Kelas: Grafik batang distribusi sampel per kelas.
Confusion Matrix: Perbandingan prediksi dan aktual untuk model baseline dan model terbaik.
Feature Importance: Diagram batang fitur-fitur paling berpengaruh.
Tampilan Sederhana (Layout Poster):
Header: Judul Proyek & Identitas (Nama/NIM/Instansi)
Pendahuluan (Kiri Atas)
Metodologi (Tengah Atas)
Hasil dan Analisis (Tengah Bawah)
Kesimpulan (Kanan Bawah)
Visualisasi: Diagram Confusion Matrix, Distribusi Kelas, dan Feature Importance
