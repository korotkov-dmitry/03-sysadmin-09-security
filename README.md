# Домашнее задание к занятию "3.9. Элементы безопасности информационных систем"

## 1. Установите Bitwarden плагин для браузера. Зарегестрируйтесь и сохраните несколько паролей.
![Bitwarden](https://user-images.githubusercontent.com/92984527/145699393-6c00647a-82ce-4ffe-aa70-0299569e2757.png)
## 2. Установите Google authenticator на мобильный телефон. Настройте вход в Bitwarden акаунт через Google authenticator OTP.
![BitwardenG](https://user-images.githubusercontent.com/92984527/145699775-838c2b78-4839-4025-8f1b-7f3581f61cf6.png)

![BitwardenG2](https://user-images.githubusercontent.com/92984527/145699766-49db815c-6b22-4177-ab4b-d7e72a9e1ded.png)
## 3. Установите apache2, сгенерируйте самоподписанный сертификат, настройте тестовый сайт для работы по HTTPS.
 `vagrant@vagrant:~$ sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 \-keyout /etc/ssl/private/apache-selfsigned.key \-out /etc/ssl/certs/apache-selfsigned.crt \-subj "/C=RU/ST=Moscow/L=Moscow/O=Company Name/OU=Org/CN=test.com"
 Generating a RSA private key
 ..........................................................................................+++++
 ...+++++
 writing new private key to '/etc/ssl/private/apache-selfsigned.key'
 -----
 vagrant@vagrant:~$ sudo vim /etc/apache2/sites-available/test.com.conf
 vagrant@vagrant:~$ sudo mkdir /var/www/test
 mkdir: cannot create directory ‘/var/www/test’: File exists
 vagrant@vagrant:~$ sudo vim /var/www/test/index.html
 vagrant@vagrant:~$ sudo a2ensite test.com.conf
 Enabling site test.com.
 To activate the new configuration, you need to run:
   systemctl reload apache2
 vagrant@vagrant:~$ sudo apache2ctl configtest
 Syntax OK
 vagrant@vagrant:~$ sudo systemctl reload apache2
 vagrant@vagrant:~$ curl https://test.com`
## 4. Проверьте на TLS уязвимости произвольный сайт в интернете (кроме сайтов МВД, ФСБ, МинОбр, НацБанк, РосКосмос, РосАтом, РосНАНО и любых госкомпаний, объектов КИИ, ВПК ... и тому подобное).

## 5. Установите на Ubuntu ssh сервер, сгенерируйте новый приватный ключ. Скопируйте свой публичный ключ на другой сервер. Подключитесь к серверу по SSH-ключу.
 
## 6. Переименуйте файлы ключей из задания 5. Настройте файл конфигурации SSH клиента, так чтобы вход на удаленный сервер осуществлялся по имени сервера.

## 7. Соберите дамп трафика утилитой tcpdump в формате pcap, 100 пакетов. Откройте файл pcap в Wireshark.

 ---
## Задание для самостоятельной отработки (необязательно к выполнению)

8*. Просканируйте хост scanme.nmap.org. Какие сервисы запущены?

9*. Установите и настройте фаервол ufw на web-сервер из задания 3. Откройте доступ снаружи только к портам 22,80,443
