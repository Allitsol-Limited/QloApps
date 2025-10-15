<div align="center">
	<a href="https://www.qloapps.com"><img src="https://forums.qloapps.com/assets/uploads/system/site-logo.png?v=hkl8e1230fo" alt="QloApps"></a>
	<br>
	<p>
		<b>QloApps - An open source and free platform to launch your own hotel booking website</b>
	</p>
</div>

<p align="center">
	<a href="https://qloapps.com/download/"><img src="https://img.shields.io/badge/Download-Download%20QloApps%20-brightgreen" alt="Download"></a>
	<a href="https://docs.qloapps.com/"><img src="https://img.shields.io/badge/Documentation-Blog-yellowgreen" alt="Documentation"></a>
	<a href="https://forums.qloapps.com/"><img src="https://img.shields.io/badge/Forum-Help%2FSupport-green" alt="Forum"></a>
	<a href="https://qloapps.com/addons/"><img src="https://img.shields.io/badge/Addons-Plugins-blueviolet" alt="Addons"></a>
	<a href="https://qloapps.com/contact/"><img src="https://img.shields.io/badge/Contact-Get%20In%20Touch-blue" alt="Contact us"></a>
	<a href="/LICENSE.md"><img src="https://img.shields.io/badge/License-OSL%20V3-green" alt="License"></a>
</p>

## Topics

- [Topics](#topics)
  - [Introduction](#introduction)
  - [Requirements](#requirements)
    - [Hosted Server Configurations](#hosted-server-configurations)
    - [Local Server Configurations](#local-server-configurations)
  - [Installation and Configuration](#installation-and-configuration)
  - [License](#license)
  - [Security Vulnerabilities](#security-vulnerabilities)
  - [Documentation \& Demo](#documentation--demo)
    - [QloApps Documentation](#qloapps-documentation)
    - [QloApps Demo](#qloapps-demo)
  - [Contribute](#contribute)
  - [Credits](#credits)

### Introduction

QloApps is one kind of a true open-source hotel reservation system and a booking engine. The system is dedicated to channeling the power of the open-source community to serve the hospitality industry.

From small independent hotels to big hotel chains, QloApps is a one-stop solution for all your hotel business needs.

You will be able to launch your hotel website, showcase your property and take and manage bookings.

### Requirements

In order to install QloApps you will need the following server configurations for hosted and local serves.
The system compatibility will also be checked by the system with installation and if the server is not compatible then the installation will not move ahead.

#### Hosted Server Configurations

- **Web server**: Apache 1.3, Apache 2.x, Nginx or Microsoft IIS
- **PHP version**: PHP 8.1+ to PHP 8.4
- **MySQL version**: 5.7+ to 8.4 installed with a database created
- SSH or FTP access (ask your hosting service for your credentials)
- In the PHP configuration ask your provider to set memory_limit to "128M", upload_max_filesize to "16M" , max_execution_time to "500" and allow_url_fopen "on"
- SSL certificate if you plan to process payments internally (not using PayPal for instance)
- **Required PHP extensions**: PDO_MySQL, cURL, OpenSSL, SOAP, GD, SimpleXML, DOM, Zip, Phar

#### Local Server Configurations

- **Supported operating system**: Windows, Mac, and Linux
- **A prepared package**: WampServer (for Windows), Xampp (for Windows and Mac) or EasyPHP (for Windows)
- **Web server**: Apache 1.3, Apache 2.x, Nginx or Microsoft IIS
- **PHP**: PHP 8.1+ to PHP 8.4
- **MySQL** 5.7+ to 8.4 installed with a database created
- In the PHP configuration, set memory_limit to "128M", upload_max_filesize to "16M" and max_execution_time to "500"
- **Required PHP extensions**: PDO_MySQL, cURL, OpenSSL, SOAP, GD, SimpleXML, DOM, Zip, Phar

### Installation and Configuration

**1.** You can install QloApps easily after downloading QloApps. There are easy steps for the installation process. Please visit [QloApps Installation Guide](https://qloapps.com/install-qloapps/) and follow the steps for the successful installation.

**2.** Or you can install QloApps with docker image. For the docker image of QloApps, please visit [Dockerize image of QloApps](https://hub.docker.com/r/webkul/qloapps_docker) <br>

- Docker pull command

```
docker pull webkul/qloapps_docker
```

### License

QloApps Core is licensed under OSL-3.0 and Modules authored by Webkul have their applicable license, LICENSE.md, kept inside their root directories, while other modules are licensed under AFL-3.0.

The online copy of OSL-3.0 can be found at [https://opensource.org/licenses/OSL-3.0](https://opensource.org/licenses/OSL-3.0).

The online copy of AFL-3.0 can be found at [https://opensource.org/licenses/AFL-3.0](https://opensource.org/licenses/AFL-3.0).

### Security Vulnerabilities

Please don't disclose security vulnerabilities publicly. If you find any security vulnerability in QloApps then please email us: mailto:support@qloapps.com.

### Documentation & Demo

#### QloApps Documentation

[https://docs.qloapps.com](https://docs.qloapps.com)

#### QloApps Demo

**Link** : https://demo.qloapps.com </br>
**username** : demo@demo.com </br>
**Password** : demodemo </br>

### Contribute

As a PHP developer who has command on PHP and MySQL and also knows how to use Git or GitHub efficiently, can contribute to code enhancements via pull requests.<br>
For more information about the contribution process please check **[Contribute to QloApps](/CONTRIBUTING.md)**

### Credits

Crafted with :heart: at [Webkul](https://webkul.com)

docker run -d -p 80:80 -p 33062:3306 webkul/qloapps_docker

CREATE DATABASE qloapps CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;

CREATE USER 'qloapps'@'localhost' IDENTIFIED BY 'qloapps123';
GRANT ALL PRIVILEGES ON qloapps.\* TO 'qloapps'@'localhost';
FLUSH PRIVILEGES;

CREATE USER 'root'@'%' IDENTIFIED BY 'qloapps123';
GRANT ALL PRIVILEGES ON qloapps.\* TO 'root'@'%';
FLUSH PRIVILEGES;
exit;

172.20.10.5

docker run -d \
 -p 80:80 \
 -e DB_SERVER="host.docker.internal:33062" \
 -e DB_NAME="qloapps" \
 -e DB_USER="root" \
 -e DB_PASSWD="your_password" \
 webkul/qloapps_docker

# Stop and remove current container

docker stop 583e529208ce
docker rm 583e529208ce

# Run new container with host network mode

docker run -d \
 -p 80:80 \
 --add-host=host.docker.internal:host-gateway \
 webkul/qloapps_docker

# Stop your current container

docker stop <container_id>
docker rm <container_id>

# Run with proper environment variables

docker run -d \
 -p 80:80 \
 -p 33062:3306 \
 --name qloapps \
 -e MYSQL_ROOT_PASSWORD=qloapps123 \
 -e MYSQL_DATABASE=qloapps \
 -e USER_PASSWORD=qloappsuserpassword \
 webkul/qloapps_docker:latest
qloapps123

127.0.0.1
for config to connect with workbench

docker exec -it qloapps mysql -u root -pqloapps123

CREATE USER 'root'@'172.17.0.1' IDENTIFIED BY 'qloapps123';
GRANT ALL PRIVILEGES ON _._ TO 'root'@'172.17.0.1' WITH GRANT OPTION;
FLUSH PRIVILEGES;
exit;

UPDATE qlo_employee
SET passwd = MD5(CONCAT('O1CMQ1HE8nK4nkrS', 'admin123'))
WHERE id_employee = 1;

docker exec -it qloapps rm -rf /home/qloapps/www/QloApps/admin

docker exec -it qloapps tail -100 /var/log/apache2/error.log
docker exec -it qloapps rm -rf /home/qloapps/www/QloApps/install

docker exec -it qloapps bash -c "cat > /home/qloapps/www/QloApps/test_login.php << 'EOF'

<?php
include('config/config.inc.php');
\$email = 'daveotengo@gmail.com';
\$password = 'admin123';
\$employee = new Employee();
\$result = \$employee->getByEmail(\$email);
echo 'Employee ID: ' . \$result . PHP_EOL;
\$emp = new Employee(\$result);
echo 'Email: ' . \$emp->email . PHP_EOL;
echo 'Password hash in DB: ' . \$emp->passwd . PHP_EOL;
echo 'Expected hash: ' . md5(_COOKIE_KEY_ . \$password) . PHP_EOL;
echo 'NW_SALT hash: ' . md5('O1CMQ1HE8nK4nkrS' . \$password) . PHP_EOL;
echo 'Active: ' . \$emp->active . PHP_EOL;
EOF"

docker exec -it qloapps mv /home/qloapps/www/QloApps/admin_new /home/qloapps/www/QloApps/admin_$(openssl rand -hex 4)


UPDATE qlo_employee 
SET passwd = '8ad70050fb6af931109c0641a4eae167'
WHERE email = 'daveotengo@gmail.com';

-- Also update the second user
UPDATE qlo_employee 
SET passwd = '8ad70050fb6af931109c0641a4eae167'
WHERE email = 'newadmin@test.com';

-- Verify
SELECT id_employee, email, passwd FROM qlo_employee;


-- You'd need to use the COOKIE_KEY hash
   INSERT INTO qlo_employee (id_profile, id_lang, lastname, firstname, email, passwd, active)
   VALUES (1, 1, 'Test', 'User', 'test@example.com', 
           MD5(CONCAT('HOL50NFpM2mOgzBkQh7JTVMLpXC7JJYfANMBJAMhZiuvdVxwehajHmCb', 'password123')), 
           1);


(base) daveotengo@localhost QloApps % docker exec -it qloapps grep -rn "passwd.*md5\|MD5.*passwd" /home/qloapps/www/QloApps/install/fixtures/

(base) daveotengo@localhost QloApps %
