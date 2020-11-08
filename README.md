## Installation

```
bash
$ git clone https://github.com/Sergey1501/testovoe-zadanie.git
$ cd testovoe-zadanie

```

## `Edit `provisioning/playbook.yml` and set the values:

```
wp_mysql_db: my_database
wp_mysql_user: my_user
wp_mysql_password: my_password
root_mysql_password: my_password
```

## `Edit `provisioning/templates/.my.cnf` and set the values:

```
user=root
password=my_password
```

```bash
$ vagrant up

После установки, чтобы wordpress смог соединится с mysql нужно выполнить команды:
Вход на сервер с mysql
$ vagrant ssh sql-server

Вход в mysql
$ mysql -u root -p
password: 08_11_2020

Дать право на подключение по сети
GRANT ALL PRIVILEGES ON `wordpress`.* TO serviceuser@192.168.53.3 IDENTIFIED BY '06_11_2020';

Выход из mysql
\q

Перезагрузка mysql
$ sudo service mysql restart

После выполнения этих команд Wordpress будет доступен на  http://192.168.53.3:8080

```




