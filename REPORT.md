### REPORT
## commit 1
pesan: perbaikan typo
perubahan :
mengubah Rekenin -> Rekening (hal ini terkait dengan konsistensi nama struct)
Mengubah SIMPL -> SIMPLE(perbaikan emnum tipe bunga)

## commit 2
pesan: penambahan header
perubahan : 
Menambahkan header <math.h> agar fungsi pow() bisa digunakan untuk menghitung bunga majemuk

## commit 3
pesan : validasi tahun
perubahan : mengubah p->tahun<0 menjadi p->tahun<=0, karena biasanya nasabah menabung minimal 1 tahun dan tidak boleh 0 atau negatif

===============================================================================================

# Program Perhitungan Bunga Bank

# Deskripsi program 
program ini dibuat untuk menghiotung **total tabungan nasabah berdasarkan jenis bunga yang digunakan**
- **Bunga Sederhana  (Simple Interest)**
- **Bunga Majemuk (Coumpound Interest)**

Program menerima input berupa data nasabah, termasuk:
- Nama Nasabah
- Suku bunga per tahun
- Lama menabung (tahun)
- Jenis bunga (sederhana atau majemuk)
- frekuensi kapitalis untuk bunga majemuk 


## Penjelasan Komponen Program

# 1. Enum: `InterestTypt'
digunakan untuk menentukan jenis bunga yang digunakan.

typdef enum { SIMPLE = 1, COMPOUND = 2 } InterestType;
# Struct: Rekening
Menyimpan data lengkap dari nasabah
typedef struct {
    char nama[64];
    double pokok;
    double rate;
    int tahun;
    int n_per_tahun;
    InterestType tipe;
} Rekening;

# 3. 

# 4. Fungsi total_simple()
Fungsi total_simple()

Menghitung total akhir tabungan untuk bunga sederhana.
Menghitung total akhir tabungan untuk bunga sederhana.
double total_simple(const Rekening *r) {
    return r->pokok + r->pokok * r->rate * r->tahun;
}
# 4. double total_compound(const Rekening *r) {
    int n = (r->n_per_tahun > 0) ? r->n_per_tahun : 1;
    return r->pokok * pow(1.0 + r->rate / n, (double)(n * r->tahun));
}
# Fungsi cetak_ringkasan()

Menampilkan ringkasan hasil perhitungan untuk tiap nasabah.
void cetak_ringkasan(const Rekening *r) {
    double total = (r->tipe == SIMPLE) ? total_simple(r) : total_compound(r);
    double bunga = total - r->pokok;

    printf("\n--- Ringkasan Rekening ---\n");
    printf("Nama               : %s\n", r->nama);
    printf("Pokok              : Rp %.2f\n", r->pokok);
    printf("Suku Bunga (%%/thn) : %.2f%%\n", r->rate * 100.0);
    printf("Lama (tahun)       : %d\n", r->tahun);
    if (r->tipe == COMPOUND) {
        printf("Kapitalisasi/thn   : %d x\n", r->n_per_tahun);
        printf("Tipe               : Bunga Majemuk\n");
    } else {
        printf("Tipe               : Bunga Sederhana\n");
    }
    printf("Total Bunga        : Rp %.2f\n", bunga);
    printf("Total Akhir        : Rp %.2f\n", total);
}
(image.png)
(image-1.png)