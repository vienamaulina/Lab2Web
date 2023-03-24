# Lab2Web
<p> Nama : Viena Dwi Putri Maulina <br> Nim : 312110469 <br> Kelas: TI.21.C1 <br> Mata Kuliah : Pemrograman Web 2 <br> Tugas Pertemuan 3 </p>

# Tugas
![gambar 1](soal.png)

<p> index.php <p>

```php
<!DOCTYPE html>
<html lang="en">
<head>
<title>Tugas</title>
</head>
<body>
<form action="output.php" method="post">
<table>
    <tr>
        <td width="100"> Nama  </td>
        <td> : <input type="text" name="nama" /> </td> 
    </tr>
        
    <tr>
        <td>Tanggal Lahir  </td>
        <td> : <input type="date" name="tanggal_lahir"> </td> </tr>
        
    <tr> 
        <td> Pekerjaan  </td>
       <td> : <input type="radio" name="pekerjaan" value="Karyawan"/>Karyawan
        <input type="radio" name="pekerjaan" value="PNS"/>PNS
        <input type="radio" name="pekerjaan" value="Petani"/>Petani
        <input type="radio" name="pekerjaan" value="Wiraswasta"/>Wiraswasta </td>
    </tr>
    <tr>
        <td></td>
        <td> <input type="submit" value="kirim"/> </td>
    </tr>
</table>
</form>
</body>
</html>

```

<p>output.php<P>

```php

<title> Output </title>
<?php
    
    $tanggal_lahir = new DateTime($_POST['tanggal_lahir']);
    $sekarang = new DateTime("today");
    if ($tanggal_lahir > $sekarang) { 
    $thn = "0";
    $bln = "0";
    $tgl = "0";
    }
    $thn = $sekarang->diff($tanggal_lahir)->y;
    $bln = $sekarang->diff($tanggal_lahir)->m;
    $tgl = $sekarang->diff($tanggal_lahir)->d;

    echo 'Nama      :  ' . $_POST['nama'];
    echo "<br>";
    echo "Tanggal Lahir : ". $_POST['tanggal_lahir'];
    echo "<br>";
    echo "Umur      : ";
    echo $thn." tahun ". $bln. " bulan " . $tgl. " hari";
    echo "<br>";
    echo "Pekerjaan     : " . $_POST['pekerjaan'];
    echo "<br>";


    $pekerjaan = ($_POST['pekerjaan']);
    switch ($pekerjaan){
        case "Karyawan": echo "Gaji     : Rp 5.000.000";break;
        case "PNS": echo "Gaji      : Rp 6.000.000";break;
        case "Petani": echo "Gaji       : Rp 3.000.000";break;
        case "Wiraswasta": echo "Gaji       : Rp 4.000.000";break;
    }
?>
```
<p> outputnya adalah <p>

![gambar 2](ss/a.png)

<p>isi data <p>

![gambar 3](ss/b.png)

<p> klik kirim, maka hasilnya seperti ini <p>

![gambar 4](ss/c.png)

# Latihan

<h4> PHP Dasar <h4>

```php
<!DOCTYPE html>
<html lang="en">
<head>
 <meta charset="UTF-8">
 <title>PHP Dasar</title>
</head>
<body>
 <h1>Belajar PHP Dasar</h1>
 <?php
 echo "Hello World";
 ?>
</body>
</html>
```

![gambar 5](ss/1.png)

<h4> Variable PHP <h4>

```php
<!DOCTYPE  html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>PHP Dasar </title>
<head>
<body>
    <h1> Belajar PHP Dasar </h1>
    <h1> Menggunakan Varable </h1>
<?php
    echo "Hello World" ;
    echo "<br>";
    $nim = "312110469";
    $nama = 'Viena Dwi Putri Maulina';
    echo "NIM   : ". $nim . "<br>";
    echo "Nama  : " . $nama;
?>
</body>
</html>
```

![gambar 6](ss/2.png)

<h4> Predefine Variable

```php
<?php
echo 'Selamat Datang ' . $_GET['nama'];
?>
```
<p> untuk mengaksesnya gunakan URL http://localhost/lab2_php_dasar/latihan/Predefine_varible.php?nama=Vien <p>

![gambar 7](ss/3.png)

<h4> Form Input <h4>

```php
<!DOCTYPE html>
<html lang="en">
<head>
 <meta charset="UTF-8">
 <title>PHP Dasar</title>
</head>
<body>
<h2>Form Input</h2>
<form method="post">
 <label>Nama: </label>
 <input type="text" name="nama">
 <input type="submit" value="Kirim">
</form>
<?php
echo 'Selamat Datang ' . $_POST['nama'];
?>
</body>
</html>
```

![gambar 8](ss/4.png)

<h4> Operator <h4>

```php
<?php
$gaji = 1000000;
$pajak = 0.1;
$thp = $gaji - ($gaji*$pajak);
echo "Gaji sebelum pajak = Rp. $gaji <br>";
echo "Gaji yang dibawa pulang = Rp. $thp";
?>
```

![gambar 9](ss/5.png)

<h4> Kondisi If <h4>

```php
<?php
$nama_hari = date("l");
if ($nama_hari == "Sunday") {
    echo "Minggu";
} elseif ($nama_hari == "Monday") {
    echo "Senin";
} else {
    echo "Selasa"; }
?>
```
![gambar 11](ss/6.png)

<h4> Kondisi Switch <h4>

```php
<?php
$nama_hari = date("l");
switch ($nama_hari) {
    case "Sunday":
        echo "Minggu";
        break;
    case "Monday":
        echo "Senin";
        break;
    case "Tuesday":
        echo "Selasa";
        break;
    default:
        echo "Sabtu";
     }
?>
 ```
 ![gambar 10](ss/7.png)
 
 <h4> Perulangan For <h4>
 
 ```php
 <?php
echo "Perulangan 1 sampai 10 <br />";
for ($i=1; $i<=10; $i++) {
    echo "Perulangan ke: " . $i . '<br />'; 
}

echo "Perulangan Menurun dari 10 ke 1 <br />";
for ($i=10; $i>=1; $i--) {
    echo "Perulangan ke: " . $i . '<br />'; 
}
?>
```

![gambar 11](ss/8.png)

<h4> Perulangan While <h4>

```php
<?php
echo "Perulangan 1 sampai 10 <br />";
$i=1;
while ($i<=10) {
    echo "Perulangan ke: " . $i . '<br />';
    $i++;
}
?>
```

![gambar 12](ss/9.png)

<h4> Perulangan Dowhile <h4>
 
 ```php
 <?php
echo "Perulangan 1 sampai 10 <br />";
$i=1;
do {
 echo "Perulangan ke: " . $i . '<br />';
 $i++;
} while ($i<=15);
?>
```
![gambar](ss/10.png)
