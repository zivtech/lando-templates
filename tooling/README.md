# Tooling Lando Templates

Tooling is a way to configure custom commands within Lando that are run as `lando COMMAND`.

## Tooling Examples

Below are some examples of Lando Tooling commands we have configured for previous projects. See the Lando docs for more information on [Tooling](https://docs.lando.dev/config/tooling.html#usage).

```
tooling:
  gem:
    service: ruby
  ruby:
    service: ruby
  compass:
    service: ruby
  drush:
    service: appserver
    description: Run drush commands.
    cmd: drush --root=/app/docroot
  db-sync:
    service: appserver
    description: Run drush sql-sync from prod to lando.
    cmd: drush --root=/app/docroot sql-sync @SITENAME.prod @SITENAME.lando
  phpcs:
    service: appserver
    cmd: "/app/coder/vendor/bin/phpcs --standard=Drupal --extensions=php,module,inc,install,test,profile,theme,js,css,info,txt"
    options:
    description: Run phpcs for given folder or file.
  phpcbf:
    service: appserver
    cmd: "/app/coder/vendor/bin/phpcbf --standard=Drupal"
    options:
    description: Run phpcs for given folder or file.
```
