# Portofolio-v2

## Project Setup
Untuk memulai proyek ini, pastikan Anda telah menginstal semua dependency dengan menjalankan perintah berikut:

```
npm install
```

## Menjalankan Proyek dalam Mode Pengembangan
Proyek ini dapat dijalankan dalam mode pengembangan dengan fitur hot-reload menggunakan perintah berikut:

```
npm run serve
```

## Membuat Build untuk Produksi
Untuk menghasilkan build yang dioptimalkan untuk produksi, jalankan perintah berikut:

```
npm run build
```

## Melakukan Linting dan Perbaikan Kode
Gunakan perintah berikut untuk melakukan linting dan perbaikan otomatis pada file proyek:

```
npm run lint
```

## Fitur Contact Form
Proyek ini menggunakan **EmailJS** untuk menangani pengiriman email dari contact form. Untuk dapat menggunakan layanan ini, Anda perlu:

1. **Mendaftar di EmailJS:**
   - Kunjungi [EmailJS](https://www.emailjs.com/) dan buat akun.
   - Setelah mendaftar, buat service baru dan dapatkan **Service ID, Template ID, dan Public Key**.
   - Masukkan informasi ini ke dalam file konfigurasi proyek agar layanan email dapat berfungsi dengan baik.

2. **Google reCAPTCHA untuk Perlindungan dari Spam:**
   - Contact form dalam proyek ini juga dilengkapi dengan **Google reCAPTCHA** untuk mencegah spam.
   - Anda perlu mendaftarkan domain website Anda di [Google reCAPTCHA](https://www.google.com/recaptcha/about/) untuk mendapatkan **Site Key** dan **Secret Key**.
   - Masukkan kunci tersebut ke dalam konfigurasi proyek agar reCAPTCHA berfungsi dengan baik.

Tanpa langkah-langkah di atas, layanan contact form mungkin tidak akan berfungsi dengan semestinya.

## Penyesuaian Konfigurasi
Silakan lihat dokumentasi resmi Vue CLI untuk penyesuaian konfigurasi lebih lanjut di:
[Configuration Reference](https://cli.vuejs.org/config/).