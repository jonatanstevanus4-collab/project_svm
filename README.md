# project_svm
PROJECT MACHINE LEARNING – Support Vector Machine (SVM)
Dataset berisi rekaman data mahasiswa yang digunakan untuk memprediksi status kelulusan mereka (Lulus Tepat Waktu atau Lulus Terlambat) berdasarkan kombinasi faktor akademik dan demografi.
Langkah-Langkah dan cara menjalankan notebook:
-upload file csv di folder google drive
-buka google collab dan connect ke google drive
-Setup & Data Loading	
1. Import Libraries: Import pandas, numpy, sklearn, matplotlib, seaborn. 
2. Mount Drive: Hubungkan Google Colab ke Google Drive (from google.colab import drive). 
3. Load Data: Baca file CSV dari path Drive Anda. 
4. Inspeksi Awal: Bersihkan nama kolom, tampilkan df.head(), df.info(), dan periksa df.isnull().sum() untuk mengidentifikasi missing values.
-Exploratory Data Analysis (EDA)
1. Statistik Deskriptif: Hitung df.describe() untuk fitur numerik. 
2. Analisis Missing Values: Tentukan strategi penanganan (Imputasi Median direkomendasikan untuk IPK dan IPS 8). 
3. Visualisasi Kunci: Buat Histogram IPK dan Countplot Status Kelulusan. 
4. Analisis Komparatif: Buat Violin Plot atau Box Plot IPK vs STATUS KELULUSAN untuk melihat perbedaan distribusi.
-Data Preprocessing
1. Imputasi: Terapkan Imputasi Median pada missing values. 
2. Encoding Target: Gunakan Label Encoding pada STATUS KELULUSAN (misalnya TEPAT=0, TERLAMBAT=1). 
3. Feature Engineering: Definisikan kolom Numerik (IPS, IPK, UMUR) dan Kategorikal (JK, Status Mahasiswa, Status Nikah). 
4. Column Transformer: Gunakan ColumnTransformer untuk menerapkan StandardScaler pada kolom Numerik dan OneHotEncoder pada kolom Kategorikal secara bersamaan. 5. Split Data: Lakukan train_test_split (disarankan 80:20) dengan stratify pada label target.
-Model Training (SVM & Tuning)
1. Definisikan Grid: Siapkan parameter grid untuk GridSearchCV yang mencakup: a. kernel='linear' dengan $C=\{0.1, 1, 10\}$. b. kernel='rbf' dengan $C=\{0.1, 1, 10\}$ dan $\gamma=\{\text{'scale'}, 0.1, 1\}$. 
2. Grid Search: Latih model SVC menggunakan GridSearchCV dengan $cv=5$ untuk menemukan kombinasi hyperparameter terbaik (baik untuk Linear maupun RBF). 3. Simpan Model: Simpan best_model dan preprocessor menggunakan pickle.
-Evaluasi & Interpretasi
1. Prediksi: Lakukan prediksi pada data uji (X_test) menggunakan best_model. 
2. Metrik: Hitung dan tampilkan Confusion Matrix, Classification Report (Precision, Recall, F1-score), dan Accuracy Score. 
3. Analisis: Bandingkan performa model Linear dan RBF. Jelaskan pengaruh parameter $C$. Interpretasikan fitur dominan (misalnya IPK) terhadap kelulusan.
-Deployment
1. Fungsi Prediksi: Buat fungsi Python sederhana (predict_status(umur, ipk, ips, ...) ) yang menerima input mentah, menerapkan preprocessor yang sudah dilatih, dan memberikan prediksi status kelulusan.
<img width="846" height="547" alt="hasil2" src="https://github.com/user-attachments/assets/c2c83b11-3ecc-4635-bab8-834ce60945f0" />
<img width="695" height="547" alt="hasil" src="https://github.com/user-attachments/assets/2aaea469-581f-4809-a4db-01f6e0c32406" />

Mahasiswa Universitas Darwan Ali (UNDA)
Nama: Jonathan Stevanus THE
NPM:  2457201002387
