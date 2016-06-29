# Role Name: MariaDB-Galera

An Ansible Role that installs MariaDB-Galera on RedHat/CentOS.

## Requirements

None.

## Role Variables

### `defaults/main.yml`

* `mariadb_repo_baseurl: "http://yum.mariadb.org/5.5/centos7-amd64/"`
* `mariadb_root_username: root`
* `mariadb_root_password: root`
* `galera_clustercheck_enable: false`
* `galera_clustercheck_username: clustercheck`
* `galera_clustercheck_password: clustercheck`
* `galera_bootstrap_node: ""`
* `galera_wsrep_provider: /usr/lib64/galera/libgalera_smm.so`
* `galera_wsrep_cluster_name: galera_cluster`
* `galera_wsrep_cluster_address: []`
* `galera_wsrep_slave_threads: 1`
* `galera_wsrep_certify_nonPK: 1`
* `galera_wsrep_max_ws_rows: 131072`
* `galera_wsrep_max_ws_size: 1073741824`
* `galera_wsrep_debug: 0`
* `galera_wsrep_convert_LOCK_to_trx: 0`
* `galera_wsrep_retry_autocommit: 1`
* `galera_wsrep_auto_increment_control: 1`
* `galera_wsrep_drupal_282555_workaround: 0`
* `galera_wsrep_causal_reads: 0`
* `galera_wsrep_notify_cmd: ""`
* `galera_wsrep_sst_method: rsync`

## Dependencies

None.

## Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
        - role: ansible-role-mariadb-galera
          mariadb_root_username: root
          mariadb_root_password: root
          mariadb_users:
            - { name: "root", host: "%", password: "root", priv: "*.*:GRANT,ALL" }
          galera_clustercheck_enable: true
          galera_clustercheck_username: clustercheck
          galera_clustercheck_password: clustercheck
          galera_wsrep_cluster_address: ['192.168.100.11', '192.168.100.12', '192.168.100.13']
          galera_bootstrap_node: "192.168.100.11"

## Author Information

z
