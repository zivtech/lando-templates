# Events Lando Templates
Lando provides Event states that can be triggered to run before or after something else happens.

See https://docs.lando.dev/config/events.html for all available events and additional documentation.


## Typical Events Configuration

### Post Pull
The `post-pull` event runs after you run `git pull`.

```
events:
  post-pull:
    - "cd $LANDO_MOUNT && composer install"
```

### Post DB Import
The `post-db-import` event runs after you run `lando db-import`.

```
events:
  post-db-import:
    - 'drush updb'
```


### Run Events on Specific Services
Events can be configured to run on a specific defined service.

The below example will disable the duo module on the appserver service.

```
events:
  post-db-import:
    - appserver: 'drush dis duo -y'
```
