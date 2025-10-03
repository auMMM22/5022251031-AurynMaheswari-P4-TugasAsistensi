#REPORT
##commit 1
pesan: perbaikan typo
perubahan :
- mengubah Rekening -> Rekening (hal ini terkait dengan konsistensi nama struct)
- Mengubah SIMPL -> SIMPLE(perbaikan emnum tipe bunga)

-----------------------------------------------------------------------------------------------

##commit 2
pesan: penambahan header
perubahan : 
- Menambahkan header <math.h> agar fungsi pow() bisa digunakan untuk menghitung bunga majemuk
-----------------------------------------------------------------------------------------------
##commit 3
pesan : validasi tahun
perubahan : mengubah p->tahun<0 menjadi p->tahun<=0, karena biasanya nasabah menabung minimal 1 tahun dan tidak boleh 0 atau negatif

-----------------------------------------------------------------------------------------------
#Penjelasan Program
program ini digunakan untuk menghitung bunga tabungan dengan dua tipe perhitungan: Bunga Sederhana dan Bunga Majemuk. Program ini dirancang untuk menerima data dari beberapa nasabah dan kemudian menampilkan perhitungan bunga untuk setiap nasabah.
-----------------------------------------------------------------------------------------------
#input dan output
##input
===Data Nasabah 1===
Nama lengkap: Auryn
Jumlah pokok (RP): 100000
Suku bunga per tahun(%), mis. 5 untuk 5%:5
Lama menabung (tahun):2
Pilih tipe bunga(1=sederhana, 2=majemuk):1

##output
Total Bunga : Rp 10000.00
Total Akhir : Rp 110000.00