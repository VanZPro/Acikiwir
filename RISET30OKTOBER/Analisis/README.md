# Tugas visualisasi ACIKIWIRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRR
Hasil ada di folder `Analisis`. File dataset yang disediakan pengguna tetap dipertahankan.

## Berkas yang digunakan

- **02_battery_visualisasi.ipynb**: nomor 2, 50.000 observasi sintetis dari 2.600 baterai. Audit kualitas dan enam visual utama, ditambah satu grafik kualitas data. Tiap visual menjelaskan alasan pemilihan, informasi, dan makna strategis.
- **03_apple_visualisasi.ipynb**: nomor 3, lima visual fundamental Apple FY2019–2025. Seleksi fakta keuangan mencegah penghitungan ganda angka pembanding antarfiling.
- **hasil/battery** dan **hasil/apple**: grafik PNG, tabel CSV, audit, dan ringkasan JSON.

## Menjalankan lokal

Notebook sudah berisi output. Untuk menghitung ulang, pertahankan susunan:

```text
RISET30OKTOBER/
  Battery/Dataset/...
  Apple/Dataset/...
  Analisis/...
```

Memerlukan Python 3.10 atau lebih baru. Dari folder Analisis:

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
jupyter lab
```

Pilih notebook dan gunakan **Restart Kernel and Run All**. Tidak ada pengambilan data dari internet saat eksekusi. Pengolahan ada langsung di sel notebook, tanpa mengimpor kode tersembunyi dari folder build.

Untuk Google Colab, unggah paket ke Drive, ekstrak dengan struktur yang sama, mount Drive, lalu pindah direktori kerja ke folder `RISET30OKTOBER/Analisis`. Mengunggah satu notebook saja tidak menyertakan dataset lokal.

## Temuan utama

**Baterai:** pada rekaman terakhir bertanggal valid per ID, median SOH 89,26%. SOH < 80% ada pada 550 baterai. Jika kondisi itu digabung dengan label High menggunakan OR, ada 579 kandidat pemeriksaan (22,27%). Kandidat bukan kegagalan terkonfirmasi. Label risiko dan hubungan antarvariabel berasal dari generator sintetis.

**Apple:** FY2025 pendapatan 416,161 miliar USD dan laba bersih 112,010 miliar USD. Laba naik 19,50% sementara kas operasi turun 5,73%. FCF sederhana, yaitu kas operasi dikurangi pembayaran aset tetap, sebesar 98,767 miliar USD dan turun 9,23%. Ini memotivasi pemeriksaan konsistensi laba dan kas dalam skenario anggaran.


## Sumber

- [EV Battery Health & Degradation Dataset](https://www.kaggle.com/datasets/vinay24baghira/ev-battery-health-and-degradation-dataset), README dan kamus dalam arsip lokal.
- [Apple SEC Financial Facts and Filings](https://www.kaggle.com/datasets/blixture/apple-stocks), metadata dan kamus lokal.
- [Dokumentasi SEC APIs](https://www.sec.gov/search-filings/edgar-application-programming-interfaces).
- [Apple FY2025 10-K](https://www.sec.gov/Archives/edgar/data/320193/000032019325000079/aapl-20250927.htm), konteks tahun fiskal dan Note 7 tentang beban pajak satu kali FY2024.

Disusun 30 Oktober 2026. Notebook menggunakan snapshot lokal, bukan data langsung terkini.
