# Parallel Blood Pressure Analysis System
### Inspired by CuffnCode

## Overview

Parallel Blood Pressure Analysis System adalah simulasi sistem analisis sinyal tekanan darah yang terinspirasi dari proyek CuffnCode. Proyek ini dibuat untuk mendemonstrasikan penerapan konsep Komputasi Paralel menggunakan Python Multiprocessing dalam pengolahan data medis.

Sistem melakukan simulasi data tekanan darah, melakukan filtering sederhana, mendeteksi puncak sinyal (peak detection), menghitung estimasi BPM (Beats Per Minute), serta membandingkan performa metode serial dan paralel.

---

## Background

CuffnCode merupakan platform pengukuran tekanan darah yang digunakan untuk pembelajaran dan penelitian pada bidang instrumentasi, embedded system, signal processing, dan kontrol.

Pada proyek ini, konsep pemrosesan sinyal dari CuffnCode diadaptasi ke dalam simulasi Python untuk menunjukkan bagaimana komputasi paralel dapat mempercepat proses analisis data.

---

## Objectives

Tujuan proyek ini adalah:

- Mengimplementasikan konsep Komputasi Paralel menggunakan Python Multiprocessing.
- Melakukan simulasi analisis sinyal tekanan darah.
- Melakukan peak detection pada sinyal tekanan darah.
- Mengestimasi BPM (Beats Per Minute).
- Membandingkan performa Serial Processing dan Parallel Processing.
- Mengukur peningkatan performa (Speedup).

---

## System Architecture

```text
Blood Pressure Signal
          │
          ▼
   Signal Filtering
          │
          ▼
    Peak Detection
          │
          ▼
     BPM Estimation
          │
          ▼
 Statistical Analysis
          │
          ▼
 Performance Evaluation
```

---

## Parallel Architecture

```text
1,000,000 Samples
        │
        ▼
+-----------------------+
|   Data Partitioning   |
+-----------------------+
        │
 ┌──────┼──────┬──────┐
 ▼      ▼      ▼      ▼

P1     P2     P3     P4

Filtering
Peak Detection
Statistics

 ▼      ▼      ▼      ▼

+-----------------------+
|   Result Aggregation  |
+-----------------------+
        │
        ▼
      Output
```

---

## Technologies Used

- Python 3
- Multiprocessing
- Time Module
- Random Module

---

## Project Structure

```text
Parallel-Blood-Pressure-Analysis/
│
├── parallel_bp.py
├── serial_bp.py
├── README.md
```

---

## How It Works

### Serial Processing

Semua data diproses secara berurutan menggunakan satu proses.

```text
Data
 ↓
Filtering
 ↓
Peak Detection
 ↓
Analysis
 ↓
Output
```

### Parallel Processing

Data dibagi menjadi beberapa bagian dan diproses secara bersamaan menggunakan 4 process.

```text
Data
 ↓
Split Data
 ↓
Process 1
Process 2
Process 3
Process 4
 ↓
Combine Results
 ↓
Output
```

---

## Experimental Results

### Test Configuration

| Parameter | Value |
|------------|---------|
| Sample Size | 1,000,000 |
| Number of Processes | 4 |
| Programming Language | Python |
| Processing Method | Multiprocessing |

---

### Serial Result

```text
Rata-rata Tekanan : 115.01 mmHg
Peak Terdeteksi   : 90263
Estimasi BPM      : 75
Waktu Eksekusi    : 1.2333 detik
```

---

### Parallel Result

```text
Rata-rata Tekanan : 115.01 mmHg
Tekanan Maksimum  : 159.67 mmHg
Tekanan Minimum   : 70.00 mmHg
Peak Terdeteksi   : 90003
Estimasi BPM      : 75
Waktu Eksekusi    : 0.8497 detik
```

---

## Performance Comparison

| Metric | Serial | Parallel |
|----------|----------|----------|
| Sample Size | 1,000,000 | 1,000,000 |
| Process | 1 | 4 |
| Average Pressure | 115.01 mmHg | 115.01 mmHg |
| Peak Count | 90,263 | 90,003 |
| BPM | 75 | 75 |
| Execution Time | 1.2333 s | 0.8497 s |

---

## Speedup Analysis

Formula:

```text
Speedup = Serial Time / Parallel Time
```

Calculation:

```text
Speedup = 1.2333 / 0.8497
         = 1.45x
```

### Result

Parallel Processing berhasil mempercepat proses analisis sekitar:

**1.45x lebih cepat dibandingkan Serial Processing**

---

## Discussion

Hasil pengujian menunjukkan bahwa penggunaan Python Multiprocessing mampu mengurangi waktu eksekusi dari:

```text
1.2333 detik
↓
0.8497 detik
```

Walaupun percepatan tidak mencapai 4 kali lebih cepat, metode paralel tetap memberikan peningkatan performa karena pekerjaan dibagi ke beberapa CPU Core yang berjalan secara bersamaan.

Perbedaan kecil pada jumlah peak yang terdeteksi terjadi karena data dibagi menjadi beberapa bagian (chunk) sehingga terdapat sedikit perbedaan pada batas pemrosesan antar process.

Namun demikian, estimasi BPM yang dihasilkan tetap sama yaitu 75 BPM sehingga hasil analisis utama tetap konsisten.

---

## Relationship with CuffnCode

CuffnCode merupakan platform pengukuran tekanan darah yang menghasilkan data sinyal dari sensor tekanan.

Pada proyek ini, data tekanan darah disimulasikan dan diproses menggunakan pendekatan komputasi paralel. Tujuannya adalah menunjukkan bagaimana teknik multiprocessing dapat digunakan untuk mempercepat proses filtering, peak detection, dan analisis sinyal pada sistem monitoring kesehatan.

---

## Future Improvements

Pengembangan selanjutnya dapat mencakup:

- Integrasi dengan sensor tekanan darah nyata.
- Digital Signal Processing (DSP).
- FFT Analysis.
- Real-time Monitoring Dashboard.
- Integrasi STM32.
- Machine Learning untuk prediksi kondisi kesehatan.
- Visualisasi grafik sinyal.

---

## Conclusion

Proyek ini berhasil mengimplementasikan konsep Komputasi Paralel menggunakan Python Multiprocessing pada simulasi analisis sinyal tekanan darah.

Berdasarkan hasil pengujian menggunakan 1.000.000 sampel data, metode paralel mampu mengurangi waktu eksekusi dari 1.2333 detik menjadi 0.8497 detik dengan speedup sebesar 1.45x.

Hasil tersebut menunjukkan bahwa komputasi paralel dapat meningkatkan efisiensi pemrosesan data medis dan berpotensi diterapkan pada sistem monitoring kesehatan yang lebih kompleks di masa depan.

---

## Authors

Parallel Blood Pressure Analysis System

Inspired by CuffnCode

Course:
IFB206 – Komputasi Paralel

Year:
2026
