# [java](#java)

Install and configure java on your system.

> The code for this role is based upon [robertdebock/ansible-role-java](https://github.com/robertdebock/ansible-role-java) with changes throughout.

## [Requirements](#requirements)

None

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](defaults/main.yml):

```yaml
---
# Set this version of java as the default
java_default_installation: true

# Set the variable to install the type, valid values are "jre" and "jdk".
java_type: jre

# Set the version of java, valid values are 8, 11 or 17.
# By default, the latest available distribution version is used, this is mapped
# in `vars/main.yml`.
# By setting java_version, you overwrite this default to your selected version.
java_version: "{{ java_default_version }}"
```

## [Dependencies](#dependencies)

None

## [Example Playbook](#example-playbook)

Install openjdk 11 and 17, setting 17 as the default installation.

```yaml
---
- name: Configure Java Build Server
  hosts: all
  roles:
    - role: java
      java_default_installation: false
      java_type: jdk
      java_version: 11
    - role: java
      java_default_installation: true
      java_type: jdk
      java_version: 17
```

## [License](#license)

[Apache-2.0](LICENSE)
