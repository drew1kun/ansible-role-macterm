terminal
=========

Cross-platform ansible role for terminal configuration

Requirements
------------

One of the following OS (or deriviatives):
  - Debian | Ubuntu
  - MacOS

Role Variables
--------------

    - terminal_iterm2: yes | no         # install iterm2 (on MacOS)
    # if yes - homebrew and terminus_powerline roles will be fetched as dependencies

    - terminal_homebrew_dep: yes | no   # speed up the role installation
    # if set to no, then homebrew dependency role will not be applied even when 'terminal_iterm2: yes'

Dependencies
------------

 - terminus_powerline

When used against MacOS hosts, then depends on:
 - homebrew

Example Playbook
----------------

    - hosts: dev_clients
      roles:
         - role: drew-kun.terminal
         #- { role: drew-kun.terminal, x: 42 }

License
-------

MIT

Author Information
------------------

Andrew Shagayev
