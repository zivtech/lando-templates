# Varnish Lando Templates
Varnish is used for caching websites.


## Typical Varnish Configuration
Varnish is configured in the services section and specific versions can be defined. The backends setting is typically set for `appserver`.

```
services:
  varnish:
    type: varnish:4.1
    backends:
      - appserver
```

Additional configuration options are available to use a custom VCL and custom environment variables. See https://docs.lando.dev/config/varnish.html for more documentation on configuration Varnish in Lando.
