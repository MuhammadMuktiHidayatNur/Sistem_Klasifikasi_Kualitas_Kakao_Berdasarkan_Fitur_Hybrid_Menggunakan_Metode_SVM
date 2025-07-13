# Sistem Klasifikasi Kualitas Kakao Berdasarkan Fitur Hybrid Menggunakan Metode SVM

Repositori ini berisi implementasi klasifikasi kualitas biji kakao (Theobroma cacao) menggunakan metode Support Vector Machine (SVM) dengan fitur hybrid (tekstur grayscale dan spektroskopik). Proyek terdiri dari dua komponen utama:

1. **Notebook Pemrosesan & Pelatihan**: `Code_Mengolah_Dataset.ipynb`
2. **Aplikasi Web (GUI)**: folder `GUI/` hasil ekstraksi `GUI.zip`

## Struktur Program

### Root

* **Code\_Mengolah\_Dataset.ipynb**
  Notebook Jupyter untuk:

  * Eksplorasi dan visualisasi data kategori (Mentah, Matang, Busuk)
  * Ekstraksi fitur grayscale (skala intensitas)
  * Pembagian data (train/test split)
  * Pelatihan model SVM dan evaluasi
  * Menyimpan hasil preprocessing (`Hasil_scale.xlsx`) dan model (`svm_model3.pkl`)

* **Dataset/** (belum disertakan)
  Folder kosong yang harus diisi dengan citra kakao mentah, matang, dan busuk sesuai struktur:

  ```text
  Dataset/
  ├── Mentah/
  ├── Matang/
  └── Busuk/
  ```

* **Hasil\_scale.xlsx**
  File Excel yang dihasilkan oleh notebook, berisi fitur grayscale terukur.

* **svm\_model3.pkl**
  Model SVM terlatih (tersedia di folder `GUI/`).

### GUI/

* **app.py**
  Skrip Flask untuk antarmuka web klasifikasi.

* **templates/index.html**
  Halaman utama GUI.

* **static/**

  * **css/style.css**: gaya tampilan.
  * **uploads/**: contoh citra dan hasil klasifikasi.

* **svm\_model3.pkl**
  Model SVM terlatih yang digunakan oleh aplikasi.

## Alur Kerja

1. **Persiapan Dataset**

   * Unduh dan ekstrak dataset ke folder `Dataset/` seperti struktur di atas.
2. **Notebook Pemrosesan & Pelatihan**

   * Buka `Code_Mengolah_Dataset.ipynb` di Jupyter Notebook/ JupyterLab.
   * Jalankan sel-sel secara berurutan untuk:

     * Memuat dan menampilkan sampel citra
     * Mengekstraksi dan menskalakan fitur
     * Membagi data dan melatih model SVM
     * Menyimpan `Hasil_scale.xlsx` dan `svm_model3.pkl`
3. **Menjalankan Aplikasi Web**

   * Ekstrak `GUI.zip` atau pastikan folder `GUI/` telah tersedia.
   * Jalankan server Flask:

     ```bash
     cd GUI
     python app.py
     ```
   * Buka browser dan akses `http://127.0.0.1:5000`.
   * Unggah citra kakao untuk klasifikasi; hasil tampilan kategori akan muncul.

## Persyaratan

* Python 3.7+
* Jupyter Notebook / JupyterLab
* Paket Python:

  ```bash
  pip install numpy pandas opencv-python scikit-learn matplotlib seaborn openpyxl flask
  ```
* Folder `Dataset/` berisi citra kakao (Mentah, Matang, Busuk).

## Mendapatkan Dataset

Dataset dapat diunduh dari Google Drive berikut:
[Link Google Drive Dataset](https://drive.google.com/drive/folders/1dvTbQ6laEP_HZ8KIP6_UyW0aWMFFXWlV?usp=sharing)

1. Klik tautan di atas.
2. Pilih seluruh folder dan unduh sebagai ZIP.
3. Ekstrak dan letakkan hasilnya ke direktori `Dataset/` di root repositori.
