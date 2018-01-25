terminal
=========

Ansible role for terminal configuration on MacOS (Linux coming soon)

This role does the following:
 - Installs Nerdfonts
 - Installs Terminux Powerline font if configured (see Role Variables section)
 - Imports Terminal Profile with Custom Solarized Colorscheme (On MacOS)
 - Installs homebrew if needed - see Role Variables section (On MacOS)
 - Installs iTerm2 from homebrew (On MacOS)
 - Imports iTerm2 profile with Custom Solarized Colorscheme (On MacOS)

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

 - drew-kun.nerdfonts
 - drew-kun.terminus_powerline (conditionally, when: terminal_iterm2 and terminal_homebrew_dep both set to 'yes')

When used against MacOS hosts, then depends on:
 - drew-kun.homebrew (conditionally, when: terminal_iterm2 and terminal_homebrew_dep both set to 'yes')

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
