Zsh
===

[![Build Status](https://travis-ci.org/dirn/ansible-zsh.svg?branch=master)](https://travis-ci.org/dirn/ansible-zsh)

An Ansible role to install and use [Zsh](http://www.zsh.org/).

Requirements
------------

This role works on OS X and Debian-based OSes. If using OS X, make sure you have
[Homebrew](http://brew.sh/) installed before running the role. If you're looking
for a role to handle it for you, check out
[dirn.homebrew](https://github.com/dirn/ansible-homebrew).

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

Several variables are available configure the role.

To control if [Oh My Zsh](https://github.com/robbyrussell/oh-my-zsh) is
installed:

    zsh_install_oh_my_zsh: false

By default Oh My Zsh's run commands file will be symlinked into the home folder.
This file, however, can be customized. It can be skipped:

    zsh_oh_my_zsh_ignore_run_commands: false

To control if [prezto](https://github.com/sorin-ionescu/prezto) is installed:

    zsh_install_prezto: false

By default all of Prezto's run commands files will be symlinked into the home
folder. Several of the files, however, can be customized. A list of files to be
skipped can be provided:

    zsh_prezto_ignore_run_commands: []

Dependencies
------------

None.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
        - role: dirn.zsh
          zsh_install_prezto: true
          zsh_prezto_ignore_run_commands:
            - zpreztorc
            - zshrc

License
-------

MIT

Author Information
------------------

This role was created by [Andy Dirnberger](https://github.com/dirn).
