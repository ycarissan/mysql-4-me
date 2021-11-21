* Pour accéder à l'utilisateur principal
```
sudo mysql -u root
```
* Pour créer un autre utilisateur
```
mysql> CREATE USER 'toto'@'localhost' IDENTIFIED BY 'motdepasse';
mysql> GRANT ALL PRIVILEGES ON * . * TO 'toto'@'localhost';
mysql> exit
Bye
```
* Pour créer une base de donnée UTF8 (ci pour case insensitive) en tant que nouvel utilisateur
```
mysql -p
mysql> CREATE DATABASE 'superbase' COLLATE utf8_general_ci;
```
