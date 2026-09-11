# Kamus Data (`data/raw/`)

Sumber: Open Data Jawa Barat (BPS & Disnakertrans). Semua data disagregasi Kabupaten/Kota + Tahun. Provinsi: JAWA BARAT (kode 32), 27 kabupaten/kota.

## 1. `bps-od_17106_jml_pengeluaran_per_kapita__kabupatenkota_data.csv`
Pengeluaran per kapita per tahun. **348 baris, 2010–2022, 27 kab/kota.**

| Kolom | Arti | Contoh |
|---|---|---|
| `id` | ID baris | 1 |
| `kode_provinsi` / `nama_provinsi` | 32 / JAWA BARAT | 32 |
| `kode_kabupaten_kota` / `nama_kabupaten_kota` | Kode & nama daerah | 3201 / KABUPATEN BOGOR |
| `jumlah_pengeluaran_per_kapita` | Nilai pengeluaran, satuan **RIBU RUPIAH** | 8951.96 (= Rp8.951.960) |
| `satuan` | RIBU RUPIAH | — |
| `tahun` | 2010–2022 | 2010 |

## 2. `disnakertrans-od_19868_daftar_upah_minimum_kabupatenkota_di_drh_prov_jabar_data.csv`
Upah Minimum Kabupaten/Kota (UMK). **189 baris, 2017–2023, 27 kab/kota.**

| Kolom | Arti | Contoh |
|---|---|---|
| `besaran_upah_minimum` | UMK dalam **RUPIAH** | 5176179.07 (Karawang 2023) |
| `satuan` | RUPIAH | — |
| `tahun` | 2017–2023 | 2023 |

Kolom wilayah sama seperti di atas.

## 3. `disnakertrans-od_15793_jumlah_penduduk_yang_bekerja_berdasarkan_kabupatenkota_data.csv`
Jumlah penduduk yang bekerja. **293 baris, 2011–2022 (2016 kosong), 27 kab/kota.**

| Kolom | Arti |
|---|---|
| `jumlah_penduduk` | Jumlah orang bekerja, satuan **ORANG** |
| `satuan` | ORANG |
| `tahun` | 2011–2015, 2017–2022 (tidak ada 2016) |

> Catatan cleaning di notebook: nilai 0 diisi dengan rata-rata.

## 4. `bps-od_17110_angka_garis_kemiskinan_per_kapita_per_bulan__kabupaten_data.csv`
Garis kemiskinan per kapita per bulan. **81 baris, 2018–2020, 27 kab/kota.**

| Kolom | Arti |
|---|---|
| `garis_kemiskinan_perkapita` | Rupiah per kapita per bulan, satuan **RUPIAH** |
| `satuan` | RUPIAH |
| `tahun` | 2018–2020 (rentang tersempit → batasi analisis gabungan) |

## 5. `bps-od_17137_nilai_inflasi_berdasarkan_tujuh_kota_data.csv`
Inflasi tahunan. **40 baris, 2018–2022, 7 kota + 1 baris gabungan.**

Kota: Bogor, Sukabumi, Bandung, Cirebon, Bekasi, Depok, Tasikmalaya + `GABUNGAN 7 KOTA`. Satuan **PERSEN**.

> Keterbatasan: inflasi hanya 7 kota, tidak mencakup 27 kab/kota. Jangan dibandingkan 1:1 dengan UMK per kab/kota.

## Rentang gabungan yang aman
Irisan semua dataset: **2018–2020**. Analisis tren UMK murni bisa 2017–2023 karena datanya lengkap.
