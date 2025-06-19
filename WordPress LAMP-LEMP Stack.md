# Triển khai ứng dụng web trên Ubuntu LAMP Stack
## 1.LAMP
### 1.1.LAMP là gì?
- LAMP là viết tắt của Linux, Apache, MySQL và PHP. Các thành phần này, được sắp xếp theo các lớp hỗ trợ lẫn nhau, tạo thành các stack phần mềm. Các website và ứng dụng web chạy trên nền tảng của các stack cơ bản này.
  - Linux: là lớp đầu tiên trong stack. Hệ điều hành này là cơ sở nền tảng cho các lớp phần mềm khác.
  - Apache: Lớp thứ hai bao gồm phần mềm web server, thường là Apache Web (HTTP) Server. Lớp này nằm trên lớp Linux. Web server chịu trách nhiệm chuyển đổi các web browser sang các website chính xác của chúng. Apache đã (và vẫn) là ứng dụng web server phổ biến nhất trên public Internet hiện nay. Trên thực tế, Apache được ghi nhận là đóng một vai trò quan trọng trong sự phát triển ban đầu của World Wide Web.
  - MySQL: Lớp thứ ba là nơi cơ sở dữ liệu database được lưu trữ. MySQL lưu trữ các chi tiết có thể được truy vấn bằng script để xây dựng một website. MySQL thường nằm trên Linux và cùng với Apache / lớp 2. Trong cấu hình highend, MySQL có thể được off load xuống 1 máy chủ lưu trữ riêng biệt.
  - PHP: là lớp trên cùng của stack. Lớp script bao gồm PHP và / hoặc các ngôn ngữ lập trình web tương tự khác. Các website và ứng dụng web chạy trong lớp này.
### 1.2.Cài đặt
- **Thực hiện triển khai cài LAMP Stack trên Ubuntu 22.04**
  - Cập nhật ubuntu
  - ```bash
    sudo apt update && sudo apt upgrade -y
    ```
  - ![image](https://github.com/user-attachments/assets/06b5bd55-b042-4c26-9a7b-6c3813c6afa0)
- **Cài đặt Apache Webserver**
  - ```bash
    sudo apt install apache2 -y
    ```
  - ![image](https://github.com/user-attachments/assets/e5ceacd7-a8e8-411d-bbc5-9a2712431486)
  - Kiểm tra xem cài đặt thành công chưa, mở trình duyệt truy cập: http://<IP-của-Ubuntu>
  - ![image](https://github.com/user-attachments/assets/0d9bf519-116d-472f-ae73-844de3232703)
- **Cài đặt MySQL**
  - ```bash
    sudo apt install mysql-server -y
    ```
  - ![image](https://github.com/user-attachments/assets/e458a0b6-2851-4fca-8ade-bbb37a36e6c3)
  - Cài đặt bảo mật
  - ```bash
    sudo mysql_secure_installation
    ```
- **Cài PHP + module cần thiết**
  - ```
    sudo apt install php libapache2-mod-php php-mysql php-curl php-xml php-gd php-mbstring -y
    ```
  - ![image](https://github.com/user-attachments/assets/8c5cd6f7-4144-4101-a7bf-59e05baed888)
  - Kiểm tra xem PHP đã cài thành công chưa
  - ```bash
    php -v
    ```
  - ![image](https://github.com/user-attachments/assets/f38e140d-9780-46d0-9790-a83e7f20aada)
- **Cài đặt WordPress**
  - Tạo database cho WordPress
  - ```bash
    sudo mysql -u root -p
    ```
  - ![image](https://github.com/user-attachments/assets/6dd2a337-e06e-4768-984f-4918b73baefb)
  - ```sql
    CREATE DATABASE wordpress_db DEFAULT CHARACTER SET utf8 COLLATE utf8_unicode_ci;
    CREATE USER 'wp_user'@'localhost' IDENTIFIED BY 'Qaz123456@';
    GRANT ALL PRIVILEGES ON wordpress_db.* TO 'wp_user'@'localhost';
    FLUSH PRIVILEGES;
    EXIT;
    ```
  - ![image](https://github.com/user-attachments/assets/35576af3-be94-4f8c-a514-5a847be82778)
  - Tải WordPress
  - ```bash
    cd /tmp
    wget https://wordpress.org/latest.tar.gz
    tar -xvzf latest.tar.gz
    ```
  - ![image](https://github.com/user-attachments/assets/260b15fa-5134-45cc-9436-39741e066400)
  - Di chuyển vào thư mục web
  - ```bash
    sudo rm -rf /var/www/html/*
    sudo mv wordpress/* /var/www/html/
    ```
  - ![image](https://github.com/user-attachments/assets/851ba453-3cb9-444b-a447-43d321df72d8)
  - Cấp quyền thư mục
  - ```bash
    sudo chown -R www-data:www-data /var/www/html
    sudo chmod -R 755 /var/www/html
    ```
  - ![image](https://github.com/user-attachments/assets/0cd6277b-8b82-41ac-95ef-f83575dd3e9c)
  - Tạo file cấu hình WordPress
    - Di chuyển vào thư mục /var/www/html
    - ```bash
      cd /var/www/html
      ``` 
    - ```bash
      sudo cp wp-config-sample.php wp-config.php
      ```
    - ![image](https://github.com/user-attachments/assets/a054a5ee-f980-45b2-972d-4084cfe58196)
  - Sửa wp-config.php
  - ```bash
    sudo nano wp-config.php
    ```
  - ![image](https://github.com/user-attachments/assets/07ff0a3c-df45-44f8-915c-fff500466307)
  - Khởi động lại Apache
  - ```bash
    sudo systemctl restart apache2
    ```
  - ![image](https://github.com/user-attachments/assets/8bba73da-ecfd-4ce3-8412-19b95ea3b7ed)
- **Kiểm thử**
  - Mở trình duyệt truy cập: http://<IP-của-Ubuntu>
  - ![image](https://github.com/user-attachments/assets/5f7a8c20-f9ab-4f97-a8b7-358d7950409a)
  - ![image](https://github.com/user-attachments/assets/81935e74-a329-428c-b22b-9a505b329a83)
  - ![image](https://github.com/user-attachments/assets/bbaca275-bd81-481c-8e8f-bc7b1b0c963e)
## 2.LEMP
### 2.1.LEMP là gì ?
- Tương tự như LAMP nhưng E ở đây là Nignx
### 2.2.Cài đặt
- **Cài đặt Nginx**
  - ```bash
    sudo apt update
    sudo apt install nginx
    ```
  - ![image](https://github.com/user-attachments/assets/83d520d7-d7b5-4306-9805-6c47e3452ee3)
  - Nếu như đã cấu hình LAMP thì cần tắt Apache hoặc chuyển Apache sang cổng khác
  - Tắt Apache
  - ```bash
    sudo systemctl stop apache2
    sudo systemctl disable apache2
    ```
  - Thay đổi cổng của Apache (mặc định là 80) trong file cấu hình
  - ```bash
    sudo nano /etc/apache2/ports.conf
    sudo nano /etc/apache2/sites-enabled/000-default.conf
    ```
  - ![image](https://github.com/user-attachments/assets/0966e7bd-6cff-4524-972d-c125f9f4177f)
  - Đổi từ VirtualHost *:80 thành ví dụ *:8080
  - `sudo systemctl restart apache2`
- **Cài PHP và module PHP-FPM (cho Nginx)**
  - Nginx không dùng mod_php như Apache, mà dùng PHP-FPM (FastCGI Process Manager)
  - `sudo apt install php-fpm php-mysql`
- **Cấu hình Nginx để xử lý file PHP
  - `sudo nano /etc/nginx/sites-available/default`
  - ![image](https://github.com/user-attachments/assets/31ffd0e9-4599-406e-a16c-be879d0fb2c3)
  - Thêm (hoặc sửa) đoạn sau trong server { ... }:
  - ```bash
    location ~ \.php$ {
        include snippets/fastcgi-php.conf;
        fastcgi_pass unix:/run/php/php8.1-fpm.sock;  # tùy phiên bản PHP
    }
    ```
  - Kiểm tra cấu hình
  - `sudo nginx -t`
  - `sudo systemctl restart nginx`
  - 
## 3.Bash Script với LAMP/LEMP
### 3.1.Bash Script với LAMP
- Việc viết bash script cài đặt LAMP là để tự động hóa toàn bộ quá trình cài đặt Linux, Apache, MySQL, PHP thay vì làm thủ công từng lệnh.
#### Mục tiêu: Tạo 1 file script .sh để:
- Cài Apache, MySQL, PHP
- Khởi động dịch vụ
- Tải và triển khai WordPress
- Cấu hình quyền thư mục
#### Triển khai
- Tạo file script: install-lamp-wordpress.sh
```
#!/bin/bash

# Cập nhật hệ thống
sudo apt update -y
sudo apt upgrade -y

# Cài Apache
sudo apt install apache2 -y
sudo systemctl enable apache2
sudo systemctl start apache2

# Cài MySQL
sudo apt install mysql-server -y
sudo systemctl enable mysql
sudo systemctl start mysql

# Cài PHP và các extension
sudo apt install php libapache2-mod-php php-mysql php-cli php-curl php-xml php-mbstring php-zip php-gd -y

# Tạo database và user cho WordPress
DB_NAME="wordpress_db"
DB_USER="wp_user"
DB_PASS="123456"

sudo mysql -e "CREATE DATABASE IF NOT EXISTS ${DB_NAME};"
sudo mysql -e "CREATE USER IF NOT EXISTS '${DB_USER}'@'localhost' IDENTIFIED BY '${DB_PASS}';"
sudo mysql -e "GRANT ALL PRIVILEGES ON ${DB_NAME}.* TO '${DB_USER}'@'localhost';"
sudo mysql -e "FLUSH PRIVILEGES;"

# Tải WordPress
cd /tmp
wget https://wordpress.org/latest.tar.gz
tar -xzf latest.tar.gz

# Copy vào thư mục web
sudo rm -rf /var/www/html/*
sudo cp -r wordpress/* /var/www/html/
sudo chown -R www-data:www-data /var/www/html
sudo chmod -R 755 /var/www/html

# Tạo file cấu hình WordPress
cd /var/www/html
sudo cp wp-config-sample.php wp-config.php

# Sửa thông tin database trong wp-config.php
sudo sed -i "s/database_name_here/${DB_NAME}/" wp-config.php
sudo sed -i "s/username_here/${DB_USER}/" wp-config.php
sudo sed -i "s/password_here/${DB_PASS}/" wp-config.php

```

#### Cách sử dụng:
##### Cấp quyền chạy
- `chmod +x install-lamp-wordpress.sh`
##### Chạy script:
- `./install-lamp-wordpress.sh`

### 3.2.Bash Script với LEMP
- Tạo file script: install-lemp-wordpress.sh
#### Triển khai
```
#!/bin/bash

# Cập nhật hệ thống
sudo apt update -y
sudo apt upgrade -y

# Cài Nginx
sudo apt install nginx -y
sudo systemctl enable nginx
sudo systemctl start nginx

# Cài MySQL
sudo apt install mysql-server -y
sudo systemctl enable mysql
sudo systemctl start mysql

# Cài PHP và các module cần thiết
sudo apt install php-fpm php-mysql php-cli php-curl php-xml php-mbstring php-zip php-gd -y

# Tạo database và user cho WordPress
DB_NAME="wordpress_db"
DB_USER="wp_user"
DB_PASS="123456"

sudo mysql -e "CREATE DATABASE IF NOT EXISTS ${DB_NAME};"
sudo mysql -e "CREATE USER IF NOT EXISTS '${DB_USER}'@'localhost' IDENTIFIED BY '${DB_PASS}';"
sudo mysql -e "GRANT ALL PRIVILEGES ON ${DB_NAME}.* TO '${DB_USER}'@'localhost';"
sudo mysql -e "FLUSH PRIVILEGES;"

# Tải và cài WordPress
cd /tmp
wget https://wordpress.org/latest.tar.gz
tar -xzf latest.tar.gz

# Copy vào thư mục web
sudo rm -rf /var/www/html/*
sudo cp -r wordpress/* /var/www/html/
sudo chown -R www-data:www-data /var/www/html
sudo chmod -R 755 /var/www/html

# Tạo file cấu hình WordPress
cd /var/www/html
sudo cp wp-config-sample.php wp-config.php
sudo sed -i "s/database_name_here/${DB_NAME}/" wp-config.php
sudo sed -i "s/username_here/${DB_USER}/" wp-config.php
sudo sed -i "s/password_here/${DB_PASS}/" wp-config.php

# Cấu hình Nginx cho WordPress
NGINX_CONF="/etc/nginx/sites-available/wordpress"
PHP_SOCKET=$(find /run/php/ -name "php*-fpm.sock" | head -n 1)

sudo tee "$NGINX_CONF" > /dev/null <<EOF
server {
    listen 80;
    server_name _;

    root /var/www/html;
    index index.php index.html index.htm;

    location / {
        try_files \$uri \$uri/ /index.php?\$args;
    }

    location ~ \.php\$ {
        include snippets/fastcgi-php.conf;
        fastcgi_pass unix:${PHP_SOCKET};
    }

    location ~ /\.ht {
        deny all;
    }
}
EOF

# Kích hoạt config và khởi động lại nginx
sudo ln -s /etc/nginx/sites-available/wordpress /etc/nginx/sites-enabled/
sudo rm /etc/nginx/sites-enabled/default
sudo nginx -t && sudo systemctl reload nginx

```
#### Cách sử dụng:
##### Cấp quyền chạy
- `chmod +x install-lemp-wordpress.sh`
##### Chạy script:
- `./install-lemp-wordpress.sh`
