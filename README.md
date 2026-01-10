# Praktikum-7
Praktikum 7 – Hardening RESTful API
Mata Kuliah: Web Service Engineering (WSE)
Nama: Rizal Kurniawan
NIM: 230104040211
Kelas: 2A SI
________________________________________
1. Deskripsi Singkat
Pada praktikum ini dilakukan proses hardening terhadap REST API yang telah dibuat pada UTS (Articles API).
Beberapa fitur keamanan ditambahkan, meliputi:
•	Konfigurasi environment menggunakan .env
•	CORS
•	Security Headers (Helmet)
•	Rate Limiting
•	Logging (morgan)
•	Global Error Handler
•	Penambahan endpoint monitoring (/api/health, /api/metrics, /api/info)
Tujuan utama adalah meningkatkan keamanan, monitoring, dan reliability API.
________________________________________
2. Teknologi yang Digunakan
•	Node.js + Express.js
•	dotenv
•	helmet
•	cors
•	express-rate-limit
•	morgan
________________________________________
3. Cara Menjalankan Aplikasi
1.	Install dependency:
2.	npm install
3.	Buat file .env
Isi sebagai berikut:
4.	PORT=3000
5.	NODE_ENV=development
6.	RATE_LIMIT_WINDOW=15
7.	RATE_LIMIT_MAX=100
8.	ALLOWED_ORIGIN=http://localhost:5173
9.	Jalankan server:
10.	node app.js
11.	Akses API melalui Postman atau browser
12.	http://localhost:3000/api/articles
________________________________________
4. Daftar Endpoint yang Diimplementasikan
CRUD Resource (Articles)
Method	Endpoint	Deskripsi	Status
GET	/api/articles	Mendapatkan semua data	200
GET	/api/articles/:id	Mendapatkan data berdasarkan ID	200 / 404
POST	/api/articles	Menambah data baru	201
PUT	/api/articles/:id	Mengubah data artikel	200 / 404
DELETE	/api/articles/:id	Menghapus artikel	204 / 404
________________________________________
Endpoint Monitoring
Endpoint	Deskripsi	Status
/api/info	Informasi API, metadata	200
/api/health	Mengecek status API	200
/api/metrics	Menampilkan penggunaan memory, cpu, uptime	200
________________________________________
Error Handling
Situasi	Hasil
Endpoint tidak ditemukan	JSON error (404)
Internal server error	JSON error (500)
________________________________________
Rate Limiting
•	Maksimal 100 request per 15 menit per IP
•	Jika melebihi:
•	429 Too Many Requests
________________________________________
5. Screenshot yang Dikumpulkan
1.	GET semua articles
2.	GET article by ID
3.	POST article
4.	PUT article
5.	DELETE article
6.	GET /api/info
7.	GET /api/health
8.	Error handling (GET /api/salah)
9.	Rate limit (status 429)
________________________________________
6. Kesimpulan
Praktikum ini berhasil meningkatkan keamanan API melalui penerapan middleware keamanan (helmet, CORS, rate limit), logging, dan error handling. Selain itu API menjadi lebih mudah dipantau melalui endpoint monitoring.

