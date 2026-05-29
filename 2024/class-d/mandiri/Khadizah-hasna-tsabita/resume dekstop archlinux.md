# Dasar Arch Linux untuk Sistem Perpustakaan Digital

## Linux sebagai Kernel

Linux sebenarnya bukan sistem operasi utuh, melainkan sebuah kernel. Kernel adalah inti dari sistem operasi yang bertugas menghubungkan perangkat keras (hardware) dengan perangkat lunak (software). Kernel mengatur proses penting seperti manajemen memori, penggunaan CPU, driver perangkat, sistem file, dan komunikasi jaringan.

Sistem operasi yang biasa disebut “Linux” sebenarnya merupakan gabungan antara Linux kernel dengan berbagai utilitas GNU, desktop environment, package manager, dan aplikasi lainnya. Contohnya adalah Arch Linux, Ubuntu, Debian, dan Fedora yang disebut sebagai distribusi Linux (Linux distribution).

Arch Linux dikenal sebagai distribusi Linux yang minimalis dan fleksibel karena pengguna dapat membangun sistem sesuai kebutuhan dari awal.

---

# Manajemen Partisi pada Arch Linux

Manajemen partisi adalah proses membagi media penyimpanan menjadi beberapa bagian logis agar sistem lebih terorganisir dan aman. Pada Arch Linux, partisi biasanya dipisahkan berdasarkan fungsi tertentu.

## Partisi Dasar Linux

### `/boot`

Partisi ini digunakan untuk menyimpan file bootloader dan kernel Linux yang dibutuhkan saat proses booting sistem.

### `/`

Disebut root partition, yaitu partisi utama tempat sistem operasi dan aplikasi inti Linux berada.

### `/home`

Digunakan untuk menyimpan data pengguna seperti dokumen, konfigurasi user, dan file pribadi.

### `swap`

Swap berfungsi sebagai memori virtual ketika RAM hampir penuh sehingga sistem tetap dapat berjalan dengan stabil.

### `/var`

Berisi data yang sering berubah seperti database, cache, log sistem, dan file server web. Pada sistem perpustakaan digital, partisi ini penting karena digunakan untuk menyimpan database aplikasi seperti SLiMS atau DSpace.

---

# Desktop Environment pada Arch Linux

Desktop Environment (DE) adalah tampilan grafis yang membuat Linux dapat digunakan melalui GUI (Graphical User Interface). Tanpa desktop environment, pengguna hanya akan menggunakan terminal.

## KDE Plasma

KDE Plasma memiliki tampilan modern dan mirip Windows. Desktop ini kaya fitur dan sangat fleksibel untuk dikustomisasi.

## GNOME

GNOME memiliki tampilan minimalis dan modern dengan workflow yang berbeda dibanding Windows.

## XFCE

XFCE merupakan desktop environment ringan yang terkenal hemat RAM dan stabil. Desktop ini memiliki logo berbentuk tikus karena menggambarkan sistem yang ringan dan cepat. XFCE cocok digunakan pada laptop dengan spesifikasi rendah atau pengguna yang menginginkan performa ringan.

## LXQt

LXQt adalah desktop environment yang lebih ringan dibanding XFCE dan cocok untuk komputer lama.

---

# Web Server dan Port pada Linux

Web server adalah layanan yang bertugas melayani permintaan website dari pengguna melalui jaringan internet. Contoh web server yang umum digunakan pada Linux adalah Apache dan Nginx.

Ketika pengguna membuka website perpustakaan digital melalui browser, browser akan mengirim request ke server melalui port tertentu.

## Pengertian Port

Port adalah jalur komunikasi pada jaringan komputer. Setiap layanan jaringan menggunakan nomor port yang berbeda.

Contoh port umum:

* Port 80 digunakan untuk HTTP
* Port 443 digunakan untuk HTTPS
* Port 22 digunakan untuk SSH
* Port 3306 digunakan untuk MariaDB/MySQL

## Port 443 dan HTTPS

Port 443 digunakan untuk layanan HTTPS yang telah menggunakan enkripsi SSL/TLS sehingga komunikasi antara browser dan server menjadi lebih aman. Pada perpustakaan digital, HTTPS penting untuk melindungi data pengguna dan proses login.

Alur sederhananya:

Browser → Port 443 → Web Server → Database → Website Perpustakaan

---

# Firewall dan iptables

Firewall adalah sistem keamanan jaringan yang bertugas mengatur lalu lintas koneksi masuk dan keluar pada server. Firewall dapat dianalogikan seperti satpam yang menentukan siapa yang boleh masuk melalui pintu tertentu.

Pada Linux, salah satu firewall yang paling terkenal adalah `iptables`.

## Fungsi iptables

iptables digunakan untuk:

* membuka port tertentu,
* menutup port yang tidak diperlukan,
* membatasi akses jaringan,
* melindungi server dari akses ilegal.

Contohnya:

* Port 443 dibuka agar website perpustakaan dapat diakses pengguna.
* Port database ditutup dari internet agar data lebih aman.

Dengan firewall, administrator dapat mengontrol keamanan server perpustakaan digital secara lebih baik.

---

# Kesimpulan

Arch Linux merupakan distribusi Linux yang fleksibel dan cocok digunakan untuk membangun sistem perpustakaan digital. Linux bekerja menggunakan kernel sebagai inti sistem operasi yang menghubungkan hardware dan software.

Dalam implementasinya, manajemen partisi digunakan untuk membagi fungsi penyimpanan agar sistem lebih aman dan terstruktur. Desktop environment seperti KDE, GNOME, dan XFCE digunakan untuk menyediakan tampilan grafis yang memudahkan pengguna.

Selain itu, layanan web server bekerja melalui port tertentu seperti port 443 untuk HTTPS, sedangkan firewall seperti iptables digunakan untuk mengatur keamanan jaringan dan akses server agar sistem perpustakaan digital tetap aman dan stabil.
