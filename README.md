# Ansible Role: hostname

An Ansible Role to update the hostname.

[![Actions Status](https://github.com/tristan-weil/ansible-role-hostname/workflows/molecule/badge.svg?branch=master)](https://github.com/tristan-weil/ansible-role-hostname/actions)

## Role Variables

Available variables are listed below, (see also `defaults/main.yml`).

Mandatory variables:

| Variable      | Description |
| :------------ | :---------- |
| hostname_fqdn |  the `hostname` to set |

Optional variables:

| Variable      | Default | Description |
| :------------ | :------ | :---------- |
| hostname_etc_hosts | <...> | a list of <etc_hosts entry> to add to/remove from /etc/hosts |

### *<etc_hosts entry>*

An *etc_hosts entry* allow to add or remove entries from the /etc/hosts file.

**NOTE**: you should use [ansible-role-etc_hosts](https://github.com/tristan-weil/ansible-role-etc_hosts/) for an
easier way to handle entries in the /etc/hosts file.
This option is only meant for simple use-case and cleaning and you probably should not use it.

Mandatory variables:

| Variable      | Description |
| :------------ | :---------- |

Optional variables:

| Variable      | Default | Description |
| :------------ | :------ | :---------- |
| line | | the exact line to add / remove / replace |
| regexp | | the regexp allowing to find an entry to remove / replace |
| state | present | *present / absent*: the state of the entry |

## Example Playbook

    - hosts: 'webservers'
      roles:
        - role: 'ansible-role-hostname'
          hostname_fqdn: xxxx

## Todo

None.

## Dependencies

None.

## Supported platforms

See [meta/main.yml](https://github.com/tristan-weil/ansible-role-hostname/blob/master/meta/main.yml)

## License

See [LICENSE.md](LICENSE.md)
