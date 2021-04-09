# ericsysmin.chrony

This role enables users to install and configure chrony on their hosts.

## Build Status

[![Build Status](https://travis-ci.org/ericsysmin/ansible-role-chrony.svg?branch=master)](https://travis-ci.org/ericsysmin/ansible-role-chrony)

## Requirements

None

## Role Variables

| Variable | Required | Default | Comments |
| -------- | -------- | ------- | -------- |
| `chrony_pkg_state` | No | `present` | Set pkg `enabled`, `disabled`, `latest` |
| `chrony_service_state` | No | `started` | Set service state, started, enabled or disabled |
| `chrony_service_enabled` | No | `yes` | A list of NTP servers to use.                   |
| `chrony_config_server` | No | `[{"0.pool.ntp.org", "options": [{"option":"iburst"}]}, {"1.pool.ntp.org", "options": [{"option":"iburst"}]}, {"2.pool.ntp.org", "options": [{"option":"iburst"}]}, {"3.pool.ntp.org", "options": [{"option":"iburst"}]}]` | A list of NTP servers, or list of maps of NTP servers and options to use (see example in defaults/main.yml). |
| `chrony_config_logdir` | No | `/var/log/chrony` | A list of NTP servers to use. |
| `chrony_config_extra_options` | No | `{}` | A dict of extra config options. |

## Examples

1) Install chrony and use the default settings.
```yaml
- hosts: all
  roles:
    - role: ericsysmin.chrony
```

2) Install chrony and use custom servers.
```yaml
- hosts: all
  roles:
    - role: ericsysmin.chrony
      chrony_config_server:
        - 0.pool.ntp.org
        - 2.pool.ntp.org
```

## License

MIT

## Author Information

[ericsysmin](https://ericsysmin.com)
