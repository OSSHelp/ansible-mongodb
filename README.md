# MongoDB

[![Build Status](https://drone.osshelp.ru/api/badges/ansible/mongodb/status.svg)](https://drone.osshelp.ru/ansible/mongodb)

## Description

The role installs and setups MongoDB.

## Deploy examples

### Install latest stable version

``` yaml
    - role: mongodb
```

### Install specific version

``` yaml
    - role: mongodb
      version: 3.2
```

LTS versions supported only:

- 4.4 (default)
- 4.2
- 4.0
- 3.6
- 3.4
- 3.2
- 3.0

Available MongoDB versions for Ubuntu releases:

- Xenial 3.0-4.4
- Bionic 4.0-4.4
- Focal 4.4

The role installs MongoDB from [official repos](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/) only.

### MongoDB settings

MongoDB configuration files use the YAML format - see [docs](https://docs.mongodb.com/manual/reference/configuration-options/).

``` yaml
- role: mongodb
  config:
    net:
      bindIp: 0.0.0.0
    systemLog:
      component:
        command:
          verbosity: 1
```

or for [old versions](https://docs.mongodb.com/v3.2/reference/configuration-options/):

``` yaml
- role: mongodb
  version: "3.2"
  config:
    net:
      http:
        enabled: "true"
        RESTInterfaceEnabled: "true"
```

for 3.0:

``` yaml
- role: mongodb
  version: "3.0"
  config:
    processManagement:
    fork: true
```

## Links

[Official Documentation](https://docs.mongodb.com/manual/)
