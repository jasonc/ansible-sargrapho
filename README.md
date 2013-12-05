SarGraphO Playbook
==================

Overview
--------
The SarGraphO playbook installs SarGraphO.  SarGraphO collects sar data, graphs it, and generates web pages to display the graphs.

Requirements
------------
SarGraphO works with the RedHat family of Linux distributions.

Variables
----------

#### `group_vars/sargrapho`

* `sargrapho_rpm` - The name of the RPM package to install.  Default: sargrapho-1.0.0-1.noarch.rpm
* `sargrapho_rpm_url` - The URL of the RPM package to install.  Default: https://github.com/jasonc/sargrapho/releases/download/v1.0.0/{{ sargrapho_rpm }}"



Usage
-----
To use this playbook, first edit the `hosts` inventory file and populate it with the servers on which you want to install SarGraphO.

    [sargrapho]
    localhost

Install SarGraphO with the following command:

    ansible-playbook -i hosts site.yml


You can change the rpm name and rpm URL for the SarGraphO package by overriding the corresponding variables.

For example, if you maintain a local repository you could do this:

    ansible-playbook -i hosts site.yml -e sargrapho_rpm_url=http://sargrapho.local.com/releases/sargrapho-1.0.0-1.noarch.rpm

