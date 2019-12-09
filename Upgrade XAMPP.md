# BACKUP DATABASE MYSQL 
- Masuklah ke folder instalasi XAMPP, biasanya terdapat di c:\xampp, lalu carilah file dengan nama xampp-control;
- Lalu klik kanan -> Run as Administrator, hingga muncul XAMPP Control Panel;
- Pada XAMPP Control Panel, klik tombol Shell;
- Pada Command Prompt Shell untuk backup database: 
<pre>
mysqldump -u root -p --all-databases > backup-db-09122019.sql
</pre>
Perintah diatas akan membuat sebuah file dengan nama backup-db-09122019.sql yang berisi semua database yang Anda punya pada databaseMySQL. File ini terdapat pada folder xampp Anda, Pastikan kamu sudah menjalankan mysql + apache;
- Langkah berikutnya adalah stop Apache dan MySQL melalui XAMPP Control Panel;
- Klik tombol quit pada XAMPP Control Panel, dan tutup juga Command Prompt Shell;
- Lalu ganti nama folder xampp menjadi xampp-old. Cara ini memungkinkan kita kembali ke versi yang lama jika terjadi hal-hal yang tidak diinginkan.
# INSTALL XAMPP BARU 
- Download versi terbaru dari XAMPP pada Web Apache Friends, <a href="https://www.apachefriends.org/index.html" target="_blank">Klik disini </a>;
- Instalasi XAMPP yang telah di download pada folder yang sama dengan xampp versi lama yang telah diubah nama folder-nya;
- Setelah instalasi selesai, masuklah ke dalam folder xampp lalu jalankan XAMPP Control Panel (Run as Administrator);
- Setelah XAMPP Control Panel muncul, tombol start pada Apache dan MySQL agar keduanya aktif.
- Cek Apache berjalan dengan baik dengan buka browser, lalu ketik http://localhost ;
- Cek juga apakah database berjalan dengan baik dengan membuka browser, lalu ketik http://localhost/phpmyadmin/
- Setelah itu, copy folder htdocs dari folder xampp-old ke folder xampp;
- Langkah selanjutnya adalah import database. Anda dapat import databasemelalui CLI (Command Line Interface) agar lebih mudah untuk import database yang sangat besar.
- bukalah filexampp\php\php.ini 
- Setelah php.ini terbuka, perbesarlah nilai pada opsi <b> upload_max_filesize, memory_limit, post_max_size. Sebagai catatan, post_max_size dan memory_limit nilainya harus lebih besar dari upload_max_filesize </b>. Hal ini memungkinkan file besar dapat di upload ke server, setelah diubah nilainya lalu file tersebut disimpan;
- Bukalah file xampp\phpMyAdmin\libraries\config.default.php dengan editor kesukaan Anda, carilah opsi $cfg['ExecTimeLimit'] = 600, lalu ubahlah nilai dari 600 ke nilai yang lebih tinggi sebagai contoh 6000, lalu file tersebut disimpan;
- Setelah itu, restart Apache dan MySQL melalui XAMPP Control Panel;
- Setelah Apache dan MySQL Aktif, buka browser lalu ketik http://localhost/phpmyadmin/, lalu klik tab import;
- Import file database backup-db-09122019.sql;
- Jika telah selesai maka akan terdapat pesan, “Import has been successfully finished“; 
- Setelah itu, buka Command Prompt Shell lalu jalankan perintah mysql_upgrade;
- Jika semuanya telah berjalan dengan baik, Anda dapat menghapus folder xampp-old;

## Sumber Referensi 
- https://www.trentech.id
- Asif Rahaman
