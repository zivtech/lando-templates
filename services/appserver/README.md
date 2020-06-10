# Appserver Lando Templates

The appserver service is the PHP app Lando is running itself. Specific settings can be configured within the appserver to run specific commands at build time or run specific commands as root.

## Appserver Configuration Options

### Build Steps

Adding a build steps to the Lando config will run the commands when the lando project is first started or when running `lando rebuild`.

There are four major Lando build steps. See more in the Lando docs about [Build Steps](https://docs.lando.dev/config/services.html#build-steps).

- `build` runs as "you" and before your service boots up.
- `build_as_root` runs as root and before your service boots up.
- `run` runs as "you" and after your service boots up.
- `run_as_root` runs as root and after your service boots up.

#### Build Step Examples

##### Build

```
appserver:
  build:
    - /bin/sh -c "mkdir -p ~/.drush/site-aliases"
    - /bin/sh -c "ln -sf /app/drush/SITENAME.aliases.drushrc.php ~/.drush/site-aliases/SITENAME.drushrc.php"
    - "mkdir -p /app/coder && cd /app/coder && composer require drupal/coder"
    - "/app/coder/vendor/bin/phpcs --config-set installed_paths /app/coder/vendor/drupal/coder/coder_sniffer"
```

##### Run as Root

Adding a `run_as_root` option to the Lando config will allow running certain commands as root when the lando project is first started or when running `lando rebuild`.

```
appserver:
  run_as_root:
    - drush --root=/app/docroot pm-enable --yes stage_file_proxy
    - drush --root=/app/docroot cc all
    - apt-get update
    - apt-get install dos2unix -y
```
