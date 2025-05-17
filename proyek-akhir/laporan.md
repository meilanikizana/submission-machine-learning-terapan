# Laporan Proyek Machine Learning - Meilani Kizana

## Project Overview

Industri film merupakan industri yang sangat besar saat ini, tidak hanya di Indonesia namun di seluruh dunia. Sejak tahun 2000, tercatat sekitar 4500 film atau setara dengan 9000 jam video dirilis setiap tahunnya di seluruh dunia (Zhang et al, 2020). Pesatnya pertumbuhan film ini diseimbangi oleh semakin meningkatnya jumlah penonton film. Menurut Fajriansyah, Adikara, dan Widodo (2021), jumlah penonton film di Indonesia terus meningkat dari tahun ke tahun. Sejak tahun 2018, jumlah penonton film bioskop mencapai 50 juta penonton dengan total hampir 200 film produksi dalam dan luar negeri yang telah tayang. Selain film yang dirilis di bioskop, budaya menonton film saat ini juga banyak bergeser ke platform streaming seperti Netflix, Disney+, Prime Video, dan masih banyak lainnya. Menurut Arfisko dan Wibowo (2022), acara TV dan film yang disediakan oleh masing-masing platform jumlahnya sangat banyak, salah satu contohnya yaitu berkisaran 6000 item pada Netflix. Adapun sistem rekomendasi merupakan suatu sistem yang dibangun untuk memprediksi atau mengumpulkan data minat pengguna dan memberikan rekomendasi item yang kemungkinan besar menarik bagi pengguna (Pradeep et al, 2020). Sistem rekomendasi juga dapat diterapkan untuk film atau dapat disebut sebagai sistem rekomendasi film yang bertujuan untuk merekomendasikan film kepada pengguna dengan menganalisis preferensi pengguna, riwayat tontonan, dan informasi terkait lainnya (Kaushik et al, 2025).

Dari sisi pengguna atau penonton, banyaknya pilihan film membuat pengguna atau penonton merasa kesulitan saat memilih film. Seringkali juga penonton menghabiskan cukup banyak waktu hanya untuk memilih film yang akan ditonton (Fajriansyah, Adikara, dan Widodo, 2021). Setelah menghabiskan banyak waktu, belum tentu film yang terpilih cocok dengan apa yang disukai oleh pengguna sehingga waktu yang dihabiskan untuk memilih film menjadi percuma. Disinilah peran sistem rekomendasi film diperlukan untuk menyelesaikan masalah ini. Dengan adanya sistem rekomendasi film, pengguna atau penonton akan lebih mudah dalam memilih film sehingga dapat lebih efisien dalam waktu dan energi. Sedangkan dari sisi bisnis, sistem rekomendasi dapat meningkatkan waktu aktivitas pengguna di dalam suatu platform dengan cara menampilkan item-item relevan kepada pengguna, yang mana nantinya seiring waktu dapat meningkatkan pendapatan untuk platform itu sendiri (Arfisko dan Wibowo, 2022). Dengan menampilkan item-item yang dipersonalisasi, setiap pengguna akan merasa lebih nyaman ketika menggunakan platform streaming tersebut. Pendekatan sistem rekomendasi film yang dapat diterapkan untuk merekomendasikan film bagi pengguna terbagi menjadi dua yaitu content based filtering dan collaborative filtering. Pendekatan pertama akan menggunakan riwayat film pengguna dan menganalisis genre untuk kemudian memberikan rekomendasi film dengan genre serupa. Adapun pendekatan collaborative akan menggunakan data rating yang diberikan oleh pengguna untuk kemudian menemukan genre-genre film yang disukai oleh pengguna dan merekomendasikan film serupa.

Berdasarkan riset yang dilakukan oleh Kaushik et al (2025) dalam membangun sistem rekomendasi yang dipersonalisasi berdasarkan pengalaman pengguna, hasilnya menunjukkan bahwa pendekatan hibrida (KNN dengan content based dan collaborative filtering) secara signifikan meningkatkan akurasi rekomendasi film, serta meningkatkan kepuasan dan engagement pengguna pada platform digital.

Referensi:
1. Fajriansyah, M., Adikara, P. P., & Widodo, A. W. (2021). Sistem Rekomendasi Film Menggunakan Content Based Filtering. Jurnal Pengembangan Teknologi Informasi dan Ilmu Komputer, 5(6), 2188-2199. Retrieved from https://j-ptiik.ub.ac.id/index.php/j-ptiik/article/view/9163/4159.
2. Arfisko, H. H., & Wibowo, A. T. (2022). Sistem Rekomendasi Film Menggunakan Metode Hybrid Collaborative Filtering Dan Content-Based Filtering. eProceedings of Engineering, 9(3). Retrieved from https://openlibrarypublications.telkomuniversity.ac.id/index.php/engineering/article/view/18066.
3. Zhang, J., Wang, Y., Yuan, Z., & Jin, Q. (2019). Personalized real-time movie recommendation system: Practical prototype and evaluation. Tsinghua Science and Technology, 25(2), 180-191. Retrieved from https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8821512.
4. Pradeep, N. K. K. R., Rao Mangalore, K. K., Rajpal, B., Prasad, N., & Shastri, R. (2020). Content based movie recommendation system. International journal of research in industrial engineering, 9(4), 337-348. Retrieved from https://www.riejournal.com/article_121501_a3717e6cf19a1845e350acb9148751ee.pdf.
5. Kaushik, M., Gupta, M., & Kashyap, V. (2025). PERSONALIZED MOVIE RECOMMENDATION SYSTEMS: ADVANCING USER-CENTRIC EXPERIENCES. PERSONALIZED MOVIE RECOMMENDATION SYSTEMS: ADVANCING USER-CENTRIC EXPERIENCES (April 8, 2025). Retrieved from https://papers.ssrn.com/sol3/Delivery.cfm?abstractid=5209133.

## Business Understanding
### Problem Statements

- Bagaimana cara memberikan rekomendasi film kepada pengguna sesuai dengan genre yang disukai oleh pengguna atau sesuai dengan film yang pernah ditonton pengguna?
- Bagaimana cara memberikan rekomendasi film kepada pengguna sesuai dengan preferensi masing-masing pengguna?

### Goals

- Memberikan 5 rekomendasi film yang sesuai dengan genre yang disukai oleh pengguna atau yang sesuai dengan film yang pernah ditonton pengguna dengan memanfaatkan pendekatan content based filtering recommendation system
- Memberikan 10 rekomendasi film yang sesuai dengan preferensi masing-masing pengguna dengan memanfaatkan pendekatan collaborative filtering recommendation system

### Solution Statements

- Memanfaatkan pendekatan content based filtering untuk membangun sistem rekomendasi yang dapat memberikan rekomendasi berdasarkan genre yang serupa
- Memanfaatkan pendekatan collaborative filtering untuk membangun sistem rekomendasi yang dapat menganalisis riwayat rating film masing-masing pengguna dan memberikan rekomendasi film yang sesuai dengan preferensi pengguna

## Data Understanding
Dataset yang digunakan dalam proyek ini merupakan dataset development berjudul 'Movie Lens Small Latest Dataset' yang diperoleh dari kaggle. Dataset ini merupakan data yang berisi rating dan tag dari pengguna dan diperoleh dari MovieLens, sebuah layanan rekomendasi film. Dataset ini terdiri dari data 610 pengguna antara 29 Maret 1996 hingga 24 September 2018. Dataset ini terdiri dari 5 file, 1 file README dan 4 file data csv. Pada proyek ini, file yang digunakan hanya 2 yaitu file movies.csv dan ratings.csv. Link dataset: [Movie Lens Small Latest Dataset](https://www.kaggle.com/datasets/shubhammehta21/movie-lens-small-latest-dataset).

### Variabel-variabel pada Movie Lens Small Latest Dataset adalah sebagai berikut:
1. links.csv

    File ini berisikan tentang id film dengan id IMDB dan id TMDB untuk memudahkan koneksi dengan sumber data lain, terdiri dari variabel-variabel berikut:
    - movieId: id film yang digunakan pada dataset ini
    - imdbId: id film pada Internet Movie Dataset
    - tmdbId: id film pada The Movie Dataset

2. movies.csv

    File ini berisikan data tentang informasi film, terdiri dari variabel-variabel berikut:
    - movieId: id film yang digunakan pada dataset ini
    - title: judul film
    - genres: kombinasi genre film

3. ratings.csv

    File ini berisikan data tentang informasi rating film oleh pengguna, terdiri dari variabel-variabel berikut:
    - userId: id pengguna
    - movieId: id film yang digunakan pada dataset ini
    - rating: penilaian bintang (rating) yang diberikan oleh pengguna
    - timestamp: waktu ketika pengguna memberikan penilaian

4. tags.csv
   
    File ini berisikan data tentang informasi tag film oleh pengguna, terdiri dari variabel-variabel berikut:
    - userId: id pengguna
    - movieId: id film yang digunakan pada dataset ini
    - tag: 1-3 kata sesuai film yang diberikan oleh pengguna
    - timestamp: waktu ketika pengguna memberikan tag

### Univariate Exploratory Data Analysis
1. Mengecek informasi pada links.csv dengan fungsi `info()`:
    - Terdapat 2 kolom bertipe int64 atau integer yaitu 'movieId' dan 'imdbID'
    - Terdapat 1 kolom bertipe float64 atau float yaitu 'tmdbId'
    - Semua kolom terdiri dari jumlah data yang sama yaitu 9.742

2. Mengecek informasi pada movies.csv dengan fungsi `info()`:
    - Terdapat 1 kolom bertipe int64 atau integer yaitu 'movieId'
    - Terdapat 2 kolom bertipe object yaitu 'title' dan 'genres'
    - Semua kolom terdiri dari jumlah data yang sama yaitu 9.742

3. Mengecek jumlah film dan genre pada movies.csv:
    - Jumlah film yang terdapat dalam movies adalah 9708 dan kombinasi genrenya 950 
    - Genre setiap film terdiri dari kombinasi beberapa genre, bukan hanya satu genre

4. Mengecek informasi pada ratings.csv dengan fungsi `info()`:
    - Terdapat 3 kolom bertipe int64 atau integer yaitu 'userId', movieId', dan 'timestamp'
    - Terdapat 1 kolom bertipe float64 atau float yaitu 'rating'
    - Semua kolom terdiri dari jumlah data yang sama yaitu 100.836 

5. Mengecek deskripsi statistik pada ratings.csv dengan fungsi `describe()`:
   - Dari hasil yang diperoleh, dapat diketahui bahwa tidak ada nilai yang tidak sesuai dengan logika bisnis. Semua nilai berada dalam rentang yang sesuai dan masuk akal dengan logika bisnis
   - Rentang rating adalah 0-5, dengan rating paling kecil yang diberikan oleh pengguna adalah 0.5 dan paling besar yaitu 5

6. Mengecek jumlah pengguna dan film yang dirating pada ratings.csv:
    - Jumlah pengguna yang memberikan rating adalah 610
    - Jumlah film yang diberikan rating adalah 9724
    - Dengan total seluruh data adalah 100836

7. Mengecek informasi pada tags.csv dengan fungsi `info()`:
    - Terdapat 3 kolom bertipe int64 atau integer yaitu 'userId', movieId', dan 'timestamp'
    - Terdapat 1 kolom bertipe object yaitu 'tag'
    - Semua kolom terdiri dari jumlah data yang sama yaitu 3.683

8. Mengecek nilai kosong dengan fungsi `isnull().sum()`:

    Pengecekan nilai kosong dilakukan hanya pada movies dan ratings karena kedua data ini yang akan digunakan, sedangkan links dan tags tidak dilakukan pengecekan nilai kosong karena tidak akan digunakan pada proyek ini.
   - Tidak terdapat nilai null di setiap kolom dalam data movies maupun data ratings
   
9. Mengecek data duplikat dengan fungsi `duplicated().sum()`:

    Pengecekan data duplikat dilakukan hanya pada movies dan ratings karena kedua data ini yang akan digunakan, sedangkan links dan tags tidak dilakukan pengecekan data duplikat karena tidak akan digunakan pada proyek ini.
   - Tidak terdapat data duplikat dalam data movies maupun data ratings

### Visualisasi Data
1. Distribusi Genre Film

    ![Bar Chart Distribusi Genre Film](https://i.ibb.co/kgLJxkKh/download.png)

   Barchart diatas digunakan untuk menampilkan visualisasi dari distribusi genre dalam data. Dari hasilnya dapat diketahui bahwa genre drama dan comedy cukup mendominasi jumlahnya. Selain itu, terdapat (no genres listed) dalam visualiasi diatas. Hal ini menunjukkan terdapat film yang belum diberikan genre. Hal ini akan ditangani pada tahapan persiapan data.

2. Distribusi Rating Film

    ![Bar Chart Distribusi Rating Film](https://i.ibb.co/m5b1qJNb/download-1.png)

   Barchart diatas digunakan untuk menampilkan visualisasi dari distribusi rating film dalam data. Dari hasilnya dapat diketahui bahwa rating 3.0 dan 4.0 cukup mendominasi jumlahnya. Adapun rating 0.5 dan 1.5 memiliki jumlah yang paling sedikit. Selain itu, dapat diketahui pula interval rating adalah 0.5.

## Data Preparation
Proyek ini akan membangun sistem rekomendasi dengan content based filtering dan collaborative filtering, sehingga persiapan data juga dipisahkan berdasarkan dua metode pendekatan tersebut.
1. Content Based Filtering Data Preparation
   
    a. Mengatasi Nilai Genre '(no genres listed)'

    Setelah dilakukan visuliasasi di tahap sebelumnya, ditemukan genre '(no genres listed)' yang artinya film belum memiliki genre. Maka pada tahap ini, data yang belum memiliki genre atau berisikan nilai '(no genres listed)' akan dihapus karena tidak memberikan informasi yang berarti dan dapat mengganggu performa sistem rekomendasi apabila tidak dihapus. Setelah dihapus, dilakukan pengecekan kembali dengan visualiasi untuk memastikan penanganan sudah benar dan berhasil.

    b. TF-IDF Vectorizer dan Cosine Similarity

    Tahapan ini digunakan untuk mengubah teks genre menjadi representasi numerik dan menghitung derajat kesamaan antar film. Tahapan ini merupakan tahap yang penting untuk membangun sistem rekomendasi berbasis konten. Teks genre diidentifikasi dan diubah ke dalam bentuk numerik agar dapat dihitung derajat kesamaannya menggunakan cosine similarity. Berikut ini adalah tahapan-tahapan yang dilakukan: 
    - Identifikasi Genre Film: mengubah data teks (genre) menjadi representasi numerik (TF-IDF matrix)
    - Fit dan Transform ke Bentuk Matriks: hasil ukuran matriks (9708, 21) yang artinya terdapat 9708 film dan 21 jenis genre
    - Mengubah Vektor TF-IDF dalam Bentuk Matriks: menggunakan fungsi todense()
    - Menampilkan Matriks TF-IDF untuk Beberapa Film terhadap Genre
    - Menghitung Derajat Kesamaan: menggunakan cosine_similarity dan menghasilkan array matriks kesamaan antar film
    - Menampilkan Matriks Kesamaan antar Film


3. Collaborative Filtering Data Preparation

    a. Encoding dan Mapping

    Tahap encode/menyandikan fitur 'userId' dan 'movieId' ke dalam indeks integer. Tahap ini diterapkan untuk menyandikan id ke dalam integer berurutan untuk mempermudah interpretasi hasil rekomendasi. Setelah tahapan encode, dilakukan mapping untuk memetakan hasil encode kedua id tersebut ke dalam dataframe 'ratings'.

    b. Mengecek dan Menyimpan Beberapa Informasi ke Variabel

    Tahap ini digunakan untuk mengecek beberapa hal mengenai data 'ratings' seperti jumlah data pengguna (610 pengguna), jumlah data film (9724 film), serta nilai rating terendah (0.5) dan tertinggi (5.0). Informasi-informasi tersebut kemudian disimpan dalam sebuah variabel yang nantinya akan digunakan dalam sistem rekomendasi. 
    
    c. Memisahkan Kolom Fitur dan Kolom Target serta Membagi Data Training dan Data Validasi

    Tahap diatas merupakan tahap untuk membuat variabel X dan variabel Y dan kemudian membagi dataset menjadi data pelatihan dan data validasi. Variabel X sebagai input yaitu 'user' dan 'movie' yang berisikan id yang telah di encode sebelumnya. Sedangkan variabel Y sebagai target yaitu 'rating' yang dinormalisasi dengan rumus min-max scaling. Adapun pembagian data pelatihan dan data validasi yang digunakan disini adalah 80% data pelatihan dan 20% data validasi. Pembagian tersebut merupakan pembagian yang umum digunakan, sehingga diterapkan pada proyek ini.

## Modeling
Pada tahapan ini dilakukan pembangunan sistem rekomendasi dengan 2 pendekatan untuk menyelesaikan permasalahan yang telah diidentifikasi sebelumnya. Pada proyek ini, saya menggunakan 2 pendekatan untuk sistem rekomendasi yaitu Content-Based Filtering dan Collaborative Filtering. Berikut ini adalah penjelasan lebih lanjut mengenai kedua pendekatan tersebut:
1. Content Based Filtering

    Pada tahap ini dilakukan pembuatan fungsi movie_recommendations dengan menggunakan beberapa parameter yaitu:
    - judul: judul film (index kemiripan dataset)
    - similarity_data: dataframe mengenai similarity/kesamaan yang telah didefinisikan sebelumnya menggunakan cosine
    - items: nama dan fitur yang digunakan untuk mendefinisikan kemiripan yaitu judul film dan genrenya
    - k: banyak rekomendasi yang diberikan adalah 5

    Fungsi ini akan berguna sebagai pemberi rekomendasi film dimana fungsi tersebut akan mengembalikan 5 film yang memiliki tingkat kemiripan genre tertinggi dengan film yang dipilih.
    
    Berikut ini adalah rekomendasi film yang dihasilkan oleh sistem rekomendasi untuk film 'Pixel Perfect (2004)' yang bergenre 'Children|Comedy|Sci-Fi':
    |    | Title                                | Genres                            |
    |----|--------------------------------------|-----------------------------------|
    | 0  | Honey, I Blew Up the Kid (1992)      | Children\|Comedy\|Sci-Fi          |
    | 1  | Cat from Outer Space, The (1978)     | Children\|Comedy\|Sci-Fi          |
    | 2  | Return from Witch Mountain (1978)    | Children\|Sci-Fi                  |
    | 3  | Black Hole, The (1979)               | Children\|Sci-Fi                  |
    | 4  | RocketMan (a.k.a. Rocket Man) (1997) | Children\|Comedy\|Romance\|Sci-Fi |

   Hasilnya menunjukkan 5 film lainnya yang memiliki genre serupa yaitu sekitaran Children, Comedy, dan Sci-Fi.
    
    Berikut ini adalah kelebihan dan kekurangan dari pendekatan content based filtering:

   a. Kelebihan
    - Dapat memberikan rekomendasi film yang sesuai dengan genre yang pernah ditonton oleh pengguna
    - Tidak membutuhkan informasi dari pengguna lainnya, cukup hanya menggunakan informasi tentang genre film

    b. Kekurangan
    - Rekomendasi yang terbatas pada genre tertentu (kurang bervariasi) karena berbasis kesamaan genre sehingga sulit untuk melakukan rekomendasi film dengan genre yang belum pernah ditonton oleh pengguna
    - Kurang dipersonalisasi karena tidak memmpertimbangkan penilaian pengguna terhadap film-film
    
3. Collaborative Filtering

    Pada tahap ini dilakukan pembuatan kelas RecommenderNet dengan keras Model class. Model menghitung skor kecocokan antara pengguna dan film dengan teknik embedding. Tahapannya yaitu:
    - Embedding Data Pengguna dan Data Film
    - Menambahkan Bias untuk Setiap Pengguna dan Film
    - Operasi Perkalian Dot Product antara Embedding User dan Film
    - Fungsi Aktivasi Sigmoid untuk Menentukan Skor Kecocokan dalam Skala [0, 1]

    Model ini akan menghasilkan output berupa top 10 rekomendasi film yang sesuai dengan preferensi pengguna dilihat dari riwayat ratingnya. Sebagai contoh untuk pengguna dengan id 599 dan 5 film dengan rating tertinggi sebagai berikut:
    - Rumble in the Bronx (Hont faan kui) (1995) : Action|Adventure|Comedy|Crime
    - 2001: A Space Odyssey (1968) : Adventure|Drama|Sci-Fi
    - His Girl Friday (1940) : Comedy|Romance 
    - Road Warrior, The (Mad Max 2) (1981) : Action|Adventure|Sci-Fi|Thriller
    - Lost in Translation (2003) : Comedy|Drama|Romance

    Berikut ini adalah rekomendasi film yang dihasilkan oleh sistem rekomendasi untuk pengguna dengan id 599 tersebut:
    - Secrets & Lies (1996) : Drama
    - Once Upon a Time in the West (C'era una volta il West) (1968) : Action|Drama|Western
    - Ran (1985) : Drama|War
    - Bridge on the River Kwai, The (1957) : Adventure|Drama|War
    - Patton (1970) : Drama|War
    - Night on Earth (1991) : Comedy|Drama
    - Guess Who's Coming to Dinner (1967) : Drama
    - Trial, The (Procès, Le) (1962) : Drama
    - Adam's Rib (1949) : Comedy|Romance
    - Three Billboards Outside Ebbing, Missouri (2017) : Crime|Drama
    
    Film dengan rating tertinggi yang diberikan oleh pengguna berkisar pada genre Action, Adventure, Comedy, Crime, Drama, Sci-Fi, Romance, dan Thiller. Hasil rekomendasi film yang diberikan untuk pengguna cukup selaras dengan film yang dirating tinggi oleh pengguna yaitu berkisar pada genre Drama, Comedy, Adventure, dan Crime. Namun juga tidak terbatas pada genre-genre tersebut.

    Berikut ini adalah kelebihan dan kekurangan dari pendekatan collaborative filtering:

   a. Kelebihan
    - Dapat memberikan rekomendasi film yang lebih beragam dalam hal genre namun tetap sesuai dengan preferensi pengguna
    - Lebih personal karena sistem mempelajari preferensi pengguna dan mampu menangkap preferensi yang kompleks sehingga hasil rekomendasi film akan lebih terpersonalisasi

    b. Kekurangan
    - Membutuhkan informasi pengguna dan rating yang cukup banyak agar dapat belajar dengan lebih baik
    - Hasil rekomendasi film agak sulit untuk diberikan penjelasan alasannya

## Evaluation
Metrik evaluasi yang digunakan dalam proyek ini adalah precision untuk content based filtering dan root mean squared error (RMSE) untuk collaborative filtering. Kedua metrik ini digunakan untuk evaluasi karena proyek ini merupakan proyek sistem rekomendasi yang menggunakan dua pendekatan berbeda sehingga diperlukan metrik menyesuaikan masing-masing pendekatan. Selain kedua metrik tersebut, saya juga menggunakan plot sebagai visualisasi nilai RMSE selama training. Berikut ini adalah penjelasan dari setiap metrik tersebut:

1. Presisi untuk Content Based Filtering

    Presisi dalam sistem rekomendasi adalah metrik yang menghitung jumlah item rekomendasi yang relevan terhadap seluruh item yang direkomendasikan. Formula:
   
    ![Precision Metrics](https://miro.medium.com/v2/resize:fit:1400/0*66v_CbuEE0gtjuCK)

    Dilihat dari hasil rekomendasi sebelumnya yang dihasilkan oleh pendekatan content based filtering. 5 film rekomendasi yang diberikan memiliki genre yang relevan dengan genre film acuan yaitu Children, Comedy, dan Sci-Fi. Kelima film rekomendasi juga memiliki genre-genre tersebut sehingga presisinya adalah: `P = 5/5 = 1` atau `100%`.

2. Root Mean Squared Error (RMSE) untuk Collaborative Filtering

    RMSE adalah metrik yang menghitung akar kuadrat dari nilai rata-rata dari kuadrat kesalahan antara nilai sebenarnya dan nilai prediksi. Formula:
   
    ![RMSE Metrics](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT9m2pvtQbmk6LgivjtafZPCN2mYvdXf9iLrRzcnr1dIjX9803p)

    Dengan:
    
   - n: jumlah sampel
   - $y_i$: nilai sebenarnya
   - $\hat{y}_i$: nilai prediksi

    Pelatihan model menggunakan ukuran batch yaitu 8 dan 20 epoch. Nilai RMSE pada data latih adalah '0.1887' dan pada data validasi adalah '0.2019'. Hal ini menunjukkan bahwa model sudah cukup baik dan tidak mengalami overfitting pada data latih. Penurunan nilai RMSE dari epoch awal hingga akhir juga menandakan proses training yang cukup smooth. Berikut ini adalah visualisasinya:

    ![RMSE Metrics Visualization](https://i.ibb.co/Qv7rFhcx/visualisasi-rmse-metrik.png)
    
## Kesimpulan Akhir
Setelah melakukan seluruh tahapan diatas, maka dapat diambil kesimpulan bahwa sistem rekomendasi telah berhasil memberikan rekomendasi film yang relevan menggunakan 2 jenis pendekatan yaitu content based filtering dan collaborative filtering. Selain itu, untuk menjawab problem statement dan goals yang telah diidentifikasi di awal. Berikut ini adalah beberapa hal yang dapat disimpulkan:
- Sistem rekomendasi dengan pendekatan content based filtering yang berfokus pada genre film berhasil memberikan 5 rekomendasi film yang sesuai dengan genre yang disukai oleh pengguna dan sesuai dengan film yang pernah ditonton oleh pengguna. Hasil evaluasi menunjukkan performa yang sangat baik yaitu tingkat presisi 1 atau 100%.
- Sistem rekomendasi dengan pendekatan collaborative filtering yang berfokus pada riwayat rating pengguna berhasil memberikan 10 rekomendasi film yang sesuai dengan preferensi masing-masing pengguna. Hasil evaluasi menunjukkan performa yang cukup baik untuk sistem rekomendasi yaitu nilai RMSE sebesar 0,2019 pada data validasi.

Kedua pendekatan yang diterapkan pada sistem rekomendasi ini memiliki kelebihan dan kekurangannya masing-masing. Secara umum, kedua pendekatan ini memiliki performa yang cukup baik dan dapat menjadi solusi dari masalah yang telah diidentifikasikan di awal, baik dari sisi pengguna maupun dari sisi bisnis.
