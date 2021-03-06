# Lando Templates

This repository provides set of YAML file templates and code snippets to reference when configuring Lando for use with Drupal, Wordpress, and other web platforms. It can also be used to configure additional services and tools like PHPMyAdmin, Redis, Solr, Behat, Codesniffer, and Mailhog. Additional info on all topics covered in this repo can be found in the [Lando Config Docs](https://docs.lando.dev/config/lando.html#base-file).

**Note:** To get started setting up the `.lando.yml` config file for new Lando app just run the following command and follow the prompts on your screen.

    lando init

This repository has full templates available and code snippets available for various configurations and configure additional services in the app.

## Current Lando Templates include:
- Drupal (7/8/Pantheon)
- Wordpress
- LAMP (Debian Stretch)
- Services (mailhog, mariadb, mysql, php, phpmyadmin, redis, solr, varnish)
- Events
- Tooling

Once you have the .lando.yml file setup like you want run the following command to restart your Lando app.

    lando restart

After that you may need to import a database.

## Importing Databases

### Pantheon Hosted
Pantheon sites have a special `lando pull` function that can be used to get the latest code, files, and database from a Pantheon site.

First, you need to have a Pantheon Machine Token, so if you haven't created one already you must [Create a Pantheon Machine Token](https://pantheon.io/docs/machine-tokens/) now. Save the token to LastPass, as you will use it often.

Next, authorize your Pantheon Machine Token token using the `lando terminus auth:login` command. _Replace YOUR_TOKEN with a Pantheon Machine Token._

    lando terminus auth:login --machine-token=YOUR_TOKEN

Next, you need to ensure your Pantheon user is added to the Pantheon project's Team page as a Team Member. The Terminus auth process does not handle Pantheon Organizations like Zivtech yet.

Now we are ready to run the `lando start` command to start our app.

After the app starts you can run the `lando pull` command to pull the codebase, files, and database from the Pantheon Dev environment.

    lando pull

Typically we try to use the [stage_file_proxy module](https://www.drupal.org/project/stage_file_proxy) to proxy Drupal's files between environments. Run the `lando pull` command with the `--files=none` option to skip downloading the Drupal site files. The same can be done for the database `--database=none` and the code `--code=none`.

    lando pull --files=none

**Note:** Lando will not find the pantheon site you are trying to pull if you are missing form the project's Team page as a Team Member. Being a member of a Supporting Organization is not currently supported by Terminus.

### Linode/Other Hosts
Linode and other hosting solutions do not have baked in tools to get the DB, so you will need to get a DB dump and import it with the following command inside the lando app directory.

    lando db-import DB-NAME.sql


## Custom URLs and Ports
Lando will configure most services with default ports and use your localhost when no Proxy URLs are defined. Configure a custom URL by defining a proxy for a defined service.

The example below sets a custom URL for the mailhog service at http://mail.my.lndo.site.

```
proxy:
  mailhog:
    - mail.my.lndo.site
```


