# Supervised-Learning-Classification
Project Supervised Learning dengan tujuan memprediksi Customer churn atau tidak berdasarkan dataset dari perusahaan telekomunikasi. Dataset : https://drive.google.com/file/d/1IX_RSFp8QbZmULWTvAKZcNWsv3sKiQ6t/view?usp=sharing

# Overviews
Goals : Memprediksi customers akan churn atau tidak berdasarkan fitur-fitur pada dataset yang dipilih <br>
Business Impact : Untuk menentukan strategy mengurangi tingkat churn customer

# Exploratory Data Analysis
- Deskripsi Statistik data numerical dan kategorical
- Univariate Analysis : Boxplot, KDE Plot, Countplot 
- Multivariate Analysis : Heatmap

# Data Preprocessing
- Handling missing value dan duplikat: Imputasi nilai 0 pada kolom null
- Feature Engineering : MonthlyToTotalRatio, tenure_group
- Feature Selection : Metode SelectKBest
- Encode : One Hot Encode, Label Encode
- Scalling dan transform data : Metode StandardScaler

# Training & Evaluasi Model
- Data Splitting : Data Train (80%) dan Data Test (20%)
- Handling Imbalance : Metode SMOTE
- Baseline Model : RandomForestClassifier
- Model Evaluated : XGBClassifier, KNeighborsClassifier

# Hyperparameter Turning
- Approach : RandomizedSearchCV (KNeighborsClassifier, XGBClassifier,RandomForestClassifier)
- Scoring Metrics: Recall, Precision, F1-Score, ROC-AUC

# Kesimpulan Final Model
Berdasarkan analisis dari masing-masing model, ditentukan model terbaik XG Boost Karena F1-score sama dengan Random Forest (0.65), tapi akurasinya lebih tinggi, precision lebih baik, dan hasil cross-validation kuat. Recall penting, karena kita ingin menangkap sebanyak mungkin pelanggan yang akan pergi, namun bukan satu-satunya metrik penting. Model yang terlalu fokus pada recall saja bisa menghasilkan banyak false positive. False positive artinya kita salah menarget pelanggan setia seolah mereka akan churn akan menebabkan buang-buang resources (diskon, campaign) yang merugikan perusahaan. Maka dari itu model XG boost lebih baik.

# Rekomendasi Bisnis
- Rekomendasi Bisnis dari feature importance: <br>
Berdasarkan analisis feature importance dari model prediksi customer churn, ditemukan bahwa pelanggan dengan kontrak bulanan, tidak menggunakan layanan seperti Tech Support dan Online Security, serta menggunakan metode pembayaran manual seperti electronic check memiliki risiko churn yang lebih tinggi. Hal ini menunjukkan bahwa fleksibilitas kontrak dan kurangnya engagement terhadap layanan tambahan menjadi faktor utama pelanggan berhenti. Selain itu, pelanggan pengguna layanan Fiber Optic dan Paperless Billing juga menunjukkan kecenderungan churn, yang mungkin disebabkan oleh ekspektasi tinggi terhadap kualitas layanan atau ketidakjelasan informasi tagihan.
Untuk mengurangi churn, perusahaan disarankan untuk menawarkan insentif bagi pelanggan kontrak bulanan agar beralih ke kontrak jangka panjang, serta mengedukasi dan mendorong penggunaan layanan tambahan seperti keamanan dan dukungan teknis. Selain itu, metode pembayaran otomatis dan transparansi dalam sistem penagihan dapat meningkatkan loyalitas pelanggan. Upaya ini akan membantu meningkatkan kepuasan pelanggan dan mempertahankan basis pelanggan yang ada secara lebih efektif.

- Rekomendasi bisnis berdasarkan SHAP summary plot:<br>
Fokus retensi harus diarahkan pada pelanggan baru, dengan kontrak bulanan, dan yang tidak menggunakan fitur tambahan seperti keamanan online (Online Security) dan dukungan teknis (Tech support). Perusahaan dapat menawarkan insentif untuk kontrak tahunan, edukasi manfaat dari layanan tambahan, serta promo khusus untuk pelanggan dengan tagihan bulanan tinggi. Segmentasi pelanggan berdasarkan tenure dan jenis layanan bisa menjadi strategi proaktif untuk mencegah churn lebih awal.
