novafloss.ssh-agent
~~~~~~~~~~~~~~~~~~~

Basic role to ensure an SSH agent is ready to use by ansible.

Example usage::

    ---

    - hosts: localhost
      roles:
      - role: novafloss.ssh-agent
        ssh_insecure: ['*.lxc']

This will:

- ensure a default ssh key exists,
- ensure ssh config dir have the right permissions,
- ensure ssh config have the right permissions,
- ensure an ssh key exists,
- ensure ssh keys have the right permissions,
- ensure an ssh agent is started and ``$SSH_AUTH_SOCK`` is defined,
- enable insecure connection to ``*.lxc`` (or any host you add to
  ``ssh_insecure``).

While this may be useless on an actual control machine, because obviously an
ssh agent would already be properly configured, this is useful to execute tests
on empty containers.
