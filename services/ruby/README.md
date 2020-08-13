# Ruby Lando Templates

## Typical Ruby Configuration
Ruby is configured in the services section and specific versions can be defined.

Ruby 2.5 is the currently defined default version in Lando.

The below example will install Ruby 2.6.

```
ruby:
  type: ruby:2.6
```

## Install Ruby Dependencies

Lando can install Ruby dependencies when the Lando project is started.

```
services:
  ruby:
    type: ruby:2.5
    build:
      - gem install compass
      - gem install rails
      - gem install mini_racer
      - gem install autoprefixer-rails
      - gem install sassy-buttons
      - gem install breakpoint
      - gem install compass-rgbapng
```
