# Website Converter

Proyek ini adalah sebuah alat Python untuk mengonversi sebuah website ke berbagai format dokumen seperti **PDF**, **DOCX**, dan **PPTX**. Proyek ini menggunakan Selenium dengan undetected_chromedriver untuk mengakses website, serta mengintegrasikan layanan anti-captcha untuk menangani CAPTCHA (misalnya reCAPTCHA). Untuk konversi DOCX dan PPTX, proyek ini mengekstrak konten HTML dan mengubahnya menjadi teks.

## Fitur

- **PDF Conversion:** Mengonversi tampilan website menjadi PDF dengan menggunakan perintah Chrome DevTools Protocol.
- **DOCX Conversion:** Mengekstrak teks dari website dan mengonversinya menjadi dokumen Word.
- **PPTX Conversion:** Mengekstrak teks dari website dan mengonversinya menjadi slide presentasi.
- **Anti-CAPTCHA:** Menangani CAPTCHA pada website menggunakan layanan pihak ketiga (misalnya AntiCaptcha).
- **Headless Browsing:** Menjalankan Chrome dalam mode headless untuk otomasi tanpa tampilan GUI.

## Persyaratan

- **Python 3.11** atau versi sebelumnya (disarankan, karena Python 3.12 dapat menyebabkan masalah dengan modul `distutils`).
- **Google Chrome** harus sudah terinstal di sistem.
- **Paket Python** berikut:
  - [Selenium](https://pypi.org/project/selenium/)
  - [undetected-chromedriver](https://pypi.org/project/undetected-chromedriver/)
  - [python-anticaptcha](https://pypi.org/project/python-anticaptcha/)
  - [beautifulsoup4](https://pypi.org/project/beautifulsoup4/) (untuk DOCX dan PPTX)
  - [python-docx](https://pypi.org/project/python-docx/) (untuk DOCX)
  - [python-pptx](https://pypi.org/project/python-pptx/) (untuk PPTX)

## Instalasi

1. **Clone atau Download Repository:**

   ```bash
   git clone https://github.com/username/website-converter.git
   cd website-converter
   ```

2. **Buat Virtual Environment (Opsional, namun disarankan):**

   ```bash
   python -m venv venv
   # Untuk Linux/macOS:
   source venv/bin/activate
   # Untuk Windows:
   venv\Scripts\activate
   ```

3. **Instal Semua Dependencies:**

   ```bash
   pip install selenium undetected-chromedriver python-anticaptcha beautifulsoup4 python-docx python-pptx
   ```

## Konfigurasi

- **API Key Anti-CAPTCHA:**  
  Setel API key layanan anti-captcha dengan mengubah variabel `CAPTCHA_SERVICE_API_KEY` di dalam script atau dengan menetapkannya sebagai environment variable:

  - Di Linux/macOS:
    ```bash
    export CAPTCHA_SERVICE_API_KEY=your_api_key
    ```
  - Di Windows:
    ```bash
    set CAPTCHA_SERVICE_API_KEY=your_api_key
    ```

- **Default Website URL:**  
  Ubah variabel `DEFAULT_WEBSITE_URL` di script jika ingin menggunakan URL default yang berbeda.

## Cara Penggunaan

Proyek ini dapat dijalankan melalui command-line dengan memilih format output yang diinginkan. Berikut contohnya:

- **Mengonversi ke PDF:**

  ```bash
  python converter.py --format pdf --website "https://example.com"
  ```

- **Mengonversi ke DOCX:**

  ```bash
  python converter.py --format docx --website "https://example.com"
  ```

- **Mengonversi ke PPTX:**

  ```bash
  python converter.py --format pptx --website "https://example.com"
  ```

Jika parameter `--output` tidak diberikan, file output akan disimpan dengan nama default sesuai format (misalnya, `output.pdf`, `output.docx`, atau `output.pptx`).

## Troubleshooting

- **Error "No module named 'bs4'":**  
  Pastikan modul `beautifulsoup4` telah terinstall:
  ```bash
  pip install beautifulsoup4
  ```

- **Masalah CAPTCHA:**  
  Pastikan API key layanan anti-captcha valid dan website target memang menggunakan CAPTCHA.

- **Masalah dengan undetected_chromedriver:**  
  Pastikan Google Chrome telah terinstal dan undetected_chromedriver adalah versi terbaru.

- **Error terkait `distutils`:**  
  Jika menggunakan Python 3.12 dan mengalami masalah dengan modul `distutils`, disarankan untuk menggunakan Python 3.11 atau lebih rendah.

## Lisensi

Proyek ini bersifat open source dan tersedia di bawah [MIT License](LICENSE).

## Kontribusi

Jika Anda ingin berkontribusi, silakan fork repository ini dan ajukan pull request. Setiap kontribusi sangat dihargai!
