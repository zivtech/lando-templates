# Solr Lando Templates
Apache Solr is used to provide a powerful search appliance on websites.


## Typical Solr Configuration
Solr is configured in the services section and specific versions can be defined.

Apache Solr 7 is the currently defined default version in Lando.

The below example will install Apache Solr 6 and enable port forwarding. 

```
services:
  solr:
    type: solr:6
    portforward: true
```

**Note:** The `portforward: true` setting ensures there are no collisions with other Lando projects as the port will change each time the Lando project is restarted.
