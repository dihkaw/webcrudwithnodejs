# Langkah Deploy nodejs di Amazon Web Service

## Install Dependency
```bash
npm install --prefix
```

## Config Environment
1. Buat file .env pada folder aplikasi
2. Tambahkan kebutuhan untuk mengkoneksikan database seperti hostname, user, password, dan nama database seperti berikut :
```javascript
DB_HOST = YOUR ENDPOINT
DB_USER = YOUR USERNAME
DB_PASSWORD = YOUR PASSWORD
DB_DATABASE = YOUR DATABASE
NODE_ENV = production
```

## Config Database
1. Buat cluster database menggunakan RDS dari Amazon Aurora MySQL atau MySQL
2. Akses cluster database tersebut menggunakan tambahan software seperti [**HeidiSQL**](https://www.heidisql.com/download.php)
3. Buat database dengan nama "barang"
4. Buat tabel menggunakan perintah berikut ini :
```javascript
CREATE TABLE IF NOT EXISTS `product` (
`product_id` int(11) NOT NULL AUTO_INCREMENT,
`product_name` varchar(200) DEFAULT NULL,
`product_price` int(11) DEFAULT NULL,
PRIMARY KEY (`product_id`)
) ENGINE=InnoDB  DEFAULT CHARSET=latin1 AUTO_INCREMENT=6 ;
```

6. Tambahkan data pada tabel product dengan perintah berikut :
```javascript
INSERT INTO `product` (`product_id`, `product_name`, `product_price`) VALUES
(1, 'Product 1', 2000),
(2, 'Product 2', 2000),
(3, 'Product 3', 3000),
(4, 'Product 4', 2000),
(5, 'Product 5', 1500);
```
## Untuk menjalankan program
```bash
npm run start-prod
```
## Test Program
buka browser dan masukan IP Address Anda dan portnya seperti berikut: http://localhost:8000

source [Handi Pradana](https://github.com/pradanahandi/nodejsbasic)
