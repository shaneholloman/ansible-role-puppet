# Ansible Role: Puppet

[![CI](https://github.com/shaneholloman-org/ansible-role-puppet/actions/workflows/ci.yml/badge.svg)](https://github.com/shaneholloman-org/ansible-role-puppet/actions/workflows/ci.yml)

An Ansible Role that installs [Puppet](https://www.puppet.com) on Linux.

## Requirements

Requires Java 7 or later to be installed on the server (you can use the `shaneholloman.java` role to install Java if needed; see the test playbook in `tests/` for an example).

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    puppet_package: puppetserver

The package to be installed.

    puppet_service: puppetserver
    puppet_service_state: started
    puppet_service_enabled: false
    puppet_service_manage: false

The service that should be run on this server. By default, this role will not manage a Puppet service, and will not enable it at boot time.

    puppet_bin_path: /opt/puppetlabs/bin

The path to all the Puppet Labs binaries (after the package is installed).

    puppet_version: 7

The major version of Puppet to be installed.

    # Used only for Debian/Ubuntu.
    puppet_apt_deb: "https://apt.puppetlabs.com/puppet{{ puppet_version }}-release-{{ ansible_distribution_release }}.deb"

The .deb file for installation on Debian-based OSes.

    # Used only for RedHat/CentOS.
    puppet_yum_rpm: "https://yum.puppet.com/puppet{{ puppet_version }}-release-el-{{ ansible_distribution_major_version }}.noarch.rpm"

The .rpm file for installation on RedHat-based OSes.

## Dependencies

None.

## Example Playbook

    - hosts: all
      roles:
        - shaneholloman.puppet

## License

MIT / BSD

## Author Information

This role was created in 2023

