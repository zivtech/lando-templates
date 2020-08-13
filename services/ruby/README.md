# Ruby Lando Templates

## Typical Ruby Configuration

```
ruby:
  type: ruby:2.5
```

## Install Ruby Dependencies

```
ruby:
  type: ruby:2.5
  install_dependencies_as_me:
    - gem install compass
    - gem install rails
    - gem install mini_racer
    - gem install autoprefixer-rails
    - gem install sassy-buttons
    - gem install breakpoint
    - gem install compass-rgbapng
```
