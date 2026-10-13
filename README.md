# KelasQu

Aplikasi kelas online KelasQu berbasis Laravel 12, Bootstrap 5, dan MySQL. Fitur awal mencakup pendaftaran peserta, login/logout, dashboard peserta, serta dashboard administrator yang hanya bisa dibuka oleh role `admin`.

## Menjalankan di Laragon

1. Pastikan PHP 8.2+, Composer, dan MySQL aktif di Laragon.
2. Buat database bernama `kelasqu` melalui HeidiSQL atau phpMyAdmin.
3. Dari folder project, salin `.env.example` menjadi `.env`, lalu sesuaikan `DB_USERNAME` dan `DB_PASSWORD`.
4. Jalankan perintah berikut:

   ```powershell
   Copy-Item .env.example .env
   composer install
   php artisan key:generate
   php artisan migrate
   php artisan serve
   ```

5. Buka alamat yang ditampilkan oleh `artisan serve`.

## Akun administrator

Pendaftaran publik selalu membuat role `user`; role tidak pernah diterima dari input form. Untuk membuat akun admin, isi `ADMIN_NAME`, `ADMIN_EMAIL`, dan `ADMIN_PASSWORD` di `.env`, kemudian jalankan `php artisan db:seed`. Seeder akan membuat atau memperbarui akun admin tersebut. Jangan membagikan atau menyimpan nilai password admin ke repositori.

## Catatan

Bootstrap dan font dimuat dari CDN. Pastikan koneksi internet tersedia saat membuka halaman. Form registrasi menggunakan validasi server, hash password bawaan Laravel, CSRF, dan regenerasi session saat login. Pengelolaan katalog kelas belum termasuk pada versi awal ini.