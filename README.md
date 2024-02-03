[![build-test](https://github.com/darkwizard242/ansible-role-dive/workflows/build-and-test/badge.svg?branch=master)](https://github.com/darkwizard242/ansible-role-dive/actions?query=workflow%3Abuild-and-test) [![release](https://github.com/darkwizard242/ansible-role-dive/workflows/release/badge.svg)](https://github.com/darkwizard242/ansible-role-dive/actions?query=workflow%3Arelease) ![Ansible Role](https://img.shields.io/ansible/role/60212?color=dark%20green%20) ![Ansible Role](https://img.shields.io/ansible/role/d/60212?label=role%20downloads) ![Ansible Quality Score](https://img.shields.io/ansible/quality/60212?label=ansible%20quality%20score) [![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-dive&metric=alert_status)](https://sonarcloud.io/dashboard?id=ansible-role-dive) [![Maintainability Rating](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-dive&metric=sqale_rating)](https://sonarcloud.io/dashboard?id=ansible-role-dive) [![Reliability Rating](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-dive&metric=reliability_rating)](https://sonarcloud.io/dashboard?id=ansible-role-dive) [![Security Rating](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-dive&metric=security_rating)](https://sonarcloud.io/dashboard?id=ansible-role-dive) ![GitHub tag (latest SemVer)](https://img.shields.io/github/tag/darkwizard242/ansible-role-dive?label=release) ![GitHub repo size](https://img.shields.io/github/repo-size/darkwizard242/ansible-role-dive?color=orange&style=flat-square)

# Ansible Role: dive

Role to install (_by default_) [dive](https://github.com/wagoodman/dive) on **Debian/Ubuntu** and **EL** systems. **dive** is a tool for exploring a docker image, layer contents, and discovering ways to shrink the size of your Docker/OCI image.

## Requirements

None.

## Role Variables

Available variables are listed below (located in `defaults/main.yml`):

### Variables list:

```yaml
dive_app: dive
dive_version: 0.12.0
dive_os: linux
dive_arch: amd64
dive_dl_url: https://github.com/wagoodman/{{ dive_app }}/releases/download/v{{ dive_version }}/{{ dive_app }}_{{ dive_version }}_{{ dive_os }}_{{ dive_arch }}.tar.gz
dive_bin_path: /usr/local/bin
dive_file_owner: root
dive_file_group: root
dive_file_permission_mode: '0755'
```

### Variables table:

Variable                  | Description
------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------
dive_app                  | Defines the app to install i.e. **dive**
dive_version              | Defined to dynamically fetch the desired version to install. Defaults to: **0.12.0**
dive_os                   | Defines os type. Defaults to: **linux**
dive_arch                 | Defines os architecture. Defaults to: **amd64**
dive_dl_url               | Defines URL to download the dive binary from.
dive_bin_path             | Defined to dynamically set the appropriate path to store dive binary into. Defaults to (as generally available on any user's PATH): **/usr/local/bin**
dive_file_owner           | Owner for the binary file of dive.
dive_file_group           | Group for the binary file of dive.
dive_file_permission_mode | Defines the permission mode level for the file. Defaults to: `0755`

## Dependencies

None

## Example Playbook

For default behaviour of role (i.e. installation of **dive**) in ansible playbooks.

```yaml
- hosts: servers
  roles:
    - darkwizard242.dive
```

For customizing behavior of role (i.e. specifying the desired **dive** version) in ansible playbooks.

```yaml
- hosts: servers
  roles:
    - darkwizard242.dive
  vars:
    dive_version: 0.9.2
```

For customizing behavior of role (i.e. placing binary of **dive** package in different location) in ansible playbooks.

```yaml
- hosts: servers
  roles:
    - darkwizard242.dive
  vars:
    dive_bin_path: /bin/
```

## License

[MIT](https://github.com/darkwizard242/ansible-role-dive/blob/master/LICENSE)

## Author Information

This role was created by [Ali Muhammad](https://www.alimuhammad.dev/).
