# Parallel Blood Pressure Analysis System
### Inspired by CuffnCode

## Overview

Parallel Blood Pressure Analysis System merupakan simulasi sistem analisis sinyal tekanan darah yang terinspirasi dari proyek CuffnCode. Proyek ini dibuat untuk mendemonstrasikan penerapan konsep Komputasi Paralel menggunakan Python Multiprocessing dalam pengolahan data medis.

Pada sistem monitoring tekanan darah digital, sensor menghasilkan data sinyal yang perlu diproses untuk memperoleh informasi penting seperti tekanan rata-rata, deteksi puncak sinyal, dan estimasi detak jantung (BPM). Ketika jumlah data semakin besar, proses analisis dapat menjadi lebih lambat jika hanya menggunakan satu proses.

Untuk mengatasi hal tersebut, proyek ini menerapkan teknik multiprocessing dengan membagi data ke beberapa proses yang berjalan secara bersamaan sehingga waktu pemrosesan menjadi lebih efisien.

---

## Background

CuffnCode merupakan platform pengukuran tekanan darah yang dikembangkan untuk keperluan pembelajaran dan penelitian pada bidang instrumentasi, signal processing, dan sistem kontrol.

Sistem tersebut menghasilkan data tekanan darah yang dapat dianalisis lebih lanjut untuk memperoleh informasi medis yang bermanfaat.

Dalam proyek ini, dilakukan simulasi pengolahan data tekanan darah menggunakan pendekatan komputasi paralel untuk menunjukkan bagaimana pemrosesan sinyal dapat dipercepat melalui pemanfaatan multi-core processor.

---

## Objectives

Tujuan dari proyek ini adalah:

- Mengimplementasikan konsep dasar komputasi paralel.
- Menggunakan Python Multiprocessing untuk membagi beban kerja ke beberapa proses.
- Melakukan filtering sinyal tekanan darah.
- Melakukan peak detection pada sinyal.
- Mengestimasi BPM (Beats Per Minute).
- Membandingkan performa metode serial dan paralel.
- Menunjukkan manfaat penggunaan multi-core processor dalam pengolahan data medis.

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
          │
          ▼
     Final Result
```

---

## Parallel Processing Architecture

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
 Final Analysis Result
```

---

## Features

### Signal Filtering

Menggunakan metode Moving Average Filter sederhana untuk mengurangi fluktuasi sinyal dan noise.

### Peak Detection

Mendeteksi puncak sinyal yang dapat digunakan untuk simulasi perhitungan denyut jantung.

### BPM Estimation

Menghitung estimasi BPM berdasarkan jumlah puncak yang terdeteksi.

### Statistical Analysis

Menghasilkan informasi:

- Average Pressure
- Maximum Pressure
- Minimum Pressure
- Peak Count
- Estimated BPM

### Parallel Computing

Menggunakan Python Multiprocessing untuk membagi pekerjaan ke beberapa CPU Core.

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
├── parallel_bp_analysis.py
├── serial_bp_analysis.py
├── README.md
│
├── images/
│   ├── serial_result.png
│   ├── parallel_result.png
│

```

---

## How It Works

### Serial Processing

Pada metode serial, seluruh data diproses oleh satu proses secara berurutan.

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

Pada metode paralel, data dibagi menjadi beberapa bagian dan diproses secara bersamaan.

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
|------------|--------|
| Sample Size | 1,000,000 |
| Number of Processes | 4 |
| Programming Language | Python |
| Parallel Method | Multiprocessing |

### Serial Result

| Metric | Value |
|----------|----------|
| Average Pressure | 114.98 mmHg |
| Peak Count | 90,209 |
| BPM | 75 |
| Execution Time | 0.7333 s |

### Parallel Result

| Metric | Value |
|----------|----------|
| Average Pressure | 114.99 mmHg |
| Peak Count | 90,548 |
| BPM | 75 |
| Execution Time | 0.4375 s |

---

## Performance Analysis

### Speedup Calculation

Formula:

```text
Speedup = Serial Time / Parallel Time
```

Calculation:

```text
Speedup = 0.7333 / 0.4375
         = 1.68x
```

The parallel implementation achieved approximately:

**1.68x faster execution time**

compared to the serial implementation.

---

## Discussion

The results indicate that parallel processing can significantly reduce computation time by distributing workloads across multiple CPU cores.

Although the speedup is not perfectly linear, the parallel approach demonstrates better performance than the serial implementation.

Minor differences in peak detection results are caused by signal partitioning boundaries during multiprocessing and do not significantly affect BPM estimation.

---

## Relationship with CuffnCode

CuffnCode is a blood pressure measurement platform designed for education and research purposes.

This project adopts the signal-processing perspective of CuffnCode and demonstrates how parallel computing techniques can be applied to accelerate blood pressure signal analysis.

The concepts explored in this project can potentially be extended to real-time embedded medical monitoring systems.

---

## Future Improvements

Potential future developments include:

- Real sensor data acquisition.
- Digital signal filtering (Butterworth Filter).
- FFT-based signal analysis.
- Real-time data visualization.
- Integration with STM32 microcontroller.
- GPU acceleration.
- Machine Learning based health prediction.

---

## Conclusion

This project successfully demonstrates the implementation of parallel computing in blood pressure signal analysis using Python Multiprocessing.

Experimental results show that parallel processing reduces execution time from 0.7333 seconds to 0.4375 seconds, achieving a speedup of approximately 1.68 times.

The project highlights how parallel computing can improve the efficiency of medical signal processing systems and serves as a conceptual extension of the CuffnCode platform.

---

## Authors

Parallel Blood Pressure Analysis System

Inspired by CuffnCode

Course:
Komputasi Paralel

Year:
2026
