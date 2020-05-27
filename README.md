# Ansible VXLAN-EVPN Example

[![N|Solid](https://upload.wikimedia.org/wikipedia/commons/3/31/Juniper_Networks_logo.svg)](https://www.juniper.net/us/en/products-services/switching/qfx-series/)

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

`Ansible VXLAN-EVPN Example` is an easier way to build Juniper data centers with Ansible.

- Makefile to build and run all automation inside a Docker container
- Build out configurations each configuration stanza for both spine and leaf switches
- assembles all configuration stanzas into a single, consumable configuration
- checks for a difference between the current running configuration
- validates that the configuration, if there was a diff, is a valid config
- pushes configuration to devices in a `load override` capacity, removing all non-Ansible elemetns

# New Features!

- Dockerfile provided to help with package dependencies

> this playbook can be ran locally or within your Ansible Tower instance

### Dependencies

`cso_ansible_sdk` uses a single open source project to work properly:

```sh
ansible==2.8.9
ansible-tower-cli
jsnapy
junos-eznc==2.4.0
jxmlease
lxml
ncclient
PyYAML
regex
requests
urllib3
xmltodict
```

### Installation

Docker containers are built with the simple command:

```sh
$ make build
```

### Using this project

```sh
$ make run
```

Update your inventory.yml file and the files listed under `host_vars` and `group_vars` with your expected configuration elements.

```sh
$ ansible-playbook pb.configuration.network.yml
```


### Development

Want to contribute? Great!

Submit a PR and let's work on this together :D 