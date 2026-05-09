README
Praktikum MySQL Procedure dan Perulangan WHILE
Identitas Mahasiswa
Nama: Mifta Auliya
NIM: IK2411028
1. Pendahuluan

Praktikum ini bertujuan untuk mempelajari penggunaan Stored Procedure dan struktur perulangan WHILE pada MySQL.
Stored Procedure digunakan untuk menyimpan sekumpulan perintah SQL yang dapat dijalankan kembali dengan mudah. Sedangkan perulangan WHILE digunakan untuk menjalankan proses secara berulang selama kondisi bernilai benar.

2. Tujuan Praktikum
Memahami penggunaan CREATE PROCEDURE.
Memahami penggunaan perulangan WHILE.
Menjalankan prosedur menggunakan CALL.
Menampilkan hasil perulangan pada MySQL.
3. Software yang Digunakan
XAMPP
MySQL / MariaDB
Visual Studio Code (opsional)
4. Langkah-Langkah Pengerjaan
A. Membuat Procedure Menghitung Total Angka 1–20
Kode Program
DELIMITER $$

CREATE PROCEDURE hitung_total()
BEGIN
    DECLARE v_counter INT DEFAULT 1;
    DECLARE v_total INT DEFAULT 0;

    WHILE v_counter <= 20 DO
        SET v_total = v_total + v_counter;
        SET v_counter = v_counter + 1;
    END WHILE;

    SELECT v_total AS total;
END$$

DELIMITER ;
Menjalankan Procedure
CALL hitung_total();
Hasil

Total penjumlahan angka 1 sampai 20 adalah 210.

B. Membuat Procedure Total Belanja Sampai Rp500.000
Kode Program
DELIMITER $$

CREATE PROCEDURE total_belanja()
BEGIN
    DECLARE v_total INT DEFAULT 0;

    WHILE v_total < 500000 DO
        SET v_total = v_total + 50000;
        SELECT v_total AS total_belanja;
    END WHILE;
END$$

DELIMITER ;
Menjalankan Procedure
CALL total_belanja();
Hasil

Program akan menampilkan total belanja bertambah Rp50.000 hingga mencapai Rp500.000.

C. Membuat Procedure Menampilkan Bilangan Genap 2–20
Kode Program
DELIMITER $$

CREATE PROCEDURE bilangan_genap()
BEGIN
    DECLARE i INT DEFAULT 2;

    WHILE i <= 20 DO
        SELECT i AS bilangan_genap;
        SET i = i + 2;
    END WHILE;
END$$

DELIMITER ;
Menjalankan Procedure
CALL bilangan_genap();
Hasil

Program menampilkan bilangan genap dari 2 sampai 20.

5. Kesimpulan

Dari praktikum ini dapat disimpulkan bahwa:

Stored Procedure mempermudah penyimpanan dan penggunaan kembali perintah SQL.
Perulangan WHILE digunakan untuk menjalankan proses berulang sesuai kondisi.
DELIMITER diperlukan agar MySQL dapat membaca procedure dengan benar.
Procedure dapat dijalankan menggunakan perintah CALL.
6. Penutup

Demikian README praktikum MySQL ini dibuat sebagai dokumentasi hasil pengerjaan procedure dan perulangan WHILE.
