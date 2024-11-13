# Chatbot dengan Memori dan Klasifikasi Intent

Tugas ini adalah chatbot sederhana dengan kemampuan menyimpan memori percakapan dan klasifikasi intents. Chatbot ini menggunakan model machine learning untuk mengenali intent dari kalimat yang diberikan pengguna.

## Author: Riyanda Cavin Sinambela

## Struktur Proyek

Berikut struktur proyek untuk membantu Anda memahami komponen di dalamnya:

```
    ├── chatbot_memory.db # Database SQLite untuk menyimpan riwayat percakapan
    ├── datasets #Folder berisi model, intents, dan data kelas
    │   ├── chatbot_model.h5 # Model machine learning chatbot dalam format H5
    │   ├── classes.pkl # File penyimpanan kelas intents
    │   ├── intents.json # Dataset intents yang digunakan chatbot
    │   └── words.pkl # File penyimpanan kata unik yang diproses
    ├── index.py # Script utama untuk menjalankan aplikasi Flask
    ├── main.ipynb # Notebook Jupyter untuk eksplorasi dan pelatihan model
    ├── README.md  # Dokumentasi proyek
    ├── static
    │   └── styles.css #CSS untuk user interface web
    └── templates
        ├── index.html  # Halaman utama interaksi chatbot
        └── view_history.html  # Halaman untuk menampilkan riwayat percakapan
```

## Fitur Utama

1. **Memori Percakapan**: Chatbot menyimpan riwayat percakapan di database SQLite.
2. **Klasifikasi Intent**: Menggunakan model machine learning untuk mengenali intent dari input pengguna.
3. **Antarmuka Web**: Menyediakan antarmuka web sederhana berbasis HTML dan CSS.
4. **Riwayat Percakapan**: Menampilkan riwayat percakapan melalui `view_history.html`.

## Persiapan dan Instalasi

### Menggunakan Anaconda untuk Menyiapkan Environment

Proyek ini menggunakan Anaconda untuk mengelola environment. Ikuti langkah berikut untuk menyiapkan environment:

1. **Instal Dependencies**:
   Instal semua dependencies dengan menggunakan file `environment.yml`.

   - Untuk menginstal environment dari environment.yml:

     ```bash
     conda env create -f environment.yml
     conda activate myenv
     ```

2.

## Penggunaan

Buka aplikasi: Akses aplikasi melalui http://localhost:5000.

Mulai chat: Ketik pesan dan dapatkan respons sesuai intent yang dikenali.

Riwayat percakapan: Klik pada View History untuk melihat riwayat percakapan.

## Penjelasan Kode Utama

main.ipynb: Berisi kode untuk menyiapkan data, melatih model, dan menyimpan hasilnya.

index.py: Mengatur seluruh fungsi utama chatbot seperti prediksi intent, mendapatkan respons, menyimpan riwayat chat, dan menyajikan hasilnya di antarmuka web.

## Struktur Fungsi Penting

clean_up_sentence: Membersihkan input pengguna untuk membuatnya lebih mudah diproses oleh model.

bow (bag of words): Membangun representasi kata dalam bentuk numerik dari input pengguna.

predict_class: Memprediksi intent berdasarkan input pengguna.
get_response: Mengambil respons yang relevan dari intents.json berdasarkan intent yang diprediksi.

## Dataset

Dataset intents dapat ditemukan di datasets/intents.json, yang berisi berbagai tag intents seperti sapaan, pertanyaan, dan pernyataan umum.

## Model

Model yang digunakan adalah chatbot_model.h5. Model ini dilatih menggunakan dataset intents, lalu disimpan dan dimuat kembali saat aplikasi Flask berjalan.

## Lisensi

Proyek ini dilisensikan di bawah MIT License. Silakan lihat file LICENSE untuk detail lebih lanjut.
