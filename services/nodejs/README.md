# Node.js Lando Templates
Node.js® is a JavaScript runtime built on Chrome's V8 JavaScript engine. It uses a non-blocking, event-driven I/O model that makes it compact, but also scalable. 


## Typical Node.js Configuration
Add the following configuration under the services section of the project's .lando.yaml file to install Node.js with Gulp and run `npm install` when this Lando project starts.

Currently the default version of Node.js installed in Lando is Node 10.

```
services:
  nodejs:
    type: node
    build:
      - "cd $LANDO_MOUNT/web/themes/custom/starterkit && npm install"
    globals:
      gulp-cli: latest
```

## Specify the Node.js Version
A specific version of Node.js can be installed by defining the version in the .lando.yaml config file.

The example below will install Node.js 8.

```
services:
  nodejs:
    type: node:8
    build:
      - "cd $LANDO_MOUNT/web/themes/custom/starterkit && npm install"
    globals:
      gulp-cli: latest
```


## Node.js Configuration with Tooling
The following configuration will add tooling commands that are available to the node service.

```
services:
  node:
    type: node
    build:
      - npm install
      - gulp
    globals:
      gulp-cli: latest
tooling:
npm:
  service: node
node:
  service: node
gulp:
  service: node
yarn:
  service: node
```

The above tooling configuration will allow lando to run command such as:

```
lando node
lando npm
lando gulp
lando yarn
```

Example: `lando gulp watch`
