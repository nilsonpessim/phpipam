![TechLabs](https://techlabs.net.br/wp-content/uploads/2021/09/logo_blog.png)

# :rocket: PHPIPAM

### Instalação do Gestor de IPS PHPIPAM

---

* Preparação do Ambiente - Ubuntu 18.04:
```
apt -y update && apt -y upgrade
```
---

* Instalação do Servidor Web - Apache2:
```
apt -y install apache2 apache2-utils
a2enmod rewrite
a2enmod headers
systemctl restart apache2
```
---

* Instalação do Bando de Dados - MariaDB:
```
apt -y install mariadb-server mariadb-client
```
---

* Instalação do PHP - Versão 7:
```
apt -y install libapache2-mod-php php php-mysql php-cli php-pear php-gmp php-gd php-bcmath php-mbstring php-curl php-xml php-zip
systemctl restart apache2
```
---

* Criar a Base de Dados:
```
mariadb -p
CREATE DATABASE phpipam;
GRANT ALL PRIVILEGES ON phpipam.* TO 'phpipam'@'localhost' IDENTIFIED BY 'phpipamadmin';
FLUSH PRIVILEGES;
quit;
```
---

* Instalando PHPIPAM - Versão 1.5.0: https://github.com/phpipam/phpipam/releases
```
cd /tmp
wget https://github.com/phpipam/phpipam/releases/download/v1.5.0/phpipam-v1.5.0.tgz
tar vxf phpipam-v1.5.0.tgz
mv phpipam/* /var/www/html/
rm /var/www/html/index.html
```
---

* Ajuste de Permissões:
```
find /var/www/* -type d -exec chmod 755 {} \;
find /var/www/* -type f -exec chmod 644 {} \;
```

--- 

* Arquivo de Configurações
```
cd /var/www/html/
cp config.dist.php config.php
nano config.php

$db['host'] = '127.0.0.1';
$db['user'] = 'phpipam';
$db['pass'] = 'phpipamadmin';
$db['name'] = 'phpipam';
$db['port'] = 3306;
```
---

### Acesse seu servidor através do IP no navegador Web para finalizar as configurações

#### Nova instalação do PHPIPAM
![img.png](assets/img.png)

---

#### Instalação automática
![img_1.png](assets/img_1.png)

---

#### Informe os dados de conexão ao banco de dados, em opções avançadas, deixe todos desmarcados.
![img_2.png](assets/img_2.png)

---

#### Clique em Continue
![img_3.png](assets/img_3.png)

---

#### Informe a senha de Admin
![img_4.png](assets/img_4.png)

---

#### Acesse o painel, Usuário Padrão: Admin
![img_5.png](assets/img_5.png)

---

## :sparkling_heart: Nos Ajude a Crescer
>Se este Material foi útil para você, ajude se inscrevendo no meu canal do YouTube.
>
>(https://youtube.com/techlabs94?sub_confirmation=1)
> 
>Isso me incentiva a trazer mais materiais como este e muitos outros de redes e tecnologia.
> 
>## ![YouTube Channel Subscribers](https://img.shields.io/youtube/channel/subscribers/UCWN6suTq5sZGqnSLos992Yw?style=social)

## :iphone: Contato e Informações
[![Whatsapp Badge](https://img.shields.io/badge/-Whatsapp-4CA143?style=flat-square&labelColor=4CA143&logo=whatsapp&logoColor=white&link=https://api.whatsapp.com/send?phone=5537999351046)](https://api.whatsapp.com/send?phone=5537999351046)