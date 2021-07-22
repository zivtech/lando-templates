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
  drupalcs:
    service: appserver
    cmd: "/app/vendor/bin/phpcs --standard=Drupal,DrupalPractice"
    description: Run phpcs Drupal Coding Standards against a given file or directory.
  drupalcbf:
    service: appserver
    cmd: "/app/vendor/bin/phpcbf --standard=Drupal"
    description: Automatically fix Drupal coding standards suggestions.
  drupal-check:
    service: appserver
    cmd: "vendor/bin/drupal-check -ad"
    description: Check Drupal code for deprecations and discover bugs via static analysis.
  phpcs-set-coder:
    service: appserver
    cmd: "/app/vendor/bin/phpcs --config-set installed_paths /app/vendor/drupal/coder/coder_sniffer"
    description: Set config-set for Drupal coder_sniffer standard.
  phpcs-set-php:
    service: appserver
    cmd: "/app/vendor/bin/phpcs --config-set installed_paths /app/vendor/phpcompatibility/php-compatibility"
    description: Set config-set for phpcompatibility standard.
  phpcbf:
    service: appserver
    cmd: "/app/vendor/bin/phpcbf --standard=PHPCompatibility --runtime-set testVersion 7.3 --extensions=php,module,inc,install,test,profile,theme,info"
    description: Automatically fix PHPCompatibility coding standards suggestions for PHP 7.3.
  phpcs:
    service: appserver
    cmd: "/app/vendor/bin/phpcs --standard=PHPCompatibility --runtime-set testVersion 7.3 --extensions=php,module,inc,install,test,profile,theme,info"
    description: Check code against the PHPCompatibility standard for PHP 7.3.
```
