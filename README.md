<h1>Nama: Muhammad Dhean Shafwan</h1>
<h1>Kelas: TI.23.A1</h1>
<hr> <br>

<h1>PHP MODULAR</h1>

<h2>1. buat folder baru pada docroot webserver (htdocs)</h2>

![image](https://github.com/user-attachments/assets/18050379-0358-4e41-94d4-abfd4ebac156)

<hr> <br>

<h2>2. Masuk ke VsCode dan masuk ke folder Latihanweb9_modular</h2>



![image](https://github.com/user-attachments/assets/77b362ed-c748-410a-a861-fb8cc4d9b3b1)

Buat file baru dengan nama header.php


    <!DOCTYPE html>
    <html lang="en">
    <head>
    <meta charset="UTF-8">
    <title>Contoh Modularisasi</title>
    <link href="style.css" rel="stylesheet" type="text/stylesheet"
    media="screen" />
    </head>
    <body>
           <div class="container">
           <header>
               <h1>Modularisasi Menggunakan Require</h1>
           </header>
           <nav>
               <a href="home.php">Home</a>
               <a href="about.php">Tentang</a>
               <a href="kontak.php">Kontak</a>
           </nav>


![image](https://github.com/user-attachments/assets/f4e1f61f-8c8c-4c60-8828-925dd6950b2b)

File ini memuat struktur dasar dokumen HTML, termasuk elemen `<head>` yang berisi metadata seperti judul halaman dan tautan ke file CSS. Selain itu, terdapat navigasi utama situs yang dirancang untuk digunakan secara konsisten di semua halaman.

<hr> <br>

<h2>Buat file baru dengan nama footer.php</h2>

![image](https://github.com/user-attachments/assets/2adbc949-6120-45b2-9f41-7a5fc0c0c2a0)

File ini berisi penutup struktur HTML, termasuk footer halaman. Footer biasanya digunakan untuk informasi hak cipta, tautan tambahan, atau informasi penting lainnya.
<hr> <br>

<h2>Buat file baru dengan nama home.php</h2>

![image](https://github.com/user-attachments/assets/e75acda4-8229-413f-a024-33729d1950c2)

        <?php require('header.php'); ?>
        
        <div class="content">
            <h2>Ini Halaman Home</h2>
            <p>Ini adalah bagian content dari halaman.</p>
        </div>
        
        <?php require('footer.php'); ?>

![image](https://github.com/user-attachments/assets/3b7bf823-d7b4-47e2-b776-094487135f74)


File ini merupakan halaman utama situs. File ini menggunakan fungsi `require()` untuk menyisipkan *header.php* di bagian atas dan *footer.php* di bagian bawah, sehingga hanya konten khusus halaman, seperti teks dan paragraf, yang perlu ditambahkan di dalamnya.

<h2> <br>
    
<h2>Buat file baru dengan nama about.php</h2>

![image](https://github.com/user-attachments/assets/dd99b9ec-f657-49fc-80b6-62da2835562b)


        <?php require('header.php'); ?>
        
        <div class="content">
            <h2>Ini Halaman About</h2>
            <p>Ini adalah bagian content dari halaman.</p>
        </div>
        
        <?php require('footer.php'); ?>


![image](https://github.com/user-attachments/assets/cfa7eb5b-f9e1-4588-8da9-da3a50b3f15e)

File ini adalah halaman *About* (Tentang). Seperti *home.php*, file ini juga memanfaatkan fungsi `require()` untuk menyisipkan *header* dan *footer*. Konten utamanya berisi deskripsi mengenai situs atau organisasi.

<hr> <br>

<h1>TUGAS DAN JAWABAN</h1>

<h2>Implementasikan konsep modularisasi pada kode program praktikum 8 tentang database, sehingga setiap halamannya memiliki template tampilan yang sama.

Berikut adalah implementasi tugas lab 8 dengan modularisasi, terdiri dari beberapa bagian seperti header, footer, dan halaman lainnya seperti tugas_header.php', tugas_footer.php, index.php, tambah.php, ubah.php, dan hapus.php`.</h2>

<h2>buat file header dengan nama tugas_header.php</h2>

        <!DOCTYPE html>
        <html lang="en">
        <head>
            <meta charset="UTF-8">
            <meta name="viewport" content="width=device-width, initial-scale=1.0">
            <title>Modularisasi - Praktikum 8</title>
            <link href="style.css" rel="stylesheet" type="text/css" />
        </head>
        <body>
            <div class="container">
                <header>
                    <h1>Sistem Data Barang</h1>
                </header>
                <nav>
                    <a href="index.php">Home</a>
                    <a href="tambah.php">Tambah Barang</a>
                </nav>
                
![image](https://github.com/user-attachments/assets/b0d1914e-5381-4bb9-a108-668c0bdb9b8f)


<h2>buat file footer dengan nama tugas_footer.php</h2>

                <footer>
                    <p>&copy; 2024, Sistem Informasi, Universitas Pelita Bangsa</p>
                </footer>
            </div>
        </body>
        </html>

![image](https://github.com/user-attachments/assets/c320f9e9-0a79-4fb9-b151-301fcb47eec6)

        
        
