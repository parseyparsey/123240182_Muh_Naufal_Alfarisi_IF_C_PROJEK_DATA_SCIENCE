# Proyek Akhir Praktikum Data Science — Covertype

## Isi folder
1. `01_Business_Understanding_dan_Data_Gathering.ipynb`
2. `02_EDA.ipynb`
3. `03_Cleaning_dan_Preprocessing.ipynb`
4. `04_Modelling_Evaluasi_dan_Konklusi.ipynb`

## Dataset
Gunakan file asli `covtype.data` dari UCI Covertype:
- DOI: https://doi.org/10.24432/C50K5N
- Repository: https://archive.ics.uci.edu/dataset/31/covertype

File dataset tidak disertakan dalam ZIP ini. Letakkan `covtype.data` di folder yang sama dengan notebook atau di subfolder `data/`.

## Urutan pengerjaan
Jalankan notebook 01 → 02 → 03 → 04.
Notebook 03 menghasilkan `covtype_preprocessed_split.npz`, yang akan dibaca oleh notebook 04. Jika file NPZ tidak ditemukan, notebook 04 mencoba memproses ulang dari `covtype.data`.

## Dependensi
Paket utama:
- Python 3
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- jupyter

Instalasi jika belum tersedia:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

## Catatan metodologis
- Data mentah Covertype tidak memiliki header; notebook menetapkan nama kolom sesuai urutan atribut.
- Pemeriksaan terhadap file yang diunggah menunjukkan 581.012 baris, 55 kolom, 0 missing value, dan 0 baris duplikat.
- Outlier IQR tidak otomatis dihapus karena nilai ekstrem dapat merepresentasikan kondisi topografi yang valid.
- `Aspect` ditransformasikan menjadi sinus dan cosinus karena bersifat melingkar.
- Split dilakukan secara stratified dengan `random_state=42`.
- Macro-F1 menjadi metrik utama karena target memiliki ketidakseimbangan kelas.
- Model yang digunakan adalah baseline Dummy, Decision Tree, dan Random Forest. Pastikan algoritma tersebut sesuai dengan materi praktikum yang diajarkan dosen/asisten.
- Hasil random split memiliki keterbatasan untuk data yang berpotensi memiliki autokorelasi spasial.

## Catatan akademik
Notebook ini adalah kerangka kerja yang perlu dijalankan, diperiksa, dan dipahami. Lengkapi interpretasi hasil visualisasi dan konklusi menggunakan output aktual ketika notebook dijalankan. Jangan menyalin angka hasil eksperimen yang belum dihasilkan oleh eksekusi notebook.
