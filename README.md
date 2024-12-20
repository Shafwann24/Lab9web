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

        
<h2>buat file index dengan nama index.php</h2>

        <?php
        require('tugas_header.php'); 
        
        $conn = new mysqli("localhost", "root", "", "latihan1");
        
        if ($conn->connect_error) {
            die("Koneksi gagal: " . $conn->connect_error);
        }
        ?>
        
        <div class="content">
            <h2>Data Barang</h2>
            <a href="tambah.php" style="margin-bottom: 10px; display: inline-block;">Tambah Data</a>
            <table border="1" cellspacing="0" cellpadding="10">
                <tr>
                    <th>ID</th>
                    <th>Kategori</th>
                    <th>Nama</th>
                    <th>Gambar</th>
                    <th>Harga Beli</th>
                    <th>Harga Jual</th>
                    <th>Stok</th>
                    <th>Aksi</th>
                </tr>
                <?php
             
                $sql = "SELECT * FROM data_barang";
                $result = $conn->query($sql);
        
              
                if ($result->num_rows > 0) {
                    while ($row = $result->fetch_assoc()) {
                        echo "<tr>
                            <td>{$row['id_barang']}</td>
                            <td>{$row['kategori']}</td>
                            <td>{$row['nama']}</td>
                            <td><img src='{$row['gambar']}' alt='{$row['nama']}' width='50'></td>
                            <td>{$row['harga_beli']}</td>
                            <td>{$row['harga_jual']}</td>
                            <td>{$row['stok']}</td>
                            <td>
                                <a href='ubah.php?id={$row['id_barang']}'>Ubah</a> |
                                <a href='hapus.php?id={$row['id_barang']}' onclick='return confirm(\"Yakin ingin menghapus data ini?\")'>Hapus</a>
                            </td>
                        </tr>";
                    }
                } else {
                    echo "<tr><td colspan='8'>Tidak ada data</td></tr>";
                }
        
                $conn->close();
                ?>
            </table>
        </div>
        
        <?php
        require('footer.php'); 
        ?>
        
![image](https://github.com/user-attachments/assets/f42d998b-d513-4022-a5e2-9c07461ca092)

Koneksi Database: Membuat sambungan ke database `latihan1` untuk mengambil informasi barang.  
Tampilkan Data: Menyajikan data barang dalam format tabel HTML.  
Aksi: Menyediakan tautan untuk mengedit dan menghapus data barang.


<h2>file tambah</h2>

        <?php
        require('tugas_header.php'); 
        
        $conn = new mysqli("localhost", "root", "", "latihan1");
        
        if ($_SERVER['REQUEST_METHOD'] === 'POST') {
            $kategori = $_POST['kategori'];
            $nama = $_POST['nama'];
            $gambar = $_POST['gambar'];
            $harga_beli = $_POST['harga_beli'];
            $harga_jual = $_POST['harga_jual'];
            $stok = $_POST['stok'];
        
            $sql = "INSERT INTO data_barang (kategori, nama, gambar, harga_beli, harga_jual, stok) 
                    VALUES ('$kategori', '$nama', '$gambar', '$harga_beli', '$harga_jual', '$stok')";
            
            if ($conn->query($sql) === TRUE) {
                echo "<p>Data berhasil ditambahkan</p>";
            } else {
                echo "<p>Error: " . $conn->error . "</p>";
            }
        }
        ?>
        
        <div class="content">
            <h2>Tambah Data Barang</h2>
            <form method="post">
                <label>Kategori:</label><br>
                <input type="text" name="kategori" required><br>
                <label>Nama:</label><br>
                <input type="text" name="nama" required><br>
                <label>Gambar:</label><br>
                <input type="text" name="gambar" required><br>
                <label>Harga Beli:</label><br>
                <input type="number" name="harga_beli" required><br>
                <label>Harga Jual:</label><br>
                <input type="number" name="harga_jual" required><br>
                <label>Stok:</label><br>
                <input type="number" name="stok" required><br><br>
                <button type="submit">Simpan</button>
            </form>
        </div>
        
        <?php
        require('footer.php'); 
        ?>

![image](https://github.com/user-attachments/assets/df79b229-ac48-4469-9a5b-6a4a21d55c61)

Form Input: Menyediakan formulir untuk memasukkan data barang baru.  
Proses Penambahan: Setelah formulir dikirim, data barang disimpan ke dalam database menggunakan perintah `INSERT INTO`.



<h2>file ubah</h2>

        <?php
        require('header.php');
        
        $id = $_GET['id'];
        $conn = new mysqli("localhost", "root", "", "db_barang");
        $sql = "SELECT * FROM barang WHERE id=$id";
        $result = $conn->query($sql);
        $row = $result->fetch_assoc();
        ?>
        
        <div class="content">
            <h2>Ubah Barang</h2>
            <form method="post" action="proses_ubah.php">
                <input type="hidden" name="id" value="<?php echo $row['id']; ?>">
                <label for="nama">Nama Barang:</label>
                <input type="text" id="nama" name="nama" value="<?php echo $row['nama']; ?>" required>
                <br>
                <label for="harga">Harga:</label>
                <input type="number" id="harga" name="harga" value="<?php echo $row['harga']; ?>" required>
                <br>
                <label for="stok">Stok:</label>
                <input type="number" id="stok" name="stok" value="<?php echo $row['stok']; ?>" required>
                <br>
                <button type="submit">Ubah</button>
            </form>
        </div>
        
        <?php
        require('footer.php'); 
        ?>
        
![image](https://github.com/user-attachments/assets/8549d29e-6864-4f68-ac41-a2cedd928d65)

Menampilkan form untuk mengedit data barang berdasarkan id yang diterima melalui parameter GET.
Setelah form di-submit, data di-update ke database dengan query UPDATE.

        
<h2>file hapus</h2>      

          <?php
        require('tugas_header.php'); // Memanggil header
        
        // Koneksi ke database
        $conn = new mysqli("localhost", "root", "", "latihan1");
        
        // Periksa koneksi
        if ($conn->connect_error) {
            die("Koneksi gagal: " . $conn->connect_error);
        }
        
        // Validasi parameter 'id'
        if (!isset($_GET['id']) || empty($_GET['id'])) {
            echo "<p>ID tidak ditemukan. <a href='index.php'>Kembali ke halaman utama</a></p>";
            exit;
        }
        
        $id = intval($_GET['id']); // Pastikan id adalah angka untuk mencegah SQL injection
        
        // Hapus data barang
        $sql_delete = "DELETE FROM data_barang WHERE id_barang = $id";
        
        if ($conn->query($sql_delete) === TRUE) {
            echo "<p>Data berhasil dihapus. <a href='index.php'>Kembali ke halaman utama</a></p>";
        } else {
            echo "<p>Terjadi kesalahan: " . $conn->error . "</p>";
        }
        
        $conn->close();
        ?>
        
        <?php
        require('footer.php'); // Memanggil footer
        ?>
                
![image](https://github.com/user-attachments/assets/5b9ebbc7-5e45-4b29-9b05-3b7f3e201b92)
                
Menghapus data barang berdasarkan id yang diterima melalui parameter GET. Query DELETE digunakan untuk menghapus data di database.


<h2>file style.css</h2>
     
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }
        
        .container {
            width: 80%;
            margin: auto;
            overflow: hidden;
        }
        
        header {
            background: #333;
            color: #fff;
            padding: 10px 0;
            text-align: center;
        }
        
        nav {
            margin: 10px 0;
            text-align: center;
        }
        
        nav a {
            margin: 0 15px;
            text-decoration: none;
            color: #333;
        }
        
        footer {
            background: #333;
            color: #fff;
            text-align: center;
            padding: 10px 0;
            margin-top: 20px;
        }            
                        
                        
