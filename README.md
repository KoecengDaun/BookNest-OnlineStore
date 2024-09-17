# BookNest Online Store

## Tautan Aplikasi PWS yang Sudah Dideploy
Aplikasi PWS dapat diakses melalui tautan berikut:
[BookNest Online Store Deployment](https://laurentius-farel-booknestonlinestore2.pbp.cs.ui.ac.id)

---

## Jawaban Pertanyaan (Tugas 2)

### 1. Implementasi Checklist Secara Step-by-Step

Untuk mengimplementasikan checklist di atas, saya melakukan langkah-langkah berikut:

1. **Mempersiapkan Lingkungan Pengembangan**:
   - Menginstal **Python** dan **Django**.
   - Mengatur **virtual environment** untuk memastikan dependencies proyek terisolasi.
   
2. **Membuat Project Django**:
   - Menjalankan `django-admin startproject BookNest` untuk membuat project baru.
   
3. **Membuat Aplikasi Django**:
   - Menambahkan aplikasi utama menggunakan perintah `python manage.py startapp store`.

4. **Membangun Model**:
   - Membuat model produk buku di `models.py` untuk menyimpan data buku seperti judul, pengarang, dan harga.
   
5. **Mengatur Views dan URL**:
   - Menghubungkan model dengan views di `views.py` untuk menampilkan data buku ke halaman HTML.
   - Mengkonfigurasi `urls.py` agar request dari pengguna diarahkan ke views yang sesuai.

6. **Mendeploy Aplikasi**:
   - Menggunakan **Heroku** atau **Vercel** untuk mendeploy aplikasi ke server live.
   - Menghubungkan dengan **PostgreSQL** sebagai database di deployment environment.

### 2. Bagan Request-Response Django

![Bagan Request-Response](https://imgur.com/a/NiZgMHC)

Bagan di atas menunjukkan alur request dan response antara client dan server pada aplikasi Django:

1. **Client** mengirimkan request ke server melalui URL tertentu.
2. **urls.py** bertanggung jawab mengarahkan request ke view yang sesuai berdasarkan pola URL.
3. **views.py** memproses request, mengambil data dari **models.py** (basis data) jika diperlukan.
4. Setelah data diproses, **views.py** akan merender template HTML dan mengirim response kembali ke client.

Kaitan antara komponen:
- **urls.py**: Mengatur routing request.
- **views.py**: Memproses logika aplikasi dan berinteraksi dengan model.
- **models.py**: Menyimpan dan mengambil data dari database.
- **HTML**: Template untuk menampilkan data di browser.

### 3. Fungsi Git dalam Pengembangan Perangkat Lunak

**Git** adalah sistem kontrol versi yang sangat penting dalam pengembangan perangkat lunak karena beberapa alasan:

- **Versi Kontrol**: Git melacak perubahan pada kode, memungkinkan pengembang untuk kembali ke versi sebelumnya jika ada kesalahan.
- **Kolaborasi**: Git memungkinkan beberapa pengembang untuk bekerja bersama dalam satu proyek tanpa konflik.
- **Manajemen Branch**: Pengembang dapat membuat branch untuk fitur baru, menguji, dan menggabungkannya ke branch utama setelah diuji.

### 4. Mengapa Framework Django Digunakan dalam Pembelajaran Pengembangan Perangkat Lunak?

Django sering digunakan sebagai framework awal karena:

- **Batteries-included**: Django menyediakan banyak fitur bawaan seperti ORM, form, autentikasi, dan admin panel, sehingga memudahkan pengembangan aplikasi web.
- **Arsitektur yang Jelas**: Django mengikuti pola **Model-View-Template (MVT)** yang memisahkan logika bisnis dari tampilan dan data.
- **Komunitas yang Besar**: Django memiliki dokumentasi yang baik dan komunitas yang aktif, membantu dalam pembelajaran dan pengembangan lebih lanjut.

### 5. Mengapa Model pada Django Disebut sebagai ORM?

Django menggunakan ORM (**Object-Relational Mapping**) untuk memetakan model ke database. ORM memungkinkan pengembang untuk:

- Menulis logika database menggunakan **Python** alih-alih menggunakan **SQL** langsung.
- Mengabstraksikan detail dari berbagai database, sehingga mempermudah pengembang dalam bekerja dengan database tanpa harus menulis query SQL yang berbeda untuk setiap database.
- ORM otomatis menangani banyak tugas CRUD (Create, Read, Update, Delete), sehingga lebih efisien dan mengurangi kemungkinan error.

---

## Jawaban Pertanyaan (Tugas 3)

### 1. Jelaskan mengapa kita memerlukan data delivery dalam pengimplementasian sebuah platform?
Data delivery diperlukan dalam sebuah platform untuk memungkinkan pertukaran data antara client dan server, atau antara berbagai aplikasi yang saling terhubung. Dalam konteks aplikasi web, data delivery memungkinkan komunikasi antara backend (server) yang mengelola database dan frontend (antarmuka pengguna) yang menampilkan informasi kepada pengguna.

 - Contohnya, ketika pengguna mengisi form untuk menambahkan produk, data tersebut harus dikirim dari browser pengguna (client) ke server, diproses, dan disimpan ke dalam database. Data delivery juga diperlukan saat menampilkan informasi seperti daftar produk, yang diambil dari server dan dikirim ke frontend dalam format seperti JSON atau XML agar dapat ditampilkan dengan benar kepada pengguna.

### 2. Menurutmu, mana yang lebih baik antara XML dan JSON? Mengapa JSON lebih populer dibandingkan XML?
JSON umumnya lebih baik dan lebih populer dibandingkan XML dalam konteks aplikasi web modern. Berikut alasannya:

 - Sintaks yang lebih sederhana: JSON memiliki struktur yang lebih ringkas dan mudah dipahami manusia maupun mesin dibandingkan XML yang memiliki markup lebih kompleks.
 - Ukuran data lebih kecil: JSON tidak membutuhkan banyak tag seperti XML, sehingga menghemat ruang dan bandwidth.
 - Kompatibilitas: JSON lebih mudah digunakan dan didukung oleh banyak bahasa pemrograman modern. JSON adalah format native untuk JavaScript, yang menjadikannya pilihan default dalam banyak aplikasi web.
 - Kecepatan: Parsing data JSON lebih cepat dibandingkan XML karena strukturnya lebih sederhana.
 - XML masih digunakan dalam beberapa aplikasi enterprise atau di lingkungan yang membutuhkan data dengan skema yang lebih kaya (misalnya, dengan namespace atau tipe data kompleks), tetapi dalam banyak aplikasi web modern, JSON menjadi pilihan utama karena efisiensi dan kesederhanaannya.

### 3. Jelaskan fungsi dari method is_valid() pada form Django dan mengapa kita membutuhkan method tersebut?
Method is_valid() dalam Django digunakan untuk memvalidasi data yang diinputkan melalui form. Fungsinya adalah untuk memastikan bahwa data yang dimasukkan sesuai dengan aturan validasi yang telah ditentukan dalam model atau form Django.

 - Jika valid, is_valid() mengembalikan True, yang berarti data dapat diproses lebih lanjut, misalnya disimpan ke dalam database.
 - Jika tidak valid, is_valid() akan mengembalikan False, dan Django akan memberikan pesan kesalahan yang dapat ditampilkan kembali kepada pengguna.

Metode ini diperlukan untuk menghindari penyimpanan data yang tidak sah atau tidak sesuai dengan format yang diinginkan; contohnya, data tidak ada dalam kolom yang harus ada atau data yang tidak memenuhi tipe data yang ditentukan dalam model.

### 4. Mengapa kita membutuhkan csrf_token saat membuat form di Django? Apa yang dapat terjadi jika kita tidak menambahkan csrf_token pada form Django? Bagaimana hal tersebut dapat dimanfaatkan oleh penyerang?
csrf_token (Cross-Site Request Forgery token) adalah langkah keamanan yang disediakan Django untuk melindungi aplikasi dari serangan CSRF (Cross-Site Request Forgery). Ini adalah token unik yang dikaitkan dengan sesi pengguna dan diverifikasi oleh server setiap kali pengguna mengirim permintaan POST (misalnya, saat mengirim form).

 - Jika tidak ada csrf_token, form yang dikirimkan dapat menjadi target serangan CSRF, di mana penyerang dapat memanipulasi sesi pengguna dan memaksa pengguna untuk melakukan tindakan yang tidak diinginkan tanpa sepengetahuan mereka. Misalnya, penyerang bisa membuat pengguna mengirimkan data palsu atau melakukan perubahan pada akun pengguna tanpa izin.
 - Penyerang dapat memanfaatkan form tanpa csrf_token dengan mengirimkan permintaan POST dari situs lain yang secara otomatis dijalankan oleh browser pengguna tanpa sepengetahuan mereka.

### 5. Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step (bukan hanya sekadar mengikuti tutorial).
Berikut langkah-langkah yang saya lakukan untuk mengimplementasikan checklist tugas ini:

 - Membuat model Product:

    - Saya memulai dengan membuat model Product di models.py, mendefinisikan semua atribut yang diperlukan seperti name, price, description, author, genre, publication_year, stock, dan isbn.
 - Membuat form ProductForm:

    - Setelah model selesai, saya membuat form ProductForm di forms.py menggunakan ModelForm, yang secara otomatis menghasilkan field dari model Product.
 - Membuat view show_main:

    - Saya membuat view show_main yang menampilkan form dan daftar produk. View ini menangani input form menggunakan method POST dan menampilkan daftar produk dari database menggunakan context yang di-render ke template main.html.
 - Menambahkan CSRF token:

    - Dalam template form, saya menambahkan tag {{ csrf_token }} untuk memastikan keamanan dari serangan CSRF.
 - Menambahkan view untuk JSON dan XML:

    - Saya menambahkan views untuk menampilkan data produk dalam format JSON dan XML, baik untuk semua produk maupun untuk produk berdasarkan ID. View ini menggunakan Django's serializers untuk mengubah data produk menjadi format JSON atau XML.
 - Menambahkan routing URL:

    - Saya menambahkan routing di urls.py untuk menghubungkan views ke URL yang sesuai. Ini termasuk routing untuk form (show_main) serta views JSON dan XML.
 - Menguji hasil dengan Postman:

    - Saya menguji URL yang menampilkan data dalam format JSON dan XML menggunakan Postman, memastikan data tampil dengan benar dalam kedua format tersebut.
   
### Gambar-Gambar

![XML by ID](ScreenShot/XML%20by%20ID.png)
![XML](ScreenShot/XML.png)
![JSON by ID](ScreenShot/JSON%20by%20ID.png)
![JSON](ScreenShot/JSON.png)
