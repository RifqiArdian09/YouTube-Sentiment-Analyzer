# 📊 YouTube Comment Sentiment Analyzer

Aplikasi berbasis Jupyter Notebook untuk melakukan analisis sentimen komentar pada suatu video YouTube secara otomatis. Pipeline data ini menarik komentar menggunakan **YouTube Data API v3**, membersihkan teks, dan mengklasifikasikan sentimen menggunakan model Deep Learning berbahasa Indonesia (**IndoBERT**).

## 🚀 Fitur Utama
- **Data Acquisition**: Menarik ribuan komentar (top-level) dari video YouTube tanpa batasan.
- **Text Preprocessing**: Membersihkan komentar dari tautan (URL), *mention*, tag HTML, dan karakter tidak relevan lainnya secara otomatis.
- **Indonesian NLP Inference**: Klasifikasi sentimen teks ke dalam kelas **Positif**, **Netral**, atau **Negatif** menggunakan model `w11wo/indonesian-roberta-base-sentiment-classifier` dari HuggingFace Transformers.
- **Analytics & Visualization**: Menghasilkan *Pie Chart* untuk melihat persentase distribusi sentimen dan *Bar Chart* frekuensi komentar.

---

## 🛠️ Prasyarat (Requirements)
Pastikan Anda memiliki hal-hal berikut sebelum menjalankan proyek ini:
- Python 3.10 atau yang lebih baru.
- Kredensial (API Key) dari **YouTube Data API v3** melalui Google Cloud Console.

---

## 💻 Instalasi dan Persiapan

1. **Clone repositori (atau unduh folder ini)**.

2. **Buat dan Aktifkan Virtual Environment** (Sangat Direkomendasikan):
   ```bash
   # Di Linux / macOS
   python3 -m venv .venv
   source .venv/bin/activate

   # Di Windows
   python -m venv .venv
   .venv\Scripts\activate
   ```

3. **Instal Dependensi**:
   Jalankan perintah berikut untuk menginstal pustaka yang diperlukan (seperti `transformers`, `torch`, `pandas`, dll).
   ```bash
   pip install -r requirements.txt
   ```

4. **Konfigurasi API Key**:
   Salin file `env.example` menjadi `.env` lalu masukkan API Key YouTube Anda:
   ```bash
   cp env.example .env
   # Buka .env dan masukkan API_KEY Anda
   # Contoh: API_KEY=AIzaSyB...
   ```

---

## 🏃‍♂️ Cara Menjalankan

1. Buka dan jalankan Jupyter Notebook:
   ```bash
   jupyter notebook
   ```
2. Buka file `youtube_sentiment_analyzer.ipynb`.
3. Jalankan *cell* satu per satu. Pada bagian konfigurasi, sistem akan memuat API Key dari file `.env` secara otomatis dan akan meminta Anda memasukkan **URL atau Video ID** YouTube yang ingin dianalisis.
4. Jika baru pertama kali dijalankan, proses klasifikasi (Cell Inference) akan mengunduh file model IndoBERT secara otomatis ke penyimpanan lokal Anda (~500 MB).

---

## 📂 Struktur Proyek
- `youtube_sentiment_analyzer.ipynb` — Kode utama alur kerja analisis sentimen.
- `requirements.txt` — Daftar pustaka Python yang dibutuhkan.
- `.env` / `env.example` — Berkas environment untuk menyimpan kredensial dengan aman.
