# Writing & Presentation Test Week 5
##### Muh Zaki Choiruddin 
##### Backend Web Development Track | Skilvul Tech4Impact

Assalamu'alaikum Wr. Wb. Di markdown ini saya akan menjelaskan berbagai materi yang telah saya pelajari selama mengikuti kegiatan `Kampus Merdeka Skilvul Tech4Impact pada track Backend Web Development`.

  - [Web Server & RESTful API](#web-server--restful-api)
    - [Pengertian](#pengertian)
    - [REST](#rest)
  - [Intro & Essential Node JS](#intro--essential-node-js)
    - [Node JS](#node-js)
    - [Arsitektur](#arsitektur)
    - [Hal yang perlu dipahami sebelum belajar Node JS](#hal-yang-perlu-dipahami-sebelum-belajar-node-js)
  - [Express JS](#express-js)
    - [Pengertian](#pengertian-1)
    - [Kelebihan](#kelebihan)
    - [Back End Web Application](#back-end-web-application)
  - [Design Database With MySQL](#design-database-with-mysql)
    - [Pengertian](#pengertian-2)
    - [Kelebihan](#kelebihan-1)
    - [Kekurangan](#kekurangan)
    - [Langkah-langkah Mendesain Database](#langkah-langkah-mendesain-database)

## Web Server & RESTful API
### Pengertian
Web server adalah komputer yang menyimpan, memproses, dan mengirim file website ke web browser. Web server terdiri dari hardware dan software yang menggunakan HTTP (Hypertext Transfer Protocol) untuk merespons permintaan pengguna web dari World Wide Web. Melalui proses ini, web server memuat dan mengirim halaman yang diminta untuk disajikan di browser pengguna, misalnya Google Chrome.

#### Hardware
Di sisi perangkat keras, server web adalah komputer yang menyimpan perangkat lunak server web dan file komponen situs web. (misalnya, dokumen HTML, gambar, CSS stylesheet, dan file JavaScript) Server web terhubung ke Internet dan mendukung pertukaran data fisik dengan perangkat lain yang terhubung ke web.

#### Software
Di sisi perangkat lunak, server web mencakup beberapa bagian yang mengontrol bagaimana pengguna web mengakses file yang dihosting. Minimal, ini adalah server HTTP. Server HTTP adalah perangkat lunak yang memahami URL (alamat web) dan HTTP (protokol yang digunakan browser Anda untuk melihat halaman web). Server HTTP dapat diakses melalui nama domain situs web yang disimpannya, dan mengirimkan konten situs web yang dihosting ini ke perangkat pengguna akhir.

#### Static Web Server
Server web statis, atau tumpukan, terdiri dari komputer (perangkat keras) dengan server HTTP (perangkat lunak). Kami menyebutnya "statis" karena server mengirimkan file yang dihosting apa adanya ke browser Anda.

#### Dynamic Web Server
Sebuah server web dinamis terdiri dari server web statis ditambah perangkat lunak tambahan, paling sering server aplikasi dan database. Kami menyebutnya "dinamis" karena server aplikasi memperbarui file yang dihosting sebelum mengirim konten ke browser Anda melalui server HTTP.

#### Static Sites
Diagram pada slide berikutnya menunjukkan arsitektur server web dasar untuk situs statis (situs statis adalah situs yang mengembalikan konten hard-coded yang sama dari server setiap kali sumber daya tertentu diminta). Saat pengguna ingin menavigasi ke halaman, browser mengirimkan permintaan "GET" HTTP yang menentukan URL-nya.

#### Dynamic Site
Situs web dinamis adalah situs di mana beberapa konten respons dihasilkan secara dinamis, hanya bila diperlukan. Di situs web dinamis, halaman HTML biasanya dibuat dengan memasukkan data dari database ke dalam placeholder di template HTML (ini adalah cara yang jauh lebih efisien untuk menyimpan konten dalam jumlah besar daripada menggunakan situs web statis).

### REST
REST, atau Representational State Transfer, adalah gaya arsitektur untuk menyediakan standar antara sistem komputer di web, sehingga memudahkan sistem untuk berkomunikasi satu sama lain. Sistem yang sesuai dengan REST, sering disebut sistem RESTful, dicirikan oleh bagaimana mereka tidak memiliki kewarganegaraan dan memisahkan masalah klien dan server.

#### Komunikasi Antara Server dan Client
- Membuat request
- Gunakan method HTTP
- Cantumkan Headers and Accept Parameters


## Intro & Essential Node JS
### Node JS
Node.js adalah lingkungan runtime JavaScript open-source, lintas platform, back-end yang berjalan pada mesin V8 dan mengeksekusi kode JavaScript di luar browser web. Node.js memungkinkan pengembang menggunakan JavaScript untuk menulis alat baris perintah dan untuk skrip sisi server—menjalankan skrip sisi server untuk menghasilkan konten halaman web dinamis sebelum halaman dikirim ke browser web pengguna.

### Arsitektur
#### Single Thread
Thread dalam ilmu komputer adalah eksekusi menjalankan beberapa tugas atau program secara bersamaan. Setiap unit yang mampu mengeksekusi kode disebut thread. Javascript menggunakan konsep single thread, yang berarti hanya memiliki satu tumpukan panggilan yang digunakan untuk menjalankan program.

#### Even Loop
Dengan menggunakan konsep arsitektur javascript, walaupun menggunakan single thread tetapi kita dapat melihat javascript seperti menggunakan multi thread. Terdapat event queue yang berguna sebagai penampung ketika terdapat perintah baru yang akan dieksekusi. Event loop akan memfasilitasi kondisi ini, event loop akan memeriksa terus menerus, ketika antrian kosong di call stack maka akan menambah antrian baru dari event queue sampai semua perintah selesai di eksekusi.

#### Server side scripting
Sejatinya javascript merupakan bahasa pemrograman yang digunakan di front end side. Sehingga kita hanya bisa mengerjakan javascript dengan menggunakan browser untuk menampilkan hasil eksekusinya. Tetapi dengan menggunakan NodeJS kita dapat menjalankan javascript di server side menggunakan terminal command line menggunakan perintah “node”.

### Hal yang perlu dipahami sebelum belajar Node JS
- Arrow Expression
Arrow expression merupakan fitur terbaru dari javascript, yaitu mempermudah membuat sintaks function menggunakan “=>”
```sh
const greeting = () => {
    return "Hello";
}
```

- Asynchronous
Asynchronous merupakan konsep yang paling penting dari javascript. Pada dasarnya, javascript mengeksekusi code secara single thread dan berurutan baris per baris yang disebut dengan synchronous. Sedangkan asynchronous memungkinkan mengeksekusi code tanpa berurutan dengan cara “skip” code dan melanjutkan eksekusi code selanjutnya. Konsep ini menungkinkan code kita tidak terjadi blocking dan lebih efisien.

- JSON
JSON atau Javascript Object Notation merupakan format yang digunakan untuk menyimpan dan mengirim data menggunakan konsep object di javascript. JSON dapat digunakan di hampir semua bahasa pemrograman sehingga sangat cocok untuk dipelajari
```sh
{
    data: [
        {"title": "Learn Node JS", "published_at": "2022-01-01"},
        {"title": "How to Become Fullstack Javascrip Developer", "published_at": "2022-03-20"},
        {"title": "Mastering Backend for College Students", "published_at": "2022-10-10"}
    ]
}
```

## Express JS
### Pengertian
Express.js, atau hanya Express, adalah kerangka aplikasi web back end untuk Node.js, dirilis sebagai perangkat lunak sumber terbuka dan gratis di bawah Lisensi MIT. Ini dirancang untuk membangun aplikasi web dan API. Ini telah disebut sebagai kerangka kerja server standar de facto untuk Node.js.

### Kelebihan
Kelebihan dari framework ini terletak pada fitur caching, support dengan Google V8 Engine, JavaScript, serta didukung oleh komunitas dan skalabilitas aplikasi yang baik.

### Back End Web Application
Back end app adalah aplikasi yang berjalan di server-side yang bekerja untuk memberikan informasi berupa data sesuai request dari client / browser / front end app. Umumnya server-side app membuat REST API.


## Design Database With MySQL
### Pengertian
MySQL adalah sebuah database management system (manajemen basis data) menggunakan perintah dasar SQL (Structured Query Language) yang cukup terkenal. Database management system (DBMS) MySQL multi pengguna dan multi alur ini sudah dipakai lebih dari 6 juta pengguna di seluruh dunia.

### Kelebihan
1. Mendukung Integrasi Dengan Bahasa Pemrograman Lain.
2. Tidak Membutuhkan RAM Besar.
3. Mendukung Multi User.
4. Bersifat Open Source
5. Tipe Data yang Bervariasi.

### Kekurangan
1. Kurang Cocok untuk Aplikasi Game dan Mobile
2. Sulit Mengelola Database yang Besar
3. Technical Support yang Kurang Bagus

### Langkah-langkah Mendesain Database
#### Menentukan Entity
Entity merupakan table-table yang akan dibuat pada database, contohnya: Users, Posts, Courses.

#### Menentukan Attributes
Attributes adalah kolom yang ada di dalam entity, attributes memiliki nama dan tipe data seperti integer, varchar, date, boolean.

#### Menentukan Relasi
Ada banyak kasus setiap entity dapat saling berhubungan, misalnya user memiliki posts. Untuk membuat relasi kita dapat memanfaatkan primary key dan foreign key.