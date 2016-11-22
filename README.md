Deploy Django
=============

Using `supervsior`: configure and run Django app in uWsgi and optionally with
Daphne for async I/O.

Requirements
------------

Debian, Django app

Role Variables
--------------

- `app` - determines directory structure and process names;
- `uwsgi_ini_tpl` - path to `uwsgi.ini` template file to use, if unset, we're using
    reasonable default one defined within role: `templates/_default_uwsgi.ini.j2`
- `supervisor_conf_tpl` - path to supervisor configuration file, if unset we're using
    default defined within role: templates/_default_supervisor.conf.j2
- `use_channels` - if start Daphne for websockets & other async io's, default: no
- `uwsgi_host` - default: `127.0.0.1`
- `uwsgi_port` - default: `8000`
- `uwsgi_processes` - default: 2

Dependencies
------------

- `xkoralsky.django_app` shares directory structure with this role

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: django_uwsgi_daphne,  }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
