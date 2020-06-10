# Mailhog Lando Templates

Mailhog captures mail sent by the web server and allows for viewing mail locally.


## Typical Mailhog Configuration
Add the following configuration under the services section of the project's .lando.yaml file.

```
services:
  mailhog:
    type: mailhog
    portforward: true
    hogfrom:
      - appserver
  appserver:
    type: php
```
