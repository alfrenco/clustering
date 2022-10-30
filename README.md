[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-c66648af7eb3fe8bc4f294546bfd86ef473780cde1dea487d3c4ff354943c9ae.svg)](https://classroom.github.com/online_ide?assignment_repo_id=8617649&assignment_repo_type=AssignmentRepo)

## Dataset

Masuk ke dalam Google BigQuery. Gunakan informasi dibawah ini sebagai tempat untuk mengambil data (gunakan sebagai informasi untuk klausa `FROM`).
   * Project ID : `ftds-hacktiv8-project`
   * Dataset Name : 
     + Batch offline : `phase1_ftds_<nomor-batch>_hck` contoh `phase1_ftds_001_hck`
     + Batch online : `phase1_ftds_<nomor-batch>_rmt` contoh `phase1_ftds_001_rmt`
   * Table Name : `credit-card-information`

Berikut ini adalah informasi dari setiap column. 
   <img src='https://i.ibb.co/2sbf0Js/P1-G4-Dataset-Information.png'>

---


## Objectives

Membuat model clustering untuk melakukan Customer Segmentation dari data kartu kredit sebuah bank. Data ini merupakan data informasi penggunaan kartu kredit selama 6 bulan terakhir. 

---


## Kesimpulan

Dari data di atas saya melakukan clustering menggunakan 3 model yaitu Kmeans, agglomerative clustering dan spectral clustering dimana sebelumnya akan dilakukan dulu pengurangan dimensi(PCA) untuk mempermudah clustering. Dari 17 kolom saya bisa mereduksi menjadi hanya 7 kolom saja menggunakan PCA dan tetap mempertahankan 95% kualitas data.

Saya melakukan clustering menggunakan 3 model clustering dengan jumlah cluster 2 dimana jumlah tersebut diperoleh dari hasil inertia dan silhouette score. Secara sekilas bisa terlihat bahwa hasil clustering antar model cukup baik namun model KMeans memperoleh hasil paling baik diantara 3 model karena secara visual pada model KMeans tidak ada data yang bercampur/bertumpuk dimana hal tersebut terjadi pada 2 model lain.

Hasil Cluster :
1. Cluster 0 : 
> * Data pada cluster ini berjumlah 2452 data atau 54.8% dari keseluruhan data
> * Memiliki rata-rata saldo, rata-rata pembelian, dan rata-rata limit kartu yang lebih rendah dibandingkan cluster 1
2. Cluster 1 : 
> * Data pada cluster ini berjumlah 2023 data atau 45.2% dari keseluruhan data
> * Memiliki rata-rata saldo, rata-rata pembelian, dan rata-rata limit kartu yang lebih tinggi dibandingkan cluster 0

Jadi bisa kita lihat bahwa cluster 1 adalah cluster yang berisi klien yang lebih sering berbelanja dan memiliki lebih banyak uang karena limit dan jumlah saldonya lebih tinggi daripada cluster 0.


