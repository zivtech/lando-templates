# PHPMyAdmin Lando Templates
PHPMyAdmin is a tool used for managing MySQL databases through a graphical UI.


## Typical PHPMyAdmin Configuration
PHPMyAdmin is configured in the services section and can be defined to access multiple MySQL installs.

The below example will configure PHPMyAdmin to run on both the MySQL 5.7 and MySQL 8 databases defined.

```
services:
  phpmyadmin:
    type: phpmyadmin
    hosts:
      - mysql57
      - mysql8
  mysql57:
    type: mysql:5.7
  mysql8:
    type: mysql:8
```
