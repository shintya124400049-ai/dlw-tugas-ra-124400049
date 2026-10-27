
# Studi Ablasi Deep Learning untuk Prediksi Trafik Seluler Kota Milan

## Kelompok

| Peran | Nama | NIM |
|---|---|---|
| Pengerja individu | Shintya Linsi Nainggolan | 124400049 |

- **Kelas:** RA
- **Program Studi:** Teknik Telekomunikasi, ITERA
- **Lokasi kelompok:** 9 - Corso Como (grid 5859)
- **Perangkat:** CPU
- **Total waktu training:** sekitar 1169,5 menit (19,5 jam)
- **Laporan:** [Lihat Laporan PDF](laporan-latex/Laporan%20Latex_124400049.pdf)

## Cara Menjalankan

Clone repository dan masuk ke folder proyek:

```bash
git clone https://github.com/shintya124400049-ai/dlw-tugas-ra-124400049.git
cd dlw-tugas-ra-124400049
```

Instal dependensi dan jalankan JupyterLab:

```bash
uv sync
uv run jupyter lab
```

Buka notebook `tugas_ablasi.ipynb`, kemudian pastikan konfigurasi berikut:

```python
LOKASI_KELOMPOK = 9
CEPAT = False
SEEDS = [0, 1, 2]
```

Siapkan dataset sesuai panduan workshop, kemudian jalankan seluruh sel notebook secara berurutan.

Hasil eksperimen disimpan dalam `hasil/ablasi.csv`, sedangkan grafik hasil pengujian berada di folder `hasil/`.

## Ringkasan Hasil

Studi ini membandingkan ANN, RNN, LSTM, dan GRU untuk memprediksi trafik internet seluler Kota Milan menggunakan lima faktor ablasi wajib (A1--A5) dan dua faktor tambahan (B1--B2).

Pada lokasi Duomo, GRU dengan konfigurasi terbaik menghasilkan Test MAE sebesar 220,3, lebih rendah dibandingkan konfigurasi acuannya sebesar 237,2.

Pada lokasi Corso Como, RNN menghasilkan Test MAE terendah sebesar 124,1 setelah menggunakan konfigurasi terbaik dari Duomo.

Hasil ini menunjukkan bahwa pengaruh hiperparameter berbeda antararsitektur dan konfigurasi terbaik pada satu lokasi belum tentu menghasilkan kinerja terbaik pada lokasi lain.

## Struktur Proyek

```text
dlw-tugas-ra-124400049/
├── tugas_ablasi.ipynb
├── hasil/
│   ├── ablasi.csv
│   └── grafik eksperimen
├── laporan-latex/
│   ├── main.tex
│   ├── references.bib
│   ├── gambar/
│   └── Laporan Latex_124400049.pdf
├── pyproject.toml
├── uv.lock
└── README.md
```

## Data

Telecom Italia Big Data Challenge (Barlacchi dkk., 2015, *Scientific Data*, lisensi ODbL), versi per jam dari Zhang dkk. (INFOCOM 2021). Disiapkan oleh pengajar di repo [mctosima/dl-workshop](https://github.com/mctosima/dl-workshop).
