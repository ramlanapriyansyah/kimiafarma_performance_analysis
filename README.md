## Overview
Proyek ini berfokus pada pembuatan dashboard kinerja PT Kimia Farma periode tahun 2020-2023 dengan tujuan untuk menganalisis data penjualan di berbagai wilayah dan periode waktu tersebut. </br> Dashboard ini bertujuan untuk memberikan wawasan tentang tren penjualan, profit, volume transaksi, dan kinerja regional dari waktu ke waktu.

## Tools yang Digunakan
- **BigQuery**: Manipulasi dan ekstraksi data.
- **Google Looker Studio**: Visualisasi Data.

## Data
Data yang digunakan berasal dari table master kimiafarma.analytic yang merupakan hasil ekstraksi dari beberapa dataset yang tersedia yaitu final_transaction, inventory, kantor_cabang, product, dan rating. </br>
Query lengkap proses ekstraksi dapat dilihat pada file `Data_Extraction.sql`

## Komponen Dashboard
Setelah table master dibuat, langkah selanjutnya yaitu memvisualisasikan hasil analisis melalui dashboard kinerja (performance dashboard). 
Secara garis besar, dashboard kinerja mencakup komponen-komponen sebagai berikut:
1. **Sales and Profit Overview**: Menampilkan total penjualan/pendapatan, total profit, dan total transaksi per tahun.
2. **Kinerja Cabang**: Menampilkan kinerja penjualan di berbagai wilayah menggunakan tabel dan peta.
3. **Analisis Perbandingan**: Menampilkan perbandingan penjualan dari waktu ke waktu.

<img width="900" alt="image" src="https://github.com/ramlanapriyansyah/kimiafarma_performance_analysis/assets/135192484/04d73fec-647b-4ae8-a6c1-deef6994551e">


Dashboard lengkap: https://lookerstudio.google.com/reporting/0bbeacfb-72ae-4209-8cfb-02877892aa04

## Temuan
1. Total pendapatan yang diperoleh PT Kimia Farma dalam periode 2020-2023 yaitu sebesar Rp 321,2 miliar; dengan total profit sebesar Rp 91,2 miliar. Atau dengan kata lain margin profit yang diperoleh PT Kimia Farma dalam periode waktu tersebut adalah sebesar 28,4%.
2. Total transaksi yang diperoleh yaitu sebanyak 672,5 ribu transaksi.
3. Total pendapatan yang diperoleh dari tahun ke tahun cenderung stabil di angka Rp 80 miliar.
4. Cabang provinsi Jawa Barat memperoleh total pendapatan dan total transaksi tertinggi dibandingkan cabang provinsi lain. Yaitu dengan total pendapatan sebesar Rp 94,8 miliar dan total transaksi sebanyak 198.723 transaksi. 
5. Dari segi rating, cabang Papua Barat memperoleh rata-rata rating tertinggi yaitu sebesar 4,64; dengan rating transaksi sebesar 4,00.
6. Customer atas nama Michael Smith memiliki total belanja tertinggi dalam periode yang dimaksud, yaitu sebesar Rp 150,5 juta dengan total transaksi sebanyak 316 transaksi.
