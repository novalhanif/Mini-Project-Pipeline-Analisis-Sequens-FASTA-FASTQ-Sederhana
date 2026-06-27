# 🧬 Simple Bioinformatics Pipeline: DNA Sequence Analysis & GC Content Calculation

> Mini Project — Mata Kuliah Struktur Data Bioinformatika 
> Institut Pertanian Bogor (IPB University)

---

## 📋 Deskripsi Proyek

Proyek ini adalah sebuah *pipeline* analisis sekuens bioinformatika sederhana yang dibangun menggunakan bahasa pemrograman **Python** dan dijalankan di lingkungan **Google Colab**. Program dirancang untuk melakukan pemrosesan terhadap file sekuens genetik berformat **FASTA** yang diunduh langsung dari database NCBI.

Program ini mengintegrasikan beberapa struktur data Python secara berurutan untuk menganalisis sekuens DNA, mulai dari pembacaan file hingga menghasilkan laporan visual dan tabel terstruktur.

---

## 🎯 Tujuan

- Mengekstrak informasi nukleotida dari file FASTA organisme/gen berbeda
- Menghitung frekuensi kemunculan masing-masing basa (A, T, C, G) menggunakan **Dictionary**
- Menghitung persentase kandungan GC (*GC Content*) tiap sekuens
- Mengurutkan (*sorting*) sekuens untuk menemukan kandidat dengan stabilitas termal tertinggi
- Menyajikan hasil dalam bentuk **grafik batang** dan **laporan CSV**

---

## 🧪 Dasar Teori

**GC Content** adalah persentase pasangan basa Guanin (G) dan Sitosin (C) di dalam molekul DNA/RNA, dihitung menggunakan rumus:

$$\text{GC Content (\%)} = \left( \frac{G + C}{A + T + C + G} \right) \times 100$$

Pasangan basa G-C dihubungkan oleh **3 ikatan hidrogen**, sedangkan pasangan A-T hanya oleh **2 ikatan hidrogen**. Akibatnya, sekuens dengan GC Content tinggi memiliki **stabilitas termal lebih kuat** (*melting temperature* / $T_m$ lebih tinggi). Parameter ini krusial dalam:

- Optimasi desain primer PCR
- Studi adaptasi organisme termofilik
- Anotasi dan karakterisasi genom

---

## ⚙️ Alur Pipeline

```
Upload File FASTA (NCBI)
[STEP 1]      Input dan Parsing  
         ↓
[STEP 2]      Menyimpang Data ke Dalam List
         ↓
[STEP 3]      Hitung Frekuensi Nukleotida dengan Dictionary
         ↓
[STEP 4]      Kalkulasi GC Content → (G+C) / total × 100%
         ↓
[STEP 5]      Sorting Descending dan Menampilkan Top 3 GC Content 
         ↓
[STEP 6]      Visualisasi Bar Chart 
         ↓
[STEP 7]      Export ke CSV dan Download Otomatis
```

## 📊 Dataset yang Digunakan
Proyek ini diuji menggunakan 1 sekuens yang diunduh dari **NCBI Nucleotide Database**:

| No. | Accession ID | Organisme | Keterangan |
|-----|-------------|-----------|------------|
| 1 | `NC_001802.1` | *Human immunodeficiency virus 1* | Complete genome (HIV-1) |

> File FASTA dapat diunduh langsung dari NCBI dengan memasukan Accession ID pada bar pencarian.

---

## 🚀 Cara Menjalankan Program

1. Buka file notebook proyek (`.ipynb`) di Google Colab.
2. Jalankan cell kode program utama dan tunggu hingga instalasi library selesai.
3. Lalu jalankan cell kode program yang kedua.
4. Saat program memunculkan tombol *Choose Files*, unggah file `.fasta`.
5. Program akan langsung mengeluarkan hasil *printout* peringkat di terminal, menampilkan grafik visual, dan membuat file CSV otomatis yang akan ke download langsung setelah program selesai dijalankan.
