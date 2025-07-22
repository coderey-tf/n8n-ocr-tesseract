# 🧠 n8n Workflow: OCR KTP with Tesseract.js & OpenRouter

Workflow ini dirancang untuk melakukan **OCR (Optical Character Recognition)** pada gambar KTP yang diunggah melalui form, lalu mengekstrak informasi penting dari hasil OCR menggunakan LLM (Large Language Model) melalui OpenRouter.

## 🚀 Fitur

- 📤 Form upload file gambar KTP (`.jpg`, `.jpeg`, `.png`)
- 🧾 OCR menggunakan [n8n-nodes-tesseractjs](https://github.com/jreyesr/n8n-nodes-tesseractjs)
- 🧠 Ekstraksi informasi seperti NIK, Nama, Tanggal Lahir, dan lainnya menggunakan **Information Extractor** & LLM
- 🤖 Dukungan model bahasa dari OpenRouter (contoh: DeepSeek)

## 📂 Struktur Alur

1. **Form Submission**  
   Pengguna mengunggah gambar KTP melalui form.

2. **Tesseract Node**  
   Gambar diproses menggunakan Tesseract.js untuk membaca teks dari gambar.

3. **Information Extractor**  
   Hasil teks dari OCR dikirim ke Information Extractor yang menggunakan LLM untuk mengidentifikasi dan mengekstrak informasi penting dari teks KTP.

4. **OpenRouter Chat Model**  
   Model LLM seperti `deepseek/deepseek-r1:free` digunakan untuk mendukung pemahaman konteks saat ekstraksi data.

## 🔧 Dependency

- [n8n](https://n8n.io/)
- [n8n-nodes-tesseractjs](https://github.com/jreyesr/n8n-nodes-tesseractjs)
- [OpenRouter API](https://openrouter.ai)
- Node community `@n8n/n8n-nodes-langchain`

## 📥 Cara Menggunakan

1. Clone repositori ini atau import file JSON workflow (`N8N OCR TESSERACT.json`) ke dalam instansi n8n kamu.
2. Install node community berikut di n8n:
   - `n8n-nodes-tesseractjs`
   - `@n8n/n8n-nodes-langchain`
3. Konfigurasikan kredensial untuk OpenRouter API di bagian credential manager.
4. Aktifkan workflow dan jalankan.

## 🧪 Contoh Informasi yang Diekstrak

- NIK  
- Nama  
- Tempat/Tanggal Lahir  
- Jenis Kelamin  
- Golongan Darah  
- Alamat  
- RT/RW  
- Kelurahan/Desa  
- Kecamatan  
- Agama  
- Status Perkawinan  
- Pekerjaan  
- Kewarganegaraan  
- Provinsi  
- Kabupaten

## 📸 Use Case

Cocok digunakan untuk:
- Verifikasi data pengguna berbasis KTP
- Digital onboarding
- Formulir otomatisasi data identitas

## 📝 Lisensi

MIT License
