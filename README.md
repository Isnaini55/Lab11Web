# Lab11Web

~~~
Nama  : Isnaini Rizkyana
NIM   : 311910254
Kelas : TI 19 C1
~~~

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
Untuk melakukan instalasi Codeigniter 4 dapat dilakukan dengan dua cara, yaitu cara manual dan menggunakan composer. Pada praktikum ini kita menggunakan cara manual.
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





