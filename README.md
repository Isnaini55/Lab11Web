# Lab11Web


~~~
Nama  : Isnaini Rizkyana
NIM   : 311910254
Kelas : TI 19 C1
~~~

## Praktikum 11

## Persiapan
Sebelum memulai menggunakan Framework Codeigniter, perlu dilakukan konfigurasi pada webserver. Beberapa ekstensi PHP perlu diaktifkan untuk kebutuhan pengembangan Codeigniter 4.
Berikut beberapa ekstensi yang perlu diaktifkan:

• php-json ekstension untuk bekerja dengan JSON;

• php-mysqlnd native driver untuk MySQL;

• php-xml ekstension untuk bekerja dengan XML;

• php-intl ekstensi untuk membuat aplikasi multibahasa;

• libcurl (opsional), jika ingin pakai Curl.

Untuk mengaktifkan ekstentsi tersebut, melalu XAMPP Control Panel, pada bagian Apache klik Config -> PHP.ini
![Xampp](https://user-images.githubusercontent.com/81541764/122629945-a7bc6b00-d0ea-11eb-9f43-0da8cc1ca786.png)

Pada bagian extention, hilangkan tanda ; (titik koma) pada ekstensi yang akan diaktifkan. Kemudian simpan kembali filenya dan restart Apache web server.
![php,ini](https://user-images.githubusercontent.com/81541764/122629994-f4a04180-d0ea-11eb-986e-20ebf35eba69.png)

## Instalasi Codeigniter 4
Untuk melakukan instalasi Codeigniter 4 dapat dilakukan dengan dua cara, yaitu cara manual dan menggunakan composer. Pada praktikum ini kita menggunakan
cara manual.

• Unduh Codeigniter dari website https://codeigniter.com/download

• Extrak file zip Codeigniter ke direktori htdocs/lab11_ci.

• Ubah nama direktory framework-4.x.xx menjadi ci4.

• Buka browser dengan alamat http://localhost/lab11_ci/ci4/public/

![codeigniter4](https://user-images.githubusercontent.com/81541764/122630296-cc194700-d0ec-11eb-8a85-d4beaa7ed113.JPG)


## Menjalankan CLI (Command Line Interface)
Codeigniter 4 menyediakan CLI untuk mempermudah proses development. Untuk mengakses CLI buka terminal/command prompt.
![CLI (Command Line Interface)](https://user-images.githubusercontent.com/81541764/122630402-7a24f100-d0ed-11eb-8809-827ef5278706.JPG)

Arahkan lokasi direktori sesuai dengan direktori kerja project dibuat (xampp/htdocs/lab11_ci/ci4/)
Perintah yang dapat dijalankan untuk memanggil CLI Codeigniter adalah:

![php spark](https://user-images.githubusercontent.com/81541764/122630421-b0fb0700-d0ed-11eb-8227-fa7418cd9e9f.JPG)

## Mengaktifkan Mode Debugging
Codeigniter 4 menyediakan fitur debugging untuk memudahkan developer untuk mengetahui pesan error apabila terjadi kesalahan dalam membuat kode program.
Secara default fitur ini belum aktif. Ketika terjadi error pada aplikasi akan ditampilkan pesan kesalahan seperti berikut.

![Mengaktifkan Mode Debugging](https://user-images.githubusercontent.com/81541764/122630461-09ca9f80-d0ee-11eb-9361-167510c4b184.JPG)

Semua jenis error akan ditampilkan sama. Untuk memudahkan mengetahui jenis errornya, maka perlu diaktifkan mode debugging dengan mengubah nilai
konfigurasi pada environment variable CI_ENVIRINMENT menjadi development.

![CI_ENVIRINMENT menjadi development](https://user-images.githubusercontent.com/81541764/122630559-d6d4db80-d0ee-11eb-9fdb-33b4dd7de357.JPG)

Ubah nama file env menjadi .env kemudian buka file tersebut dan ubah nilai variable CI_ENVIRINMENT menjadi development.

Contoh error yang terjadi. Untuk mencoba error tersebut, ubah kode pada file app/Controller/Home.php hilangkan titik koma pada akhir kode.
![home php](https://user-images.githubusercontent.com/81541764/122630673-be18f580-d0ef-11eb-8b41-4f35030cad2a.JPG)

## Struktur Direktori
Untuk lebih memahami Framework Codeigniter 4 perlu mengetahui struktur direktori dan file yang ada. Buka pada Windows Explorer atau dari Visual Studio Code -> Open Folder.
Terdapat beberapa direktori dan file yang perlu dipahami fungsi dan kegunaannya.

• .github folder ini kita butuhkan untuk konfigurasi repo github, seperti konfigurasi untuk build dengan github action;

• app folder ini akan berisi kode dari aplikasi yang kita kembangkan;

• public folder ini berisi file yang bisa diakses oleh publik, seperti file index.php, robots.txt, favicon.ico, ads.txt, dll;

• tests folder ini berisi kode untuk melakukan testing dengna PHP unit;

• vendor folder ini berisi library yang dibutuhkan oleh aplikasi, isinya juga termasuk kode core dari system CI.

• writable folder ini berisi file yang ditulis oleh aplikasi. Nantinya, kita bisa pakai untuk menyimpan file yang di-upload, logs, session, dll.

  Sedangkan file-file yang berada pada root direktori CI sebagai berikut.

• .env adalah file yang berisi variabel environment yang dibutuhkan oleh aplikasi.

• .gitignore adalah file yang berisi daftar nama file dan folder yang akan diabaikan oleh Git.

• build adalah script untuk mengubah versi codeigniter yang digunakan. Ada versi release (stabil) dan development (labil).

• composer.json adalah file JSON yang berisi informasi tentang proyek dan daftar library yang dibutuhkannya. File ini digunakan oleh Composer sebagai acuan.

• composer.lock adalah file yang berisi informasi versi dari libraray yang digunakan aplikasi.

• license.txt adalah file yang berisi penjelasan tentang lisensi Codeigniter;

• phpunit.xml.dist adalah file XML yang berisi konfigurasi untuk PHPunit.

• README.md adalah file keterangan tentang codebase CI. Ini biasanya akan dibutuhkan pada repo github atau gitlab.

• spark adalah program atau script yang berfungsi untuk menjalankan server, generate kode, dll.

![Struktur Direktori CI4](https://user-images.githubusercontent.com/81541764/122630721-2bc52180-d0f0-11eb-9437-66b700d8b542.JPG)

Fokus kita pada folder app, dimana folder tersebut adalah area kerja kita untuk membuat aplikasi. Dan folder public untuk menyimpan aset web seperti css, gambar, javascript, dll.

## Memahami Konsep MVC
Codeigniter menggunakan konsep MVC. MVC meripakan singkatan dari Model-View-Controller. MVC merupakan konsep arsitektur yang umum digunakan dalam pengembangan aplikasi. Konsep MVC adalah memisahkan kode program berdasarkan logic proses, data, dan tampilan. Untuk logic proses diletakkan pada direktori Contoller, Objek data diletakkan pada direktori Model, dan desain tampilan diletakkan pada direktori View.
Codeigniter menggunakan konsep pemrograman berorientasi objek dalam mengimplementasikan konsep MVC.

### Model
merupakan kode program yang berisi pemodelan data. Data dapat berupa database ataupun sumber lainnya.
View merupakan kode program yang berisi bagian yang menangani terkait tampilan user interface sebuah aplikasi. didalam aplikasi web biasanya pasti akan berhubungan dengan html dan css.
### Controller
merupakaan kode program yang berkaitan dengan logic proses yang menghubungkan antara view dan model. Controller berfungsi untuk menerima request dan data dari user kemudian diproses dengan menghubungkan bagian model dan view.
## Routing dan Controller
Routing merupakan proses yang mengatur arah atau rute dari request untuk menentukan fungsi/bagian mana yang akan memproses request tersebut. Pada framework CI4, routing bertujuan untuk menentukan Controller mana yang harus merespon sebuah request. Controller adalah class atau script yang bertanggung jawab merespon sebuah request.
Pada Codeigniter, request yang diterima oleh file index.php akan diarahkan ke Router untuk meudian oleh router tesebut diarahkan ke Controller.
Router terletak pada file app/config/Routes.php

![route php](https://user-images.githubusercontent.com/81541764/122630777-83fc2380-d0f0-11eb-88d1-8f9d4572f2a6.JPG)

Pada file tersebut kita dapat mendefinisikan route untuk aplikasi yang kita buat.
Contoh:
~~~
$routes->get('/', 'Home::index');
~~~

Kode tersebut akan mengarahkan rute untuk halaman home.

## Membuat Route Baru.
Tambahkan kode berikut di dalam Routes.php
~~~
$routes->get('/about', 'Page::about');
$routes->get('/contact', 'Page::contact');
$routes->get('/faqs', 'Page::faqs');
~~~

![route php 2](https://user-images.githubusercontent.com/81541764/122630818-fec53e80-d0f0-11eb-8845-1f67df30a401.JPG)

Untuk mengetahui route yang ditambahkan sudah benar, buka CLI dan jalankan perintah berikut.
~~~
php spark routes
~~~

![php spark routes](https://user-images.githubusercontent.com/81541764/122630896-71ceb500-d0f1-11eb-8d16-3e66acda5e62.jpg)

Selanjutnya coba akses route yang telah dibuat dengan mengakses alamat url http://localhost:8080/about
![localhost_about](https://user-images.githubusercontent.com/81541764/125445287-e1028e9d-1de7-40f0-8612-881c17c046c2.JPG)


Ketika diakses akan mucul tampilan error 404 file not found, itu artinya file/page tersebut tidak ada. Untuk dapat mengakses halaman tersebut,
harus dibuat terlebih dahulu Contoller yang sesuai dengan routing yang dibuat yaitu Contoller Page.

## Membuat Controller
Selanjutnya adalah membuat Controller Page. Buat file baru dengan nama page.php pada direktori Controller kemudian isi kodenya seperti berikut.
~~~
<?php

namespace App\Controllers;

class Page extends BaseController {
    public function about()   {
        echo "Ini halaman About";
    }
    public function contact() {
        echo "Ini halaman Contact";
    }
    public function faqs() {
        echo "Ini halaman FAQ";
    }
}
~~~

![page_php](https://user-images.githubusercontent.com/81541764/125445336-acb9dff6-e309-41f4-be43-2b95356f2022.JPG)


## Auto Routing
Secara default fitur autoroute pada Codeiginiter sudah aktif. Untuk mengubah status autoroute dapat mengubah nilai variabelnya.
Untuk menonaktifkan ubah nilai true menjadi false.
~~~
$routes->setAutoRoute(true);
~~~

Tambahkan method baru pada Controller Page seperti berikut.
~~~
    public function tos() {
        echo "ini halaman Term of Services";
    }
~~~


Method ini belum ada pada routing, sehingga cara mengaksesnya dengan menggunakan alamat: http://localhost:8080/page/tos

![page_tos](https://user-images.githubusercontent.com/81541764/125445379-2072a06b-2b73-470b-8b95-a3789ba1f739.JPG)


## Membuat View
Selanjutnya adalam membuat view untuk tampilan web agar lebih menarik. Buat file baru dengan nama about.php pada
direktori view (app/view/about.php) kemudian isi kodenya seperti berikut.
~~~
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title><?= $title; ?></title>
    </head>
<body>
    <h1><?= $title; ?></h1>
    <hr>
        <p><?= $content; ?></p>
</body>
</html>
~~~

Ubah method about pada class Controller Page menjadi seperti berikut:
~~~
    public function about() {
        return view('about', [ 'title' => 'Halaman About', 'content' => 'Ini adalah halaman abaut
        yang menjelaskan tentang isi halaman ini.' ]);
    }
~~~

![method about](https://user-images.githubusercontent.com/81541764/125445554-dfb581e6-54a8-4109-bcbd-54282b013613.JPG)


## Membuat Layout Web dengan CSS
Pada dasarnya layout web dengan css dapat diimplamentasikan dengan mudah pada codeigniter. Yang perlu diketahui adalah, pada Codeigniter 4 file yang menyimpan asset css dan javascript terletak pada direktori public.
Buat file css pada direktori public dengan nama style.css (copy file dari praktikum lab4_layout. Kita akan gunakan layout yang pernah dibuat pada praktikum 4.

![Direktori asset](https://user-images.githubusercontent.com/81541764/122631381-9f1d6200-d0f5-11eb-88c8-edc88a658e2a.JPG)

Kemudian buat folder template pada direktori view kemudian buat file header.php dan footer.php

File app/view/template/header.php
~~~
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title><?= $title; ?></title>
        <link rel="stylesheet" href="<?= base_url('/style.css');?>">
    </head>
    <body>
        <div id="container">
            <header>
                <h1>Layout Sederhana</h1>
            </header>
            <nav>
                <a href="<?= base_url('/');?>" class="active">Home</a>
                <a href="<?= base_url('/artikel');?>">Artikel</a>
                <a href="<?= base_url('/about');?>">About</a>
                <a href="<?= base_url('/contact');?>">Kontak</a>
            </nav>
            <section id="wrapper">
                <section id="main">
~~~
![header](https://user-images.githubusercontent.com/81541764/122631753-18b64f80-d0f8-11eb-8000-4efbf538d5e5.JPG)

File app/view/template/footer.php
~~~
    </section>
        <aside id="sidebar">
            <div class="widget-box">
                <h3 class="title">Widget Header</h3>
                <ul>
                    <li><a href="#">Widget Link</a></li>
                    <li><a href="#">Widget Link</a></li>
                </ul>
            </div>
            <div class="widget-box">
                <h3 class="title">Widget Text</h3>
                <p>Vestibulum lorem elit, iaculis in nisl volutpat, malesuada tincidunt arcu. Proin in leo fringilla,
                    vestibulum mi porta, faucibus felis. Integer pharetra est nunc, nec pretium nunc pretium ac.</p>
                </div>
        </aside>
    </section>
    <footer>
        <p>&copy; 2021 - Universitas Pelita Bangsa</p>
    </footer>
</div>
</body>
</html>
~~~
![footer](https://user-images.githubusercontent.com/81541764/122631824-bad63780-d0f8-11eb-8c7d-3abbd89ae05d.JPG)

Kemudian ubah file app/view/about.php seperti berikut.
~~~
    <?= $this->include('template/header'); ?>
        <h1><?= $title; ?></h1>
    <hr>
        <p><?= $content; ?></p>
    <?= $this->include('template/footer'); ?>
~~~
Selanjutnya refresh tampilan pada alamat http://localhost:8080/about

![layout dengan css](https://user-images.githubusercontent.com/81541764/125446092-ba1b9991-9a1d-44dd-80ef-60a730dcfb47.JPG)






# Praktikum 12

## Langkah-langkah Praktikum

## Persiapan.
Untuk memulai membuat aplikasi CRUD sederhana, yang perlu disiapkan adalah database server menggunakan MySQL. Pastikan MySQL Server sudah dapat dijalankan melalui XAMPP.

## Membuat Database
~~~
CREATE DATABASE lab_ci4;
~~~
![Create Database](https://user-images.githubusercontent.com/81541764/124341415-65188980-dbe6-11eb-8524-d57d69c15781.JPG)


## Membuat Tabel
~~~
CREATE TABLE artikel (
  id INT(11) auto_increment,
  judul VARCHAR(200) NOT NULL,
  isi TEXT,
  gambar VARCHAR(200),
  status TINYINT(1) DEFAULT 0,
  slug VARCHAR(200),
  PRIMARY KEY(id)
);
~~~
![Create Tabel](https://user-images.githubusercontent.com/81541764/124341472-db1cf080-dbe6-11eb-895e-914b659f720f.JPG)

## Konfigurasi koneksi database
Selanjutnya membuat konfigurasi untuk menghubungkan dengan database server. Konfigurasi dapat dilakukan dengan dua cara,
yaitu pada file app/config/database.php atau menggunakan file .env. Pada praktikum ini kita gunakan konfigurasi pada file .env.

![Konfigurasi Koneksi Database](https://user-images.githubusercontent.com/81541764/124341595-a8bfc300-dbe7-11eb-89cc-48ac32d7f9fa.JPG)


## Membuat Model
Selanjutnya adalah membuat Model untuk memproses data Artikel. Buat file baru pada direktori app/Models dengan nama ArtikelModel.php
~~~
<?php
        namespace App\Models;
        use CodeIgniter\Model;
        class ArtikelModel extends Model {
            protected $table = 'artikel';
            protected $primaryKey = 'id';
            protected $useAutoIncrement = true;
            protected $allowedFields = ['judul', 'isi', 'status', 'slug', 'gambar'];
        }
~~~

![Artikel Model php](https://user-images.githubusercontent.com/81541764/124341686-47e4ba80-dbe8-11eb-92e1-5f912aedca48.JPG)

## Membuat Controller
Buat Controller baru dengan nama Artikel.php pada direktori app/Controllers.
~~~
<?php
    namespace App\Controllers;
    
    use App\Models\ArtikelModel;

    class Artikel extends BaseController {
        public function index()
    {
        $title = 'Daftar Artikel';
        $model = new ArtikelModel();
        $artikel = $model->findAll();
        return view('artikel/index', compact('artikel', 'title'));
    }
}
~~~
![Artikel php](https://user-images.githubusercontent.com/81541764/124341809-436cd180-dbe9-11eb-9f9d-676688ee2cc0.JPG)

## Membuat View
Buat direktori baru dengan nama artikel pada direktori app/views, kemudian buat file baru dengan nama index.php.
~~~
<?= $this->include('template/header'); ?>

<?php if($artikel): foreach($artikel as $row): ?>

<article class="entry">
<h2<a href="<?= base_url('/artikel/' . $row['slug']);?>"><?= $row['judul']; ?></a> </h2>
<img src="<?= base_url('/gambar/' . $row['gambar']);?>" alt="<?= $row['judul']; ?>">
<p><?= substr($row['isi'], 0, 200); ?></p>
</article>
<hr class="divider" />
<?php endforeach; else: ?>
<article class="entry">
    <h2>Belum ada data.</h2>
</article>
<?php endif; ?>

<?= $this->include('template/footer');?>
~~~
![index](https://user-images.githubusercontent.com/81541764/124341901-1240d100-dbea-11eb-9ef2-4842f628eac0.JPG)

