# Load Balancing Aplikasi dengan Docker & Nginx

## kelompok 6 
### anggota kelompok
1. ARIF FRATAMA
2. MUHAMMAD FAISAL AL FARISI
3. HOT MIDA NADIKA NAINGGOLAN

## Deskripsi
Project ini bertujuan untuk mengimplementasikan **load balancing** menggunakan **Nginx sebagai reverse proxy** yang mendistribusikan trafik ke beberapa backend container.  
Setiap backend berjalan di dalam container Docker yang berbeda, dan Nginx akan membagi request secara bergantian (round-robin).

---

## Teknologi yang Digunakan
- Docker
- Docker Compose
- Nginx
- Multiple backend containers

---

## Struktur Folder
loadbalancer-nginx/
│── docker-compose.yml
│
├── nginx/
│ └── nginx.conf
│
├── backend1/
│ └── index.html
│
└── backend2/
└── index.html

## Cara Menjalankan Aplikasi
1. Pastikan Docker sudah terinstall
Cek dengan perintah:
docker --version
docker compose version

2. Jalankan semua container
Masuk ke folder project, lalu jalankan:
docker compose up -d

3. Cek container yang berjalan
docker psPastikan container berikut aktif:
nginx-lb
backend1
backend2

4. Akses aplikasi
Buka browser dan akses:
http://localhost:8080

Lakukan refresh halaman beberapa kali.
Jika tampilan backend berganti-ganti, maka load balancing berhasil.

## Cara Kerja Sistem
Client mengakses aplikasi melalui browser.
Request diterima oleh Nginx.
Nginx bertindak sebagai reverse proxy.
Request diteruskan ke backend container secara bergantian.
Backend mengirim response kembali ke client.
Output yang Diharapkan
Minimal terdapat 2 backend container
Nginx berfungsi sebagai reverse proxy
Load balancing berjalan dengan baik (round-robin)
Tampilan backend berubah saat halaman di-refresh

## Kesimpulan
Implementasi ini menunjukkan bahwa Nginx dapat digunakan sebagai reverse proxy sekaligus load balancer untuk mendistribusikan trafik ke beberapa backend container menggunakan Docker.

