[![Build Status](https://travis-ci.org/dincho/ansible-elasticsearch.svg?branch=master)](https://travis-ci.org/dincho/ansible-elasticsearch)
[![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-published-blue.svg)](https://galaxy.ansible.com/detail#/role/6363)

Elasticsearch
=========

Ansible role to install and setup [Elasticsearch](https://www.elastic.co/products/elasticsearch) on Debian-like systems

Requirements
------------

* JRE - autoinstalled (default jre)

Role Variables
--------------

* `es_version`: [default: `2.4.*`]: Version to install
* `es_default_config`: [default: {ES_JAVA_OPTS: -Xms128m -Xmx128m}]: /etc/default/elasticsearch configuration
* `es_config`: [default: {}]: List of node [configuration options](https://www.elastic.co/guide/en/elasticsearch/reference/current/index.html)

Dependencies
------------

none

Example Playbook
----------------

    - hosts: servers
      vars:
        es_version: '2.4.1'
        es_default_config:
          MAX_OPEN_FILES=65535
        es_config:
          network.bind_host: localhost
      roles:
         - dincho.elasticsearch

License
-------

MIT

