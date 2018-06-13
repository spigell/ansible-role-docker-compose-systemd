ansible-role-docker-compose-systemd
=========

Install your docker-compose service as systemd unit

Requirements
------------

None

Role Variables
--------------

all variables for the role must be in list named `docker_services`:

    docker_services:
    - name: test
      enabled: no
      root_dir: /srv/docker/test-service
      compose_template: examples/test.yml.j2
      unit_template: examples/test.service.j2
      my_var: var1

  - name (required)

name of your service.

  - enabled (optional)

Indicates autostart of service. Default is `yes`.

  - root_dir (required)

directory where docker-compose file will be lying.

  - compose_template (required)

path to docker-compose.yml file.

  - unit_template (required)

path to systemd unit for service.



Of course you can define new vars for templates and get access it while looping over the list.

Dependencies
------------

None

Example Playbook
----------------

    - hosts: localhost
      roles:
         - { role: spigell.ansible-role-docker-compose-systemd }

Testing
-------

### via Sparrowdo

There is a sparrowfile for [sparrowdo](https://github.com/melezhik/sparrowdo) in /tests directory. The one can use it to execute the role on vagrant, docker, etc...

License
-------

BSD
