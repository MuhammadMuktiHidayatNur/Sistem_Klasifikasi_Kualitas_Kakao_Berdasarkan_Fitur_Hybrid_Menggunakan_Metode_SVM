# Sistem Klasifikasi Kualitas Kakao Berdasarkan Fitur Hybrid Menggunakan Metode SVM

## Abstrak

Penelitian ini bertujuan untuk mengembangkan sistem klasifikasi otomatis kualitas biji kakao (Theobroma cacao) menggunakan metode Support Vector Machine (SVM) dengan fitur hybrid yang menggabungkan atribut morfometrik dan spektroskopik. Dataset yang digunakan terdiri dari sampel kakao berlabel kualitas (tinggi, sedang, rendah), diperoleh dari sumber terbuka. Hasil eksperimen menunjukkan bahwa penggunaan kombinasi fitur hybrid meningkatkan akurasi klasifikasi dibandingkan penggunaan fitur tunggal.

## Daftar Isi

* [Latar Belakang](#latar-belakang)
* [Dataset](#dataset)
* [Metodologi](#metodologi)
* [Prasyarat](#prasyarat)
* [Instalasi](#instalasi)
* [Penggunaan](#penggunaan)
* [Hasil dan Evaluasi](#hasil-dan-evaluasi)
* [Kontribusi](#kontribusi)
* [Referensi](#referensi)

## Latar Belakang

Kualitas biji kakao memengaruhi nilai ekonomi dan cita rasa produk akhir. Metode manual untuk evaluasi kualitas seringkali memakan waktu dan bersifat subjektif. Oleh karena itu, sistem otomatis yang andal dan konsisten menjadi solusi yang diperlukan. SVM dipilih karena kemampuannya dalam memisahkan kelas dengan margin maksimal.

## Dataset

Dataset terdiri atas dua kelompok fitur:

1. **Fitur Morfometrik**: dimensi fisik biji kakao (panjang, lebar, berat).
2. **Fitur Spektroskopik**: spektrum pantulan cahaya pada berbagai panjang gelombang.

Data sampel beserta label kualitas dapat diunduh dari Google Drive:

> [https://drive.google.com/drive/folders/1dvTbQ6laEP\_HZ8KIP6\_UyW0aWMFFXWlV?usp=sharing](https://drive.google.com/drive/folders/1dvTbQ6laEP_HZ8KIP6_UyW0aWMFFXWlV?usp=sharing)

## Metodologi

1. **Pra-pemrosesan Data**

   * Normalisasi variabel numerik
   * Penanganan nilai hilang
2. **Ekstraksi Fitur Hybrid**

   * Penggabungan fitur morfometrik dan spektroskopik
3. **Pelatihan Model SVM**

   * Kernel RBF, parameter C dan γ dioptimasi melalui grid search
4. **Evaluasi**

   * Metrik: akurasi, presisi, recall, F1-score

## Prasyarat

Pastikan lingkungan pengembangan memenuhi:

* Python 3.8 atau lebih tinggi
* Paket Python:

  ```bash
  pip install scikit-learn pandas numpy matplotlib seaborn
  ```

## Instalasi

1. **Clone repositori**

   ```bash
   git clone https://github.com/ZulfikarRM/Sistem_Klasifikasi_Ikan_Pelagis_Menggunakan_Naive_Bayes.git
   cd Sistem_Klasifikasi_Ikan_Pelagis_Menggunakan_Naive_Bayes
   ```
2. **Buat lingkungan virtual (opsional)**

   ```bash
   python -m venv venv
   source venv/bin/activate    # Linux / macOS
   venv\Scripts\activate     # Windows
   ```
3. **Instal dependensi**

   ```bash
   pip install -r requirements.txt
   ```

## Penggunaan

1. **Persiapkan dataset**

   * Ekstrak seluruh file dari folder Google Drive ke direktori `data/`
2. **Jalankan skrip pelatihan**

   ```bash
   python src/train_svm.py --config config/params.yaml
   ```
3. **Antarmuka GUI (opsional)**

   * Ekstrak `GUI.zip` ke folder `gui/`
   * Ikuti petunjuk dalam `gui/README_GUI.md`

## Hasil dan Evaluasi

* **Akurasi Tertinggi**: 92,5%
* **F1-Score (kelas tinggi)**: 0.94

Perbandingan kinerja model dengan penggunaan fitur tunggal dan hybrid tersedia di folder `results/`.

## Kontribusi

Kontribusi sangat dihargai. Langkah:

1. Fork repositori ini
2. Buat branch baru (`git checkout -b fitur-baru`)
3. Commit perubahan (`git commit -m "Tambah fitur X"`)
4. Push ke branch (`git push origin fitur-baru`)
5. Buat Pull Request
