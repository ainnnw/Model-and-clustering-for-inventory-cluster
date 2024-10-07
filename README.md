# -Model-and-clustering-for-inventory-cluster-

* <h1>Business Problem</h1>
Perusahaan A merupakan perusahaan yang bergerak di bidang e-commerce yang berfokus sebagai penyedia platform belanja online dengan menghadirkan produk retail kepada pelanggan. Ada berbagai macam kategori produk yang ditawarkan diantaranya pakaian, skincare, peralatan olahraga, aksesoris, dan sebagainya. Berdasarkan history penjualan, diperoleh hasil yang menunjukkan banyaknya peminat dari masing-masing produk yang ditawarkan sehingga perlu di kaji apakah masih diminati atau tidak produk tersebut serta bagaimana rencana promosi yang efektif untuk meningkatkan penjualan tiap produk Perusahaan A

* <h1>Goal</h1>
Tujuan dari project ini adalah menemukan rencana promosi yang efektif terhadap product yang dijual lalu menjaga stok product agar tetap tersedia dengan melihat pola penjualan dan forecasting tiap product.

* <h1>Solusi yang ditawarkan </h1>
1.  mengidentifikasi tren penjualan produk berdasarkan keadaan aktual dan prediksi kedepannya dengan mengukur hasil prediksi menggunkan MAE.<br>
2.  mengelompokan setiap produk ke dalam cluster, yang bertujuan untuk memahami karakteristik product dalam transaksi.<br>
3.  menyusun strategi pemasaran yang efektif untuk penjualan produk, meningkatkan produk yang penjualannya di bawah rata-rata quantity global dilihat dari transaksi bulan sebelumnya.<br>

# Cluster
metode Cluster digungakan untuk mengklompokan produk berdasarkan riwayat transaksi agar dapat melihat tren tren penjualan dari setiap product. <br>
metode yang digunakan adalah elbow method.

![Logo Proyek](https://github.com/ainnnw/-Model-and-clustering-for-inventory-cluster-/blob/main/Asset/elbow.PNG)<br>
Dari metode ini didapatkan 5 cluster dengan presepsi profile cluster :<br>
Cluster 0 = Top 3 Quantity by cluster, Item price slightly below average of item price global, total amount below average of total amount global, Shipment fee low price, Domination product season spring, good freq recency top 2.<br>
Cluster 1 = Very low quantity, item price, and total amount, normaly shipment fee, domination product season summer, bad freq recency.<br>
Cluster 2 = Great quantity, total amount, and recency, high item price and shipment fee, domination product season summer.<br>
Cluster 3 = Top 2 quantity by cluster, item price and total amount above average of item price global, normaly shipment fee, domination product season winter, good freq recency top 3.<br>
Cluster 4 = Bad quantity, total amount, and recency, low item price and shipment fee, domination product season fall.<br>

# Forcasting
forcasting menggunkan metode multt forcasting dengan cara membanding 2 model XGB dan Prophet. untuk mengetahui performa model diukur menggunakan <br>
r2_score || mean absolute error || median absolute error || Mean Squared Error || Root Mean Squared Error 
![forcasting result](https://github.com/user-attachments/assets/bb9f1e9f-e5b8-4dd2-9454-4e363744fddc)


# Dashboard
Pembuatan dashbord menggunkan microsoft power BI 
![halaman over](https://github.com/ainnnw/-Model-and-clustering-for-inventory-cluster-/blob/main/Asset/Team%20Proteus_Dashboard-1.png)
![halaman cluster](https://github.com/ainnnw/-Model-and-clustering-for-inventory-cluster-/blob/main/Asset/Team%20Proteus_Dashboard-2.png)
![halaman forcas](https://github.com/ainnnw/-Model-and-clustering-for-inventory-cluster-/blob/main/Asset/Team%20Proteus_Dashboard-3.png)

# insight<br>
<br>Forecasting dilakukan selama 6 bulan kedepan dimulai dari Agustus 2022 - Januari 2023, dimana pada bulan periode ini di Indonesia mengalami peralihan musim dari kemarau ke musim penghujan
<br>Hasil forecasting dengan metode prophet, memperoleh hasil prediksi mengalami peningkatan frekuensi quantity sebesar 0,8333% dari periode sebelumnya
<br>Hasil forecasting dengan metode XGBoost, memperoleh hasil prediksi mengalami penurunan frekuensi quantity sebesar −7,0167% dari periode sebelumnya
<br>Semakin banyak kode promo yang disediakan, maka semakin banyak quantity penjualannya
<br>61 % atau 739.692 transaksi dari global transaksi belum menggunakan code-promo. 
<br>Push quantity, dilihat dari hasil forecasting prohet cluster 2 memiliki frekuensi quantity paling sedikit, sedangkan cluster 2 memiliki profiling great quantity and recence, higt total amount. Dilihat dari hasil forecastig XGBoost mengalami penurunan yang cukup signifikan pada quantity, untuk meningkatkan quantity dipilih product pada cluster 0 dan 3 karena masih memiliki harapan dilihat dari recency dan frekuensi quantity

# recomendation<br>
## persediaan barang
Prediksi quantity yang bisa dijual seperti hasil forecasting  maka  perlu menyiapkan stok barangnya juga, kecuali cluster yang masuk ke dalam starategi pemasaran untuk di tingkatkan frekuensinya
## rencana promosi global 
<br>Menambah kuantitas promo yang sudah ada sebelumnya
<br>Minimal payment 100k up to 10% cashback
<br>Voucher disc up to 15% + cashback 5% use Credit Card dengan min. payment 200.005
<br>Free ongkir 
## rencana promosi cluster up to quantity
<br>up to stok  sama dengan rata-rata quantity bulan sebelumnya, kemudian menerapkan opsi promo:
<br>Flash sale 
<br>Diskon Up to 50 % untuk pembelian lebih dari 1
<br>Penggunaan voucher diskon  up to 20%
<br>Iklan media sosial

  





