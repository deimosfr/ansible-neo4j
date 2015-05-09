Ansible Neo4j playbook
=====

This role installs and configures Neo4j. It also handles Neo4j spatial.

Requirements
------------

This role requires Ansible 1.6 or higher and platform requirements are listed
in the metadata file.

Role Variables
--------------

The variables that can be passed to this role. You can find all options in

```
# Select neo4j version
neo4j_package: neo4j # community version
#neo4j_package: neo4j-advanced
#neo4j_package: neo4j-enterprise

# Package version
neo4j_package_version: stable
#neo4j_package_version: oldstable
#neo4j_package_version: testing

# Force user id
neo4j_uid:

# Manage service
neo4j_manage_service: True

# Neo4j spatial plugin
neo4j_install_spatial: false
neo4j_spatial_version: '0.13-neo4j-2.1.2'
neo4j_plugins_directory: '/usr/share/neo4j/plugins'

# java prerequisite
neo4j_install_java: false
neo4j_java_package_name: openjdk-7-jdk

# limits.conf
neo4j_update_limits: true
neo4j_nofile_value: 40000

# neo4j neostore mapped memory
neo4j_mm_nodestore: 25M
neo4j_mm_relationshipstore: 50M
neo4j_mm_propertystore: 90M
neo4j_mm_propertystore_strings: 130M
neo4j_mm_propertystore_arrays: 130M
neo4j_mm_index: 5M
neo4j_nm_index_keys: 5M
neo4j_cache_type: none

# server
neo4j_server_database_location: data/graph.db
neo4j_server_webserver_address: 127.0.0.1
neo4j_server_webserver_port: 7474
neo4j_server_webserver_https_enabled: false
neo4j_server_webserver_https_port: 7473
neo4j_server_webserver_https_cert_location: conf/ssl/snakeoil.cert
neo4j_server_webserver_https_key_location: conf/ssl/snakeoil.key
neo4j_server_webserver_https_keystore_location: data/keystore

# webadmin
neo4j_server_webadmin_rrdb_location: data/rrd
neo4j_server_webadmin_data_uri: /db/data/
neo4j_server_webadmin_management_uri: /db/manage/
neo4j_server_db_tuning_properties: conf/neo4j.properties
neo4j_server_manage_console_engines: shell
neo4j_server_database_mode: SINGLE

# logging
neo4j_server_http_log_enabled: false
neo4j_server_http_log_config: conf/neo4j-http-logging.xml
neo4j_keep_logical_logs: true
```

Examples
========

```
# Roles
- name: neo4j
  hosts: neo4j
  user: root
  roles:
    - deimosfr.neo4j
  vars_files:
    - "host_vars/neo4j.yml"
```

Dependencies
------------

- Java

License
-------

GPL2

Author Information
------------------

Pierre Mavro / deimosfr


