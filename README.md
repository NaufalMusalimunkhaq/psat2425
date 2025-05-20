# Aplikasi Penilaian Sumatif Akhir Tahun (PSAT)

Halo teman-teman! 👋
Ini adalah aplikasi web sederhana untuk membantu guru dan siswa dalam mengelola absensi secara sederhana.
## 🧸 Fitur-Fitur Utama

    📝 Input dan edit nama, kelas, absen, dan foto siswa

    📊 Lihat daftar siswa dalam tampilan tabel

    🔐 Login dan logout untuk keamanan

    🎨 Tampilan sederhana dan mudah digunakan

## 🛠️ Cara Menggunakan Aplikasi Ini
## 1. Siapkan File .env

### Buat file bernama .env di folder utama proyek. Isinya seperti ini:

    DB_USER=isi_dengan_username_database
    DB_PASS=isi_dengan_password_database
    DB_NAME=isi_dengan_nama_database
    DB_HOST=isi_dengan_host_database

    Contoh:

    DB_USER=admin
    DB_PASS=P4ssw0rd123
    DB_NAME=psat2425
    DB_HOST=rdsku.AaBbCc123.us-east-1.rds.amazonaws.com

## 2. Jalankan Aplikasi

### Buka file index.php di browser untuk memulai aplikasi.
### 🔐 Informasi Login

### Gunakan akun berikut untuk masuk ke aplikasi:

    Username: admin

    Password: 123

### 📁 Struktur Folder

    index.php – Halaman utama aplikasi

    input.php – Formulir untuk menambahkan data nilai

    edit.php – Formulir untuk mengedit data nilai

    delete.php – Menghapus data nilai

    dashboard.php – Tampilan dashboard setelah login

    menu.php – Navigasi menu aplikasi

    logout.php – Keluar dari aplikasi

    db.php – Koneksi ke database

    style.css – Gaya tampilan aplikasi

    uploads/ – Folder untuk menyimpan file yang diunggah

## 3. Atau kalo kamu pake AWS kamu bisa:

### 3.1 buat server rds terlebih dahulu dengan cara:

    - masuk ke 'Aurora and RDS' > 'Databases'

    - klik 'create database' untuk membuat database RDS baru

    - pilih > standar create
            > engine options = MYsql
            > Templates = Free Tier
            > Availability and durability = Single-AZ
            > DB cluster identifier = (nama db milikmu nanti)
            > Master username = (username)
            > Master password = (password)
            > Public acces = no
            > Existing VPC security groups = (pilih SG dengan allow inbound  MySQL (3306) from anywhereIPv4 (0.0.0.0/0))
            > lalu 'create database'

    - masuk ke database yang baru dibuat tadi dengan klik namanya
    
    - lalu tunggu hingga endpointnya muncul

### 3.2 buat instance ec2 dengan cara: 

    - Masuk ke 'EC2' > 'instances'
    
    - Klik 'Launch instance' untuk membuat instance baru 

    - pilih > Name = (Nama instance)
            > Application and OS Images = ubuntu
            > Instance type = t2micro atau t2nano
            > Key pair (login) = vockey
            > Firewall (security groups) = SSH, HTTP, HTTPS, anywhere 0.0.0.0/0
            > Advanced detail > user data
            > isi user data dengan
            ``` sudo apt update -y
                sudo apt install -y apache2 php php-mysql libapache2-mod-php mysql-client
                sudo rm -rf /var/www/html/{*,.*}
                sudo git clone https://github.com/paknux/crudsiswa.git /var/www/html
                sudo chmod -R 777 /var/www/html
                echo DB_USER=(username) > /var/www/html/.env
                echo DB_PASS=(password)  >> /var/www/html/.env
                echo DB_NAME=(database)  >> /var/www/html/.env
                echo DB_HOST=(endpoint rds) >> /var/www/html/.env
            ```
            > lalu 'Launch instance'

    - connect ke instance dengan klik 'instance' lalu 'connect'
    
    - kamu seharusnya sudah bisa akses website dengan ip public instancemu
    

🧪 Teknologi yang Digunakan

    PHP

    MySQL

    HTML & CSS

📚 Lisensi

Proyek ini dibuat untuk keperluan pembelajaran dan dapat digunakan secara bebas.

Selamat mencoba dan semoga bermanfaat! 🎉