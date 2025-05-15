# Rakamin - Internship Study Case
## Study case explanation

Sebagai seorang Data Analyst PT Sejahtera Bersama, saya ditugaskan untuk memberi usulan dengan tujuan mempertahankan penjualan ataupun menaikkan penjualan. Beberapa tahap yang perlu dikerjakan sebagai berikut:
- Menentukan primary key setiap dataset: Customer, Products, Orders, dan ProductCategory.
- Menentukan relationship antar dataset
- Membuat table master berisi: CustomerEmail (cust_email), CustomerCity (cust_city), OrderDate (order_date), OrderQty (order_qty), ProductName (product_name), ProductPrice (product_price), ProductCategoryName (category_name), TotalSales (total_sales)
- Membuat visualisasi yang menampilkan data penjualan tersebut dengan beberapa poin sebagai berikut:
    - Total keseluruhan sales
    - Total keseluruhan sales berdasarkan kategori produk
    - Total keseluruhan qty berdasarkan kategori produk
    - Total sales berdasarkan kota
    - Total qty berdasarkan kota
    - Top 5 kategori produk yang paling tinggi salesnya
    - Top 5 kategori produk yang paling tinggi qtynya
- Menyampaikan rekomendasi

## Hasil pengerjaan
### Primary key dan relationship datasets
![image](https://github.com/user-attachments/assets/7f47fbfa-f110-465e-aace-1986785c0b14)
### Table master
Big Query - SQL Query
```
    SELECT date, categoryname, prodname, price, quantity, (price*quantity) as totalsales, customeremail, customercity
    FROM `rakamin_project.Orders` as O
    LEFT JOIN `rakamin_project.Customers`as C
    USING(CustomerID)
    LEFT JOIN `rakamin_project.Products` as P
    USING(ProdNumber)
    LEFT JOIN `rakamin_project.ProductCategory`as PC
    ON P.Category = PC.CategoryID
```

Link to dataset: ...
### Visualisasi
![image](https://github.com/user-attachments/assets/bf0d63c8-4fa1-4ef4-a88a-c22c45b3c720)

Presentation Report: https://lookerstudio.google.com/s/lkkSwTtiO8c

Berdasarkan data penjualan tahun 2020–2021, PT Sejahtera Bersama berhasil meraih total penjualan sebesar 1,8 juta dolar dengan jumlah produk terjual sebanyak 11,8 ribu unit. Kategori robots menjadi penyumbang penjualan terbesar dengan nilai sebesar 743,5 ribu dolar (sekitar 41,3% dari total penjualan), diikuti oleh drones dengan 477,4 ribu dolar (sekitar 26,5%), sementara kategori lainnya seperti robot and drone kits serta training videos menyumbang angka yang lebih kecil. Hal ini menunjukkan bahwa penjualan didominasi oleh produk-produk teknologi canggih, yang mengindikasikan adanya pergeseran minat pelanggan ke arah solusi bisnis yang lebih efisien dan efektif, meskipun membutuhkan investasi awal yang besar.

Di sisi lain, jika dilihat dari jumlah unit yang terjual, produk ebooks menjadi yang paling banyak dibeli, yaitu sebesar 3,1 ribu unit (sekitar 26,3% dari total), disusul oleh training videos sebanyak 2,1 ribu unit (sekitar 17,8%), lalu blueprints, serta drone and kits. Hal ini mencerminkan bahwa produk digital seperti buku dan video daring lebih diminati karena sifatnya yang fleksibel, mudah diakses, dan berbiaya lebih rendah dibandingkan versi fisiknya. 

Dari sisi lokasi, kota-kota dengan kontribusi penjualan terbesar—yakni lebih dari 25 ribu dolar—adalah Washington, San Diego, Houston, Sacramento, Springfield, dan Albany. Seluruh kota ini berada di wilayah Amerika Serikat, yang menunjukkan bahwa pasar utama PT Sejahtera Bersama masih kuat di kawasan tersebut dan memiliki potensi untuk terus dikembangkan.

### Recommendation
- **Kembangkan Paket Produk Digital Bertema Teknologi (Ebooks & Training Videos)**
Melihat tingginya jumlah unit terjual untuk ebooks dan training videos, perusahaan dapat membuat paket bundling bertema teknologi seperti “Robot Mastery Kit” atau “Drone Business Starter Pack” yang mencakup ebook, video, dan blueprints sekaligus. Hal ini akan meningkatkan nilai produk, mendorong pembelian lebih besar per transaksi, dan tetap menjaga daya tarik harga bagi pelanggan yang sensitif terhadap biaya.
- **Fokus Pemasaran Terarah di Kota-Kota High-Spending**
Kota-kota seperti Washington, San Diego, Houston, Sacramento, Springfield, dan Albany telah terbukti menghasilkan >$25.000 dalam penjualan. Perusahaan bisa melakukan kampanye pemasaran digital yang lebih agresif dan terlokalisasi di kota-kota ini—misalnya dengan iklan berbasis lokasi, webinar eksklusif, atau penawaran khusus untuk pelanggan lama—untuk mempertahankan dan meningkatkan pangsa pasar di wilayah yang sudah terbukti potensial.



