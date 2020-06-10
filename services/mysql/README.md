# MySQL Lando Templates

MySQL is the default database service on Drupal recipes, but MariaDB is the default database service on Pantheon recipes.

## Typical MySQL Configuration

```
services:
  database:
    type: mysql:5.7
```
