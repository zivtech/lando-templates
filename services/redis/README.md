# Redis Lando Templates

## Common Redis Configuration

```
services:
  redis:
    type: redis
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
