# Laporan Proyek Machine Learning - Meilani Kizana

## Domain Proyek

Bank merupakan sebuah lembaga keuangan sebagai penghimpun uang dari masyarakat dalam bentuk simpanan sekaligus sebagai penyalur kembali dalam bentuk kredit atau pembiayaan lainnya. Adapun churn merupakan suatu kondisi ketika pelanggan memilih untuk berhenti atau keluar dari sebuah layanan. Churn umumnya terjadi ketika pelanggan memilih untuk pindah ke penyedia layanan lainnya karena memberikan penawaran yang lebih menarik ataupun karena ketidakpuasan pada layanan penyedia saat ini (Luong et al, 2025). Selain itu, mendapatkan atau menarik pelanggan baru memerlukan biaya 5 hingga 25 kali lebih besar daripada mempertahankan pelanggan yang telah ada (Shu & Ye, 2023). Oleh karena itu, penting bagi suatu perusahaan termasuk bank untuk dapat mengetahui apa yang menjadi penyebab churn dan cara mengatasinya.

Masalah churn pada bank atau nasabah yang memilih untuk keluar dan berhenti dari suatu bak merupaan masalah yang sangat penting dan harus diatasi oleh bank. Hal ini dikarenakan berdasarkan laporan perbankan global, pengurangan 5% churn pelanggan dapat meningkatkan keuntungan hingga 25% (Gao et al, 2025). Berdasarkan data tersebut, dapat diketahui bahwa tingkat churn memiliki pengaruh yang cukup besar terhadap keuntungan suatu bank. Oleh karena itu, identifikasi nasabah berisiko dan penyebab nasabah melakukan churn menjadi suatu hal yang sangat penting guna mendukung pertumbuhan berkelanjutan di bank. Untuk menangani masalah tersebut, teknologi machine learning dapat diterapkan. Teknologi machine learning saat ini memiliki kemampuan yang ampuh untuk prediksi churn dengan kemampuannya menganalisis kumpulan data nasabah yang besar, berdimensi tinggi, dan dinamis secara efektif (Imani et al, 2025). Dengan memanfaatkan pendekatan machine learning seperti Random Forest, K-Nearest Neighbor, AdaBoost, dan lainnya dapat membantu bank untuk mengidentifikasi dan memprediksi nasabah yang berpotensi melakukan churn serta mengidentifikasi penyebab nasabah melakukan churn. Dengan identifikasi dan prediksi dini, maka bank dapat mengambil langkah pencegahan atau antisipasi untuk dapat mengurangi tingkat churn nasabah.

Berdasarkan riset yang dilakukan oleh Gao et al (2025) dalam memprediksi churn nasabah dengan sentence transformers dan framework stacking ensemble, hasilnya berhasil mengungkapkan beberapa prediktor utama yang menyebabkan churn nasabah seperti perilaku transaksi yang tidak normal, ketidakaktifan nasabah, dan faktor ketidakpuasan. 

Referensi:
 1. Luong, T. T., Luong, V. G., Tran, A. H. T., & Nguyen, T. M. (2025). Application of Machine Learning Techniques for Customer Churn Prediction in the Banking Sector. Interdisciplinary Journal of Information, Knowledge, and Management, 20, 009. Retrieved from https://www.ijikm.org/Volume20/IJIKMv20Art009Luong11309.pdf.
 2. Imani, M., Joudaki, M., Beikmohamadi, A., & Arabnia, H. R. (2025). Customer Churn Prediction: A Review of Recent Advances, Trends, and Challenges in Conventional Machine Learning and Deep Learning. Retrieved from https://www.preprints.org/manuscript/202503.1969/v2.
 3. Gao, J., Wang, H. Y., Lu, Y. L., & Yu, L. N. (2025). Customer churn prediction in the banking sector using Sentence Transformers and a stacking ensemble framework. Acadlore Trans. Mach. Learn, 4(2), 109-123. Retrieved from https://library.acadlore.com/ATAIML/2025/4/2/ATAIML_04.02_04.pdf.
 4. Shu, X., & Ye, Y. (2023). Knowledge Discovery: Methods from data mining and machine learning. Social Science Research, 110, 102817. Retrieved from https://www.sciencedirect.com/science/article/pii/S0049089X22001284.

## Business Understanding
### Problem Statements
- Bagaimana cara mengindentifikasi nasabah bank yang berpotensi melakukan churn atau meninggalkan bank?
- Dari serangkaian fitur yang ada, apa saja fitur yang memiliki pengaruh paling besar atau bertanggung jawab terhadap tingkat churn nasabah bank?

### Goals

- Mengidentifikasi nasabah bank yang berpotensi melakukan churn atau meninggalkan bank seakurat mungkin berdasarkan fitur-fitur yang tersedia
- Mengetahui fitur yang memiliki pengaruh paling besar atau bertanggung jawab terhadap tingkat churn nasabah bank

### Solution Statements
- Memanfaatkan pendekatan machine learning yaitu K-Nearest Neighbor, Random Forest, AdaBoost, dan Logistic Regression untuk melakukan klasifikasi dan identifikasi nasabah yang berpotensi melakukan churn
- Mengevaluasi keempat model tersebut dengan empat metrik evaluasi yaitu akurasim presisi, recall, dan f1 score untuk kemudian memilih model terbaik yang dapat diterapkan untuk menyelesaikan masalah churn berdasarkan hasil evaluasi

## Data Understanding
Data yang digunakan dalam proyek ini merupakan data publik berjudul 'Bank Customer Churn' yang diperoleh dari kaggle. Data ini merupakan data nasabah pemegang rekening pada salah satu Bank Multinasional Anonim. Data ini terdiri dari 10.000 baris data dengan total 18 kolom. Link dataset: [Bank Customer Churn](https://www.kaggle.com/datasets/radheshyamkollipara/bank-customer-churn).

### Variabel-variabel pada Bank Customer Churn dataset adalah sebagai berikut:
- RowNumber: nomor baris data
- CustomerId: nilai acak sebagai identitas nasabah
- Surname: nama belakang nasabah
- CreditScore: skor kredit nasabah
- Geography: lokasi negara nasabah
- Gender: jenis kelamin nasabah
- Age: usia nasabah
- Tenure: berapa lama nasabah telah menjadi nasabah bank (dalam tahun)
- Balance: saldo nasabah
- NumOfProducts: jumlah produk yang dibeli nasabah melalui bank
- HasCrCard: apakah nasabah memiliki kartu kredit atau tidak (0: nasabah tidak memiliki kartu kredit, 1: nasabah memiliki kartu kredit)
- IsActiveMember: apakah nasabah aktif atau tidak (0: nasabah tidak aktif, 1: nasabah aktif)
- EstimatedSalary: perkiraan gaji nasabah
- Exited: apakah nasabah meninggalkan bank (churn) atau tidak (0: nasabah tidak meninggalkan bank, 1: nasabah meninggalkan bank)
- Complain: apakah nasabah memiliki komplain/keluhan atau tidak (0: nasabah tidak memiliki komplain, 1: nasabah memiliki komplain)
- Satisfaction Score: skor kepuasan pelanggan terhadap penyelesaian komplain/keluhan yang diajukan
- Card Type: tipe kartu yang dimiliki oleh nasabah
- Points Earned: total poin yang diperoleh nasabah dari hasil penggunaan kartu kredit

### Exploratory Data Analysis (EDA)
1. Mengecek informasi pada dataset dengan fungsi `info()`:
   - Terdapat 2 kolom bertipe float64 atau float yaitu 'Balance' dan 'EstimatedSalary'
   - Terdapat 12 kolom bertipe int64 atau integer yaitu 'RowNumber', 'CustomerId', 'CreditScore', 'Age', 'Tenure', 'NumOfProducts', 'HasCrCard', 'IsActiveMember', 'Exited', 'Complain', 'Satisfaction Score', dan 'Point Earned'
   - Terdapat 4 kolom bertipe object yaitu 'Surname', 'Geography', 'Gender', dan 'Card Type'
   - Semua kolom terdiri dari jumlah data yang sama yaitu 10.000

2. Mengecek deskripsi statistik dengan fungsi `describe()`:
   - Dari hasil yang diperoleh, dapat diketahui bahwa tidak ada nilai yang tidak sesuai dengan logika bisnis. Semua nilai berada dalam rentang yang sesuai dan masuk akal dengan logika bisnis.

3. Mendeteksi nilai null dengan `isnull().sum()`:
   - Tidak terdapat nilai null di setiap kolom dalam dataset

4. Mendeteksi data duplikat dengan `duplicated().sum()`:
   - Tidak terdapat data duplikat dalam dataset

5. Univariate Analysis

   a. Kolom Kategorikal
   
    ![Categorical Features Univariate Analysis](https://i.ibb.co/C3ynV4vG/categorical-features-univariate-analysis.png)
   - Nasabah bank yang didata berasal dari 3 negara yaitu sekitar 50% dari Prancis serta masing-masing 25% dari Spanyol dan German.
   - Perbandingan nasabah perempuan dan laki-laki cukup seimbang, dengan lebih kurang 4.500 nasabah perempuan dan lebih kurang 5.500 nasabah laki-laki.
   - Sekitar 70% nasabah memiliki kartu kredit, sedangkan sisanya tidak memiliki kartu kredit. Hal ini berarti data yang dimiliki didominasi oleh nasabah yang memiliki kartu kredit.
   - Perbandingan nasabah aktif dengan nasabah tidak aktif hampir seimbang.
   - Perbandingan nasabah yang meninggalkan bank berada di perbandingan 80:20. Dengan 80% tidak meninggalkan bank dan 20% meninggalkan bank.
   - Perbandingan nasabah yang melakukan komplain berada di perbandingan 80:20. Dengan 80% tidak tidak memiliki komplain, dan 20% memiliki komplain.
   - Adapun jumlah skor kepuasan pengguna untuk penyelesaian keluhan atau komplain mereka tersebar cukup merata dari skor 1 hingga 5.
   - Tipe kartu terbagi menjadi 4 jenis yaitu Diamond, Silver, Gold, dan Platinum. Adapun yng terdapat pada data ini tersebar cukup merata pada keempat tipe kartu tersebut.


   b. Kolom Numerikal
   
    ![Numerical Features Univariate Analysis](https://i.ibb.co.com/0yMN9hV7/numerical-features-univariate-analysis.png)
   - Nilai CreditScore sebagian besar berada antara 550 hingga 750. Terdapat outlier dengan skor sangat rendah di bawah 400. Distribusi bersifat mendekati normal dengan sedikit skew ke kiri.
   - Usia nasabah berkisar dari 18 hingga lebih dari 90 tahun, yang cenderung terpusat pada rentang usia 30–40 tahun. Adapun usia nasabah yang lebih dari 60 tahun terdeteksi sebagai outlier. Namun hal ini dibiarkan karena usia tersebut masih masuk akal sebagai nasabah sebuah bank.
   - Lama menjadi nasabah cukup terdistribusi secara merata antara 0 hingga 10 tahun, hal ini menunjukkan bahwa tidak ada durasi tertentu yang dominan bagi nasabah.
   - Saldo nasabah tersebar cukup beragam, dengan saldo 0 yang mendominasi, kemudian sisanya terdistribusi pada saldo 5.000 hingga 20.000, serta terdapat juga nasabah dengan saldo hingga 25.000. Hal ini menunjukkan bahwa mayoritas nasabah memiliki saldo kecil atau 0, dilihat dari persebarannya yang cenderung ke kiri.
   - Sebagian besar nasabah membeli 1 atau 2 produk. Adapun nasabah yang membeli 3 hingga 4 produk, namun jumlah nasabah yang membeli 4 produk relatif sedikit sehingga terdeteksi sebagai outlier. Namun hal ini masih normal dan masuk akal sehingga dapat dibiarkan.
   - Estimasi gaji nasabah tersebar merata dari 0 hingga 200.000. Distribusi ini tampak seragam tanpa adanya outlier.
   - Poin yang diperoleh nasabah tersebar cukup merata antara 100 hingga 1000, dengan konsentrasi di sekitar nilai 600.
   
7. Multivariate Analysis
   
    a. Korelasi antar Fitur Numerik
   
    ![Numerical Features Pairplot](https://i.ibb.co/prv9JnT6/numerical-features-pairplot.png)

   Dari hasil analisis hubungan antar fitur numerikal diatas, dapat diketahui bahwa tidak terdapat hubungan yang linear atau cukup signifikan antar dua fitur terhadap nasabah yang meninggalkan bank atau tidak. Hal ini menunjukkan bahwa fitur-fitur memiliki hubungan yang cukup kompleks atau non-linear.

    b. Matriks Korelasi
   
    ![Correlation Matrix](https://i.ibb.co/HTVfxRBL/correlation-matrix.png)

   Heatmap diatas digunakan untuk mencari hubungan atau tingkat korelasi antar fitur-fitur numerikal. Hal yang perlu diperhatikan adalah hubungan antar fitur yang memiliki korelasi positif terutama terhadap fitur yang akan menjadi target yaitu 'Exited'. Hasil menunjukkan bahwa fitur yang memiliki korelasi positif mulai dari yang paling tinggi tingkat korelasinya adalah fitur 'Complain', fitur 'Age', fitur 'Balance', dan fitur 'EstimatedSalary'. Adapun untuk fitur 'Complain' memiliki korelasi yang sangat tinggi, artinya hampir setiap nasabah yang melakukan komplain, memilih untuk meninggalkan bank. Begitupun sebaliknya, dimana nasabah yang tidak melakukan komplain, mayoritas akan tetap di bank.

    c. Korelasi Fitur Kategorikal dengan Fitur Target
   
    ![Categorical Features and Churn Correlation](https://i.ibb.co/5xwh3CSt/categorical-features-and-churn-correlation.png)

   Grafik diatas digunakan untuk mengetahui bagaimana hubungan antara fitur kategorikal dengan fitur target 'Exited' dengan cara melihat perbandingan nasabah yang memilih meninggalkan bank dengan nasabah yang tetap di bank. Dari hasil tersebut menunjukkan penyebaran yang cukup seragam antara pengguna melakukan churn atau meninggalkan bank. Namun pada fitur 'Complain', tingkat nasabah yang meninggalkan bank sangat tinggi pada pelanggan yang memiliki komplain. Hal ini menunjukkan hampir semua nasabah yang memiliki komplain, memilih untuk meninggalkan bank. Sedangkan untuk negara, German perlu diperhatikan karena memiliki tingkat churn yang cukup tinggi dibandingkan dengan 2 negara lainnya.

## Data Preparation
Teknik data preparation yang saya terapkan yaitu:
1. Encoding Fitur Kategorikal

   Proses ini digunakan untuk melakukan one hot encoding pada fitur kategorikal yang belum dilakukan encoding yaitu fitur 'Geography', 'Gender', dan 'Card Type'. Tahap ini berfungsi untuk mengubah fitur kategorikal menjadi numerikal agar dapat digunakan sebagai input dalam model.
   
2. Seleksi Fitur

    Proses ini digunakan untuk menghapus (drop) kolom yang tidak penting atau tidak lagi diperlukan. Kolom 'RowNumber', 'CustomerId', dan 'Surname' dihapus karena tidak memberikan insight apapun terhadap proses klasifikasi dan hanya merupakan kolom identitas. Sedangkan kolom 'Geography', 'Gender', dan 'Card Type' dihapus karena telah dilakukan one hot encoding yang menghasilkan kolom baru yang bertipe numerikal, sehingga kolom ini harus dihapuskan agar tidak terjadi duplikasi.
   
3. Memisahkan Kolom Fitur dan Kolom Target dan Membagi Dataset menjadi Data Latih dan Data Uji
   
    Proses ini digunakan untuk memisahkan kolom fitur dengan kolom target serta membagi data menjadi 2 yaitu data pelatihan dan data uji. Target pada klasifikasi ini adalah kolom 'Exited' sehingga kolom tersebut dipisahkan dan disimpan dalam variabel y, sedangkan kolom lainnya disimpan dalam variabel X. Adapun pembagian data pelatihan dan data uji yanng digunakan disini adalah 80% data pelatihan dan 20% data uji. Pembagian tersebut merupakan pembagian yang umum digunakan, sehingga diterapkan pada proyek ini.
   
4. Standardisasi Fitur Numerikal
   
    Proses ini digunakan untuk melakukan standardisasi terhadap fitur-fitur numerikal yang akan digunakan dalam pembangunan model. Standardisasi yang digunakan adalah StandardScaler yang mengubah nilai numerik ke rentang -1 hingga 1. Tahap ini perlu dilakukan agar perbedaan rentang angka dalam fitur numerik tidak memengaruhi pelatihan model.


## Modeling
Pada tahapan ini dilakukan pembangunan model dengan algoritma yang dipilih untuk menyelesaikan permasalahan yang telah diidentifikasi sebelumnya. Pada proyek ini, saya menggunakan 3 algoritma untuk klasifikasi yaitu K-Nearest Neighbor, Random Forest, dan Logistic Regression. Berikut ini adalah penjelasan lebih lanjut mengenai algoritma yang digunakan:
1. K-Nearest Neighbor (KNN)
   
    Algoritma pertama yang saya gunakan adalah KNN. Adapun parameter yang digunakan adalah `n_neighbor=10` yang berarti menggunakan 10 data tetangga terdekatnya untuk menentukan kelasnya. Berikut ini adalah kelebihan dan kekurangan dari algoritma KNN:
   
    a. Kelebihan
   - Sederhana dan mudah untuk digunakan
   - Mampu mengidentifikasi pola non-linear
  
    b. Kekurangan
   - Kurang cocok untuk data dengan ukuran fitur atau dimensi yang besar
   - Memerlukan waktu yang relatif lama ketika melakukan prediksi pada data berukuran besar
   
2. Random Forest
   
    Algoritma kedua yang saya gunakan adalah Random Forest. Adapun parameter yang digunakan adalah `n_estimators=25` yang berarti jumlah pohon yang dibangun adalah 25, `max_depth=3` yang berarti kedalaman maksimum setiap pohon adalah 3, `random_state=55` untuk mengontrol seed pembangkitan angka acak, dan `n_jobs=-1` untuk memerintahkan penggunaan semua CPU yang tersedia untuk mendukung proses paralel. Berikut ini adalah kelebihan dan kekurangan dari algoritma Random Forest:
   
    a. Kelebihan
   - Mampu menangani dataset dengan kelas yang tidak seimbang dan mengatasi overfitting terhadap data pelatihan
   - Mampu mengidentifikasi pola non-linear dan data yang kompleks
   
    b. Kekurangan
   - Cenderung sulit untuk diinterpretasikan bagaimana cara pengambilan keputusannya
   - Model relatif lebih berat dan membutuhkan sumber daya yang cukup besar
   
3. Logistic Regression
   
    Algoritma ketiga yang saya gunakan adalah Logistic Regression. Adapun untuk parameternya menggunakan default dari `LogisticRegression()`. Berikut ini adalah kelebihan dan kekurangan dari algoritma Logistic Regression:
   
    a. Kelebihan
   - Proses pelatihan cenderung cepat dan efisien
   - Mudah untuk diinterpretasikan
   
    b. Kekurangan
   - Kurang cocok untuk data dengan fitur yang memiliki hubungan non-linear
   - Rentan terjadi underfitting pada dataset dengan kelas yang tidak seimbang

Dari ketiga model yang telah dibangun dan dilakukan evaluasi berdasarkan 4 metrik yaitu akurasi, presisi, recall, f1 score. Hasilnya menunjukkan bahwa model dengan algoritma Random Forest memiliki performa yang paling baik di keempat metrik tersebut. **Oleh karena itu, model dengan algoritma Random Forest dipilih sebagai solusi (model terbaik).** Selain karena unggul dalam keempat metrik evaluasi, model ini juga memiliki kelebihan yang cocok untuk penyelesaiian kasus ini yaitu mampu menangani data dengan kelas yang tidak seimbang dan mampu mengidentifikasi pola non-linear. Hal ini sesuai dengan data yang digunakan dalam proyek ini dimana perbandingan data kelas didominasi oleh nasabah yang tidak melakukan churn dan tidak terdapat pola linear antar fitur dalam data ini seperti yang telah ditampilkan pada tahapan EDA. 

## Evaluation
Metrik evaluasi yang digunakan dalam proyek ini adalah akurasi, presisi, recall, dan f1 score. Keempat metrik ini digunakan untuk evaluasi karena proyek ini merupakan proyek klasifikasi sehingga metrik tersebut digunakan. Selain keempat metrik tersebut, saya juga menggunakan confusion matrix sebagai visualisasi bagaimana hasil prediksi oleh model yang menunjukkan jumlah prediksi yang benar dan salah. Berikut ini adalah penjelasan dari setiap metrik tersebut:
1. Akurasi
   
Akurasi adalah metrik yang menghitung jumlah prediksi benar terhadap total seluruh prediksi yang dilakukan oleh model. 
Formula:
![Formula Akurasi](https://assets.cdn.dicoding.com/original/academy/dos-701b28b93cb6ba8c3e9d6b9c8c1bae9920241015153232.jpeg)

Dengan:
   - TP (True Positives): model benar memprediksi hasil yang benar dengan tepat.
   - TN (True Negatives): model benar memprediksi hasil yang salah dengan tepat.
   - FP (False Positives): model salah memprediksi hasil yang salah sebagai benar atau hasil yang salah sebagai benar.
   - FN (False Negatives): model salah memprediksi hasil yang benar sebagai salah.


2. Presisi

Presisi adalah metrik yang menghitung jumlah prediksi positif yang benar terhadap total seluruh prediksi positif yang dilakukan oleh model. Metrik ini digunakan untuk mengukur seberapa baik model menghindari positif palsu (FP).
Formula:
![Formula Presisi](https://assets.cdn.dicoding.com/original/academy/dos-fc5f282672f1b572c4cd9a0e747dec5e20241015153231.jpeg)

Dengan:
   - TP (True Positives): model benar memprediksi hasil yang benar dengan tepat.
   - FP (False Positives): model salah memprediksi hasil yang salah sebagai benar atau hasil yang salah sebagai benar.


3. Recall

Recall adalah metrik yang menghitung jumlah prediksi positif yang benar terhadap total seluruh prediksi positif yang sebenarnya ada dalam data. Metrik ini digunakan untuk mengukur seberapa baik model menangkap semua kasus positif.
Formula:
![Formula Recall](https://assets.cdn.dicoding.com/original/academy/dos-d17ca76e6a72ddc98ed5c803561cf20820241015153231.jpeg)
Dengan:
   - TP (True Positives): model benar memprediksi hasil yang benar dengan tepat.
   - FN (False Negatives): model salah memprediksi hasil yang benar sebagai salah.


4. F1 Score

F1 Score adalah metrik yang menghitung rata-rata harmonis dari presisi dan recall. F1 Score biasanya mampu menggambarkan performa model secara lebih akurat ketika model memiliki nilai presisi dan recall yang tidak seimbang. 
Formula:
![Formula F1 Score](https://assets.cdn.dicoding.com/original/academy/dos-0ab2c6bcc31494e4c1cc70008ae9a31620241015153232.jpeg)


**Adapun hasil evaluasi model berdasarkan metrik evaluasi tersebut adalah sebagai berikut:**
| No | Model               | Accuracy | Precision | Recall | F1-Score |
|----|---------------------|----------|-----------|--------|----------|
| 1  | K-Nearest Neighbor  | 0.6975   | 0.698948  | 0.6975 | 0.698220 |
| 2  | Random Forest       | 0.9990   | 0.999000  | 0.9990 | 0.999000 |
| 3  | Logistic Regression | 0.4910   | 0.726871  | 0.4910 | 0.537187 |

Dari hasil evaluasi diatas, dapat diketahui beberapa hal berikut:
- Random Forest menunjukkan performa terbaik di keempat metrik evaluasi. Hal ini menunjukkan bahwa Random Forest cocok untuk digunakan dalam kasus ini.
- K-Nearest Neighbor atau KNN memiliki performa rata-rata 69% di keempat metrik. Hal ini menunjukkan performa yang cukup baik namun masih kurang kuat untuk digunakan dalam kasus ini.
- Logistic Regression memiliki performa yang paling rendah jika dibandingkan dengan algoritma lainnya. Hal ini menunjukkan bahwa algoritma ini tidak cocok untuk digunakan dalam kasus ini. Walaupun nilai presisi cukup tinggi, namun nilai pada akurasi, recall, dan f1 score cenderung rendah.

## Kesimpulan Akhir
Setelah melakukan tahapan-tahapan diatas, maka dapat diambil kesimpulan bahwa model yang cocok digunakan untuk melakukan klasifikasi nasabah bank yang melakukan churn atau tidak adalah model yang menggunakan algoritma Random Forest. Selain itu, untuk menjawab problem statement dan goals yang telah diidentifikasi di awal. Berikut ini adalah beberapa hal yang dapat disimpulkan:

- Nasabah bank yang berpontensi melakukan churn atau meninggalkan bank dapat diidentifikasi dengan penerapan model machine learning Random Forest. Model ini terpilih sebagai model terbaik berdasarkan evaluasi performanya dengan empat metrik evaluasi yang diterapkan. Dengan menerapkan model machine learning ini, bank akan dapat mengidentifikasi nasabah bank lebih dini sehingga dapat mengatur strategi lebih lanjut untuk penanganan maupun pencegahan terjadinya churn.
- Proyek ini juga menjawab problem statement kedua mengenai identifikasi fitur yang memiliki pengaruh paling besar terhadap tingkat churn nasabah. Fitur-fitur tersebut berhasil diidentifikasi pada tahapan EDA yaitu pada tahapan visualisasi korelasi antar fitur terhadap fitur target ('Exited'). Adapun fitur-fitur yang memiliki pengaruh paling besar terhadap tingkat churn nasabah bank adalah fitur 'Complain', fitur 'Age', fitur 'Balance', dan fitur 'EstimatedSalary'
