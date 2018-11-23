Django app in supervisor group
==============================

Manages process group of multi-server Django app in supervisor.

Requirements
------------

Debian, Django app

Role Variables
--------------

- `app` - app label
- `group_name` - group name; if unset, defaults to `{{ app }}`
- `servers` - list of servers; if unset setting up process group is omitted

- `supervisor_config_dir` - directory where all config files are placed
- `supervisor_user` - user predefined to run given service
- `supervisor_manage_user` - user allowed to use supervisorctl & create/edit individual configs
- `supervisor_manage_group` - respective group as above
- `supervisor_manage_chmod` - octal unix perms for supervisor socket and config dir
  (caution: needs be specified as string)

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: django_supervisor, servers: [ app_uwsgi, app_channels_worker ]  }

License
-------

BSD
