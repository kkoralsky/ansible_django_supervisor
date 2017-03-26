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

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: django_supervisor, servers: [ app_uwsgi, app_channels_worker ]  }

License
-------

BSD
