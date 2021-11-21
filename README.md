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
ATTENTION, les caractères unicodes ne sont pris en compte que dans les types de variable
NCHAR ou NVARCHAR. Les types CHAR et VARCHAR sont en ASCII.
* Pour créer une table
```
mysql> CREATE TABLE supertable(
              id       INT,
              nom      VARCHAR(100),
              prenom   VARCHAR(100),
              ...                  ,
);
```
* Rendre une valeur obligatoire (avec un défaut ou non):
```
mysql> CREATE TABLE supertable(
              id       INT,
              nom      VARCHAR(100) NOT NULL,
              prenom   VARCHAR(100),
              elo      CHAR(5) NOT NULL DEFAULT '1099E',
              ...                  ,
);
```
* Pour modifier une table
```
mysql> ALTER TABLE supertable ADD elo INT;
mysql> ALTER TABLE supertable MODIFY elo BIGINT;
mysql> ALTER TABLE supertable DROP elo;
```
