# Pre-Test Bootcamp DevOps

## knowledge base

1. Apa yang anda ketahui tentang DevOps?
2. Apa yang anda ketahui tentang Infrastructure?
3. Apa yang anda ketahui tentang server, sebutkan implementasi berserta contohnya?
4. Mengapa server dibutuhkan dalam pengembangan/development suatu software?
5. Apa yang anda ketahui mengenai Virtualisasi dan Container?
6. Mengapa teknology container saat ini sangat populer?
7. Apa yang anda ketahui tentang Orchestration Container System?

Cara pengerjaan, silahkan update file ini tulis jawabanya di bawah ini

1. DevOps adalah sebuah pendekatan dalam pengembangan perangkat lunak yang menggabungkan 
   praktik pengembangan (development) dan operasi (operations). Tujuan utama DevOps adalah
   untuk mempercepat siklus pengembangan perangkat lunak, meningkatkan kualitas, 
   dan meningkatkan kolaborasi antara tim pengembangan dan operasi.

2. Infrastruktur dalam konteks teknologi informasi merujuk pada komponen fisik dan virtual
   yang mendukung operasi sistem informasi. Ini mencakup:

   Perangkat keras: Server, jaringan, penyimpanan, perangkat periferal.
   Perangkat lunak: Sistem operasi, database, aplikasi middleware.
   Jaringan: Konektivitas antara berbagai komponen infrastruktur.
   Data: Informasi yang disimpan dan diproses oleh sistem.

   Contoh infrastruktur: pusat data, cloud computing, jaringan area lokal (LAN).

3. Server adalah komputer yang menyediakan layanan kepada klien melalui jaringan.

   Implementasi server:

   Server web: Menyediakan halaman web (misalnya, Apache, Nginx).
   Server database: Menyimpan dan mengelola data (misalnya, MySQL, PostgreSQL).

   Contoh penggunaan server:

   Website: Server web melayani permintaan halaman web dari browser pengguna.
   Aplikasi e-commerce: Server aplikasi memproses transaksi pembelian dan server database 
   menyimpan informasi pelanggan dan produk.
   Layanan cloud: Server menyediakan berbagai layanan komputasi, penyimpanan, dan jaringan 
   melalui internet.

4. Server dibutuhkan dalam pengembangan perangkat lunak karena:

   Lingkungan pengembangan: Server menyediakan lingkungan untuk menguji dan mengembangkan 
   aplikasi sebelum dideploy ke produksi.
   Hosting aplikasi: Server digunakan untuk menghosting aplikasi yang sudah jadi agar dapat
   diakses oleh pengguna.
   Penyimpanan data: Server digunakan untuk menyimpan data aplikasi, seperti data pengguna,
   konfigurasi, dan log.

5. Virtualisasi: Teknologi yang memungkinkan menjalankan beberapa sistem operasi atau beberapa
   salinan dari sistem operasi yang sama pada perangkat keras tunggal.
   Container: Unit pengemasan perangkat lunak yang ringan dan independen. Container berisi semua
   yang dibutuhkan aplikasi untuk berjalan, termasuk kode, runtime, sistem operasi, dan pustaka.

6. Portabilitas: Container dapat berjalan di berbagai platform tanpa modifikasi.
   Efisiensi: Container lebih ringan dan lebih cepat untuk di-start dibandingkan mesin virtual.
   Skalabilitas: Container dapat dengan mudah di-skalakan untuk memenuhi permintaan yang berubah-ubah.
   Kemudahan pengelolaan: Banyak alat yang tersedia untuk mengelola container, seperti Docker dan Kubernetes.

7. Orchestration container system adalah perangkat lunak yang digunakan untuk mengotomatiskan penyebaran,
   pengelolaan, dan scaling container. Sistem ini membantu mengelola lingkungan container yang kompleks 
   dengan banyak container yang berjalan secara bersamaan.

   Contoh orchestration container system:
   Kubernetes: Platform open-source yang paling populer untuk mengelola container.

   

## Task 1 (Virtualization)

- Buatlah sebuah VM dengan kententuan
  - username: `<github_user>` contoh `dimasm93`
  - hostname: `<email_without_at>` contoh `dimas.tabeldata.com`
  - OS: `ubuntu-20.04` atau `centos-7`
- Install webserver `nginx`
- Buatlah web profile temen-temen kemudian deploy ke webserver nginx tersebut yang telah di deploy
  
(kirimkan hasil screenshotnya simpan dalam folder `screenshot` dengan nama `task1.png`)

## Task 2 (Container)

Jika saya memiliki architecture seperti berikut:

![container-apps](docs/images/01-container.png)

Dimana berikut adalah configurasi docker image:

1. Backend container
  - image: `dimmaryanto93/udemy-springboot-app:latest`
  - port: `8080`
  - env: 
    - `DATABASE_HOST`: `<ip-domain-db>`
    - `DATABASE_PORT`: `5432` 
    - `DATABASE_NAME`: `<db-name>`
    - `DATABASE_PASSWORD`: `<db-password>`
    - `APPLICATION_PORT`: `8080`
  need:
    - Database PostgreSQL v14.2
2. Frontend container
  - image: `dimmaryanto93/udemy-angular-app:latest`
  - port: `80`
  - env:
    - `APPLICATION_PORT`: `80`
    - `NGINX_ROOT_DOCUMENT`: `/var/www/html`
    - `BACKEND_HOST`: `<ip-backend-apps>`
    - `BACKEND_PORT`: `<port-backend-apps>`
    - `BACKEND_CONTEXT_PATH`: `/`
  - need:
    - Backend container

Silahkan buat docker-compose filenya, kemudian simpan dalam folder `tasks` dengan nama `docker-compose.yaml`

