Role Name
=========

Набор задач для проекта `Homebot`

Requirements
------------

Intall dependencies
```sh
ansible-galaxy install nginxinc.nginx
```

Role Variables
--------------

none

Dependencies
------------

	nginxinc.nginx
    geerlingguy.nodejs



Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: nginxinc.nginx }
         - { role: homebot }

License
-------

GNU

Author Information
------------------

"Sergey Vedernikov"<s@vedernik.ru>