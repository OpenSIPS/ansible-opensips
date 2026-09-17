OpenSIPS
=========

This role installs [OpenSIPS](http://opensips.org/) SIP Server from the
official OpenSIPS Repositories for [Debian](http://apt.opensips.org/) and
[RedHat](http://yum.opensips.org/).

Galaxy
------

Install your role using [Ansible
Galaxy](https://galaxy.ansible.com/razvancrainea/opensips):

```
ansible-galaxy install razvancrainea.opensips
```


Role Variables
--------------

The following variables can be set to tune the role's install behavior:
* `opensips_version` - specifies the version of OpenSIPS that is going to be
installed. Default is `2.4`.
* `ansible_build` - indicates the OpenSIPS build. Possible values are
`releases` and `nightly`. Default value is `releases`.
* `opensips_yum_release` - indicates a specific RedHat release of OpenSIPS that should be used.
* `opensips_modules` - additional modules that are going to be installed
besides the `opensips` package. This variable should contain packages from the
distribution that `opensips` is installed on. For example, if you want to add
the httpd module, you will have to add to the list `opensips-http-modules`. Default value is empty
(`[]`) - no other modules are installed.
* `opensips_config` - specify a configuration template that is going to be
used instead of the default opensips configuration file.
* `opensips_start` - specify whether OpenSIPS should be started/restarted. Default value is `yes`.

Example Playbook
----------------

Setting up a playbook is very simple: all you need to do is to load the
`opensips` role.

```
    - hosts: servers
      import_role:
         - name: opensips
```

License
-------

GPLv3

Author Information
------------------

This role has been developed by the [OpenSIPS Project](project@opensips.org).
