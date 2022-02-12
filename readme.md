## MariaDB Docker Starter
Ini adalah starter untuk membuat db server MariaDB

#### Instalasi
Clone repo ini dan Cukup jalankan perintah di bawah

```
docker compose build && docker compose up -d
```

Jika sudah dibuild, cukup jalankan ini saja

```
docker compose up -d
```

#### Akses dari container docker lain
Untuk mengakses MariaDB di sini, tambahkan networks seperti di bawah ini di `docker-compose.yml` projek lain

```
networks:
  mariadb_default:
    external: true
```

Kemudian di servicenya tinggal tambah

```
networks:
 - mariadb_default
```

Dan akses host nya diset `mariadb`

Nama network disesuaikan dengan nama yang diset di docker compose MariaDB nya.

#### Jika ingin menjalankan dari local
Cukup akses db kredensial ini

```
host = localhost
port = 3306
user = root
password =
```
