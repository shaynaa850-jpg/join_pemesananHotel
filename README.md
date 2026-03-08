<div align="center">

# ✨ DB PEMESANAN HOTEL ✨
### Made by shayna difitri.r 💙

<img src="https://raw.githubusercontent.com/shaynaa850-jpg/join_pemesananHotel/main/s-l1200.jpg" width="800">

![Database](https://img.shields.io/badge/Database-MySQL-orange)
![Project](https://img.shields.io/badge/Project-Hotel-blue)
![Author](https://img.shields.io/badge/Author-shayna-pink)

</div>

---

## 📌 Project Overview

Project ini merupakan **database pemesanan hotel** yang dibuat menggunakan **MySQL**.  
Database ini digunakan untuk mengelola data pelanggan, kamar hotel, serta pemesanan kamar.

Database ini terdiri dari **3 tabel utama**, yaitu:

- tb_pelanggan
- tb_kamar
- tb_pemesanan

---

## ⭐ Features

✔ Membuat Database  
✔ Membuat Table  
✔ Insert Data  
✔ INNER JOIN  
✔ LEFT JOIN  
✔ RIGHT JOIN  

---

# 💻 SQL Script (Command Prompt)

## 1️⃣ Membuat Database

```sql
CREATE DATABASE db_pemesanan_hotel;
USE db_pemesanan_hotel;
```

---

## 2️⃣ Membuat Table Pelanggan

```sql
CREATE TABLE tb_pelanggan (
id_pelanggan INT AUTO_INCREMENT PRIMARY KEY,
nama_pelanggan VARCHAR(100),
no_hp VARCHAR(15),
alamat TEXT
);
```

---

## 3️⃣ Membuat Table Kamar

```sql
CREATE TABLE tb_kamar (
id_kamar INT AUTO_INCREMENT PRIMARY KEY,
nomor_kamar VARCHAR(10),
tipe_kamar VARCHAR(50),
harga INT
);
```

---

## 4️⃣ Membuat Table Pemesanan

```sql
CREATE TABLE tb_pemesanan (
id_pemesanan INT AUTO_INCREMENT PRIMARY KEY,
id_pelanggan INT,
id_kamar INT,
tanggal_checkin DATE,
tanggal_checkout DATE,
FOREIGN KEY (id_pelanggan) REFERENCES tb_pelanggan(id_pelanggan),
FOREIGN KEY (id_kamar) REFERENCES tb_kamar(id_kamar)
);
```

---

# 📥 Insert Data

## Data Pelanggan

```sql
INSERT INTO tb_pelanggan (nama_pelanggan, no_hp, alamat) VALUES
('Ainaa','08123456789','Jakarta'),
('Budi','08234567890','Bandung'),
('Citra','08345678901','Surabaya');
```

---

## Data Kamar

```sql
INSERT INTO tb_kamar (nomor_kamar, tipe_kamar, harga) VALUES
('101','Standard',300000),
('102','Deluxe',500000),
('103','Suite',800000);
```

---

## Data Pemesanan

```sql
INSERT INTO tb_pemesanan (id_pelanggan,id_kamar,tanggal_checkin,tanggal_checkout) VALUES
(1,2,'2026-03-01','2026-03-03'),
(2,1,'2026-03-02','2026-03-04');
```

---

# 🔗 JOIN Query

## INNER JOIN

```sql
SELECT p.nama_pelanggan, k.nomor_kamar, pm.tanggal_checkin
FROM tb_pemesanan pm
INNER JOIN tb_pelanggan p
ON pm.id_pelanggan = p.id_pelanggan
INNER JOIN tb_kamar k
ON pm.id_kamar = k.id_kamar;
```

---

## LEFT JOIN

```sql
SELECT p.nama_pelanggan, k.nomor_kamar
FROM tb_pelanggan p
LEFT JOIN tb_pemesanan pm
ON p.id_pelanggan = pm.id_pelanggan
LEFT JOIN tb_kamar k
ON pm.id_kamar = k.id_kamar;
```

---

## RIGHT JOIN

```sql
SELECT p.nama_pelanggan, k.nomor_kamar
FROM tb_pemesanan pm
RIGHT JOIN tb_kamar k
ON pm.id_kamar = k.id_kamar
LEFT JOIN tb_pelanggan p
ON pm.id_pelanggan = p.id_pelanggan;
```

---

<div align="center">

✨ Project Database Practice ✨  
💙 Made with effort by **shayna**

</div>
