# Redis Lando Templates

## Typical Redis Configuration
Redis is configured in the services section and specific versions can be defined.

Redis 5 is the currently defined default version in Lando.

The below example will install Redis 4.

```
services:
  redis:
    type: redis:4
    portforward: true
```

## Custom Redis Configuration File
Define a custom redis configuration file.

```
services:
  redis:
    type: redis
    config:
      server: config/redis.conf
```
