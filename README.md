Solr
=========

Installs Apache Solr from upstream release.

[![Build Status](https://travis-ci.org/ucsdlib/ansible-role-solr.svg?branch=master)](https://travis-ci.org/ucsdlib/ansible-role-solr)

Requirements
------------

Requires Java, which is installed via dependency.

Role Variables
--------------

* `solr_version`: Version to install (default: 6.3.0)
* `solr_mirror`: Mirror to download from (default: http://archive.apache.org/dist/)
* `solr_start`: Flag to start the Solr service immediately (defaut: true)
* `solr_enable`: Flag to start Solr at boot (default: true)

Solr Installation Options:
* `solr_install_dir`: (`-i`) default: /opt
* `solr_live_dir`: (`-d`) default: /var/solr
* `solr_port`: (`-p`) default: 8983
* `solr_service_name`: (`-s`) default: solr
* `solr_user`: (`-u`) solr

* `solr_download_dir`: Temporary directory to download and extract (default: /tmp/solr)
* `solr_set_default`: Set "/opt/solr" symlink (default: true)
* `solr_set_usr_bin`: Set "/usr/local/bin/solr" symlink (default: false)
* `solr_webproxy`: Webproxy to use (default: _none_)

Dependencies
------------

Uses ucsdlib.java to install java, and sets `/usr/local/bin` symlink.

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: ucsdlib.solr, solr_version: 6.2.0 }

Notes
-----

Included is the `helpers/download.yml` playbook which will download the Solr
tarball and cache it, making future deploys faster. The role itself will have
to be writable by the calling user (or at least the files directory within the
role).

`ansible-playbook roles/ucsdlib.solr/helpers/download.yml`

License
-------

BSD 2 Clause

Author Information
------------------

John H. Robinson, IV  
The Library  
UC San Diego  
