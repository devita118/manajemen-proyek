Proyek Manajemen Tugas Sederhana
Proyek ini adalah aplikasi web sederhana untuk mengelola proyek dan tugas. Aplikasi ini memungkinkan pengguna untuk membuat proyek, menambahkan anggota tim (yang sudah terdaftar atau baru), serta membuat dan melacak tugas dalam setiap proyek.

Fitur Utama
Manajemen Proyek:

1. Buat, lihat, edit, dan hapus proyek.
2. Setel deskripsi dan tanggal jatuh tempo proyek.
3. Lihat progres proyek secara real-time berdasarkan tugas yang diselesaikan.

Manajemen Anggota Tim:

1. Tambahkan anggota tim ke proyek dari daftar pengguna yang sudah terdaftar.
2. Tambahkan anggota tim baru secara instan dengan mengisi nama dan email (akun baru akan dibuat).
3. Tentukan peran anggota tim (Anggota, Pengamat).
4. Hapus anggota tim dari proyek.

Manajemen Tugas:

1. Buat tugas baru untuk proyek tertentu.
2. Berikan deskripsi dan tanggal jatuh tempo untuk setiap tugas.
3. Tugaskan tugas kepada anggota tim proyek.
4. Perbarui status tugas (To Do, In Progress, Done).
5. Hapus tugas.

Akses Terbatas:

`1. Hanya pemilik proyek yang dapat mengedit detail proyek, menambah/menghapus anggota, dan mengelola tugas.
Anggota dan pengamat hanya dapat melihat proyek dan tugas yang relevan.

Sistem Otentikasi:

1. Login dan registrasi pengguna standar Laravel.
Teknologi yang Digunakan
1. Laravel Framework (PHP)
2. MySQL (Database)
3. HTML5
4. CSS3 (Inline styles dan basic custom CSS)
5. JavaScript (Vanilla JS untuk toggle UI)

Persyaratan Sistem
Sebelum memulai, pastikan Anda memiliki perangkat lunak berikut terinstal di sistem Anda:

1. PHP (Versi 8.1 atau lebih tinggi direkomendasikan)
2. Composer
3. Node.js & npm (Opsional, jika Anda berencana mengcompile aset front-end Laravel)
4. MySQL (atau database lain yang didukung Laravel seperti PostgreSQL, SQLite)
5. Web Server (Apache, Nginx, atau gunakan php artisan serve)

Instalasi dan Setup
Ikuti langkah-langkah berikut untuk menginstal dan menjalankan proyek di lingkungan lokal Anda:

1. Clone Repositori:

Bash

git clone <URL_REPOSITORI_ANDA>
cd nama-folder-proyek-anda
(Ganti <URL_REPOSITORI_ANDA> dengan URL repositori Git Anda.)

2. Instal Dependensi Composer:

Bash

composer install
Buat File .env:

Bash

cp .env.example .env
Hasilkan Application Key:

Bash

php artisan key:generate
Konfigurasi Database:
Buka file .env dan sesuaikan pengaturan database Anda:

Code snippet

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=nama_database_anda
DB_USERNAME=username_database_anda
DB_PASSWORD=password_database_anda
(Pastikan Anda telah membuat database dengan nama_database_anda di MySQL Anda.)

Jalankan Migrasi Database:
Ini akan membuat tabel-tabel yang diperlukan di database Anda, termasuk users, projects, tasks, dan project_user (pivot table).

Bash

php artisan migrate
Opsional: Anda bisa menjalankan seeder untuk mengisi data dummy (jika Anda memilikinya):

Bash

php artisan db:seed
Jalankan Server Pengembangan Laravel:

Bash

php artisan serve
Aplikasi akan berjalan di http://127.0.0.1:8000 (atau port lain yang ditunjukkan).

Penggunaan
Buka aplikasi di browser Anda: http://127.0.0.1:8000.

Registrasi: Buat akun baru jika Anda belum punya.

Login: Masuk dengan akun Anda.

Dashboard Proyek: Setelah login, Anda akan melihat daftar proyek yang Anda miliki atau yang Anda ikuti.

Membuat Proyek Baru: Klik tombol "Buat Proyek Baru" untuk memulai proyek Anda sendiri. Anda akan otomatis menjadi pemilik proyek tersebut.

Melihat Detail Proyek: Klik pada nama proyek untuk melihat detail, anggota tim, dan daftar tugasnya.

Menambah Anggota Tim:

Di halaman detail proyek, klik "Tambah Anggota Tim".

Pilih "Pilih dari Pengguna Terdaftar" untuk menambahkan akun yang sudah ada.

Pilih "Tambahkan Pengguna Baru" untuk membuat akun baru dan menambahkannya ke proyek. Catatan: Untuk pengguna baru, password akan dibuat secara acak dan tidak diberitahukan. Dalam implementasi nyata, Anda perlu menambahkan fitur notifikasi password atau reset password bagi pengguna baru.

Mengelola Tugas:

Di halaman detail proyek, Anda bisa "Buat Tugas Baru".

Perbarui status tugas (To Do, In Progress, Done) langsung dari daftar tugas.

Hanya pemilik proyek yang bisa menghapus tugas.

Struktur Proyek (Singkat)
app/Models/: Berisi model Eloquent (User.php, Project.php, Task.php).

app/Http/Controllers/: Berisi controller (ProjectController.php, TaskController.php).

database/migrations/: Berisi file migrasi database untuk tabel users, projects, tasks, project_user.

resources/views/: Berisi file Blade template (layouts/app.blade.php, projects/show.blade.php, dll.).

routes/web.php: Mendefinisikan rute-rute web aplikasi.

Lisensi
Proyek ini bersifat open-source di bawah MIT License.