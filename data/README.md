# Dataset: Titik Panas Kebakaran Indonesia (NASA FIRMS, VIIRS S-NPP)

## Sumber
- Penyedia: NASA FIRMS (Fire Information for Resource Management System)
- URL: https://firms.modaps.eosdis.nasa.gov/country/
- Sensor: VIIRS S-NPP, resolusi 375 m
- Cakupan wilayah: Indonesia
- Cakupan waktu: 20 Januari 2012 – 31 Desember 2024
- Tanggal unduh: 10/6/2026

## Ukuran
- Jumlah file: 13 CSV (satu file per tahun)
- Total baris: **3.418.464** (memenuhi syarat > 1 juta baris)
- Total ukuran: ±258 MB

| Tahun | Jumlah baris |
|---|---:|
| 2012* | 318.613 |
| 2013 | 257.222 |
| 2014 | 555.597 |
| 2015 | 875.824 |
| 2016 | 117.250 |
| 2017 | 90.849 |
| 2018 | 191.173 |
| 2019 | 437.281 |
| 2020 | 91.536 |
| 2021 | 68.325 |
| 2022 | 57.220 |
| 2023 | 253.388 |
| 2024 | 104.186 |

\* Data 2012 dimulai 20 Januari, saat VIIRS S-NPP mulai beroperasi.

## Cara Mengunduh
1. Buka https://firms.modaps.eosdis.nasa.gov/country/.
2. Pilih sensor **VIIRS S-NPP**.
3. Unduh file tahunan 2012–2024 dan ambil CSV untuk **Indonesia**.
4. Simpan seluruh file di `data/raw/firms/` dengan nama asli,
   misalnya `viirs-snpp_2015_Indonesia.csv`.

Struktur folder yang diharapkan:
data/raw/firms/
├── viirs-snpp_2012_Indonesia.csv
├── ...
└── viirs-snpp_2024_Indonesia.csv


## Deskripsi Kolom
| Kolom | Tipe | Arti |
|---|---|---|
| latitude, longitude | float | Pusat piksel deteksi |
| bright_ti4 | float | Brightness temperature kanal I-4 (Kelvin) |
| bright_ti5 | float | Brightness temperature kanal I-5 (Kelvin) |
| scan, track | float | Ukuran piksel arah scan dan track (km) |
| acq_date | date | Tanggal akuisisi (UTC) |
| acq_time | string (HHMM) | Jam akuisisi (UTC) |
| satellite | string | Satelit (`N` = Suomi NPP) |
| instrument | string | Instrumen (`VIIRS`) |
| confidence | string | Keyakinan deteksi: `l` low, `n` nominal, `h` high |
| version | int | Versi pemrosesan data |
| frp | float | Fire Radiative Power (MW) |
| daynight | string | `D` siang, `N` malam |
| type | int | 0 kebakaran vegetasi, 1 gunung api aktif, 2 sumber statis lain, 3 lepas pantai |

## Catatan
- Waktu dalam data menggunakan **UTC**, bukan WIB/WITA/WIT.
- File data tidak di-commit ke repository (lihat `.gitignore`).

## Acknowledgment
Data disediakan oleh LANCE FIRMS yang dioperasikan oleh NASA/GSFC/ESDIS.