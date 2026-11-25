# Klasifikasi Game "Hit": Decision Tree vs Naive Bayes

Tugas besar mata kuliah **CAK3DAB3 Kecerdasan Artifisial**, S1 Informatika PJJ Telkom University, Semester Ganjil 2025/2026.

**Bagus Brang Wicaksono** (103042580005), kelas IF-48-PJJ-01

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/baguzbw/VideoGameHITAnalysis/blob/main/Project_AI_VideoGame_Hit.ipynb)

## Tujuan

Memprediksi apakah sebuah video game menjadi **Hit** (terjual minimal 1 juta unit) dari informasi non-penjualan seperti genre, platform, publisher, rating usia, dan ulasan. Dua algoritma dibandingkan: **Decision Tree** dan **Naive Bayes**.

## Dataset

[Video Game Sales with Ratings](https://www.kaggle.com/datasets/rush4ratio/video-game-sales-with-ratings) (Kaggle), gabungan data penjualan VGChartz dan ulasan Metacritic per Desember 2016.

- 16.719 baris, 16 kolom
- Hanya 12,4% game yang termasuk Hit, jadi kelasnya tidak seimbang
- Semua kolom penjualan dibuang dari fitur untuk mencegah data leakage

## Hasil

| Metrik | Baseline | Decision Tree | Naive Bayes |
|---|---|---|---|
| Accuracy (data uji) | 0,876 | **0,900** | 0,856 |
| Precision | 0 | **0,690** | 0,431 |
| Recall | 0 | 0,354 | **0,499** |
| F1-score | 0 | **0,468** | 0,463 |
| Accuracy 5-fold CV | – | **0,899** | 0,854 |

Uji McNemar menghasilkan p ≈ 7,4 × 10⁻¹⁴, sehingga perbedaan kedua model signifikan. Decision Tree lebih akurat karena tidak bergantung pada asumsi independensi dan distribusi fitur, serta mampu menangkap interaksi antarfitur.

## Cara menjalankan

1. Klik tombol **Open in Colab** di atas.
2. Pilih **Runtime → Run all**.

Dataset otomatis dimuat dari repo ini, jadi tidak perlu upload file.

## Isi repo

| File | Keterangan |
|---|---|
| `Project_AI_VideoGame_Hit.ipynb` | Notebook lengkap: EDA, pra-pemrosesan, training, tuning, dan evaluasi |
| `Video_Games_Sales_as_at_22_Dec_2016.csv` | Dataset |
