terminal
=========

[![MIT licensed][mit-badge]][mit-link]
[![Galaxy Role][role-badge]][galaxy-link]

Ansible role for terminal configuration on MacOS (Linux coming soon)

This role does the following:
 - Installs Nerdfonts
 - Installs Terminus Powerline font if configured (see Role Variables section)
 - Imports Terminal.app Profile with Custom Solarized Dark Colorscheme (On MacOS)
 - Installs homebrew if needed - see Role Variables section (On MacOS)
 - Installs iTerm2 from homebrew (On MacOS)
 - Imports iTerm2 profile with Custom Solarized Dark Colorscheme (On MacOS)
 - Sets up nerdfonts for Non-ASCII Fonts and Terminus-Powerline font as ASCII Font.

Requirements
------------

One of the following OS (or deriviatives):
  - MacOS (with [Homebrew][homebrew])

If Homebrew is not installed on the managed host, install the following role via galaxy:

    ansible-galaxy install drew-kun.homebrew

And include it in the playbook:

    roles:
      - drew-kun.homebrew

Role Variables
--------------

    mac_terminal_iterm2: yes | no         # install iterm2 (on MacOS)
    # if yes - homebrew and terminus_powerline roles will be fetched as dependencies

Dependencies
------------

 - [drew-kun.terminus_powerline][terminus_powerline-galaxy-link] (conditionally, when: terminal_iterm2 and terminal_homebrew_dep both set to 'yes')
 - [drew-kun.nerdfonts][nerdfonts-galaxy-link]

Install via ansible-galaxy:

    ansible-galaxy install drew-kun.nerdfonts drew-kun.terminus_powerline

Example Playbook
----------------

    - hosts: dev_clients
      roles:
         - role: drew-kun.terminal

License
-------

[MIT][mit-link]

Author Information
------------------

![Andrew Shagayev](drewshg@gmail.com)

[role-badge]: https://img.shields.io/badge/role-drew--kun.mac__terminal-green.svg
[galaxy-link]: https://galaxy.ansible.com/drew-kun/mac_terminal/
[homebrew-galaxy-link]: https://galaxy.ansible.com/drew-kun/homebrew/
[nerdfonts-galaxy-link]: https://galaxy.ansible.com/drew-kun/nerdfonts/
[terminus_powerline-galaxy-link]: https://galaxy.ansible.com/drew-kun/terminus_powerline/

[mit-badge]: https://img.shields.io/badge/license-MIT-blue.svg
[mit-link]: https://raw.githubusercontent.com/drew-kun/ansible-terminal/master/LICENSE
[homebrew]: http://brew.sh/
