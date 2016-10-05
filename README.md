Solr
=========

Installs Apache Solr from upstream release.

Requirements
------------

Requires Java, which is installed via dependency.

Role Variables
--------------

* `solr_version`: Version to install (default: 6.2.1)
* `solr_mirror`: Mirror to download from (default: http://archive.apache.org/dist/)

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

License
-------

BSD 2 Clause

Author Information
------------------

John H. Robinson, IV  
The Library  
UC San Diego  
