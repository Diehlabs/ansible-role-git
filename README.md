ansible-role-git
[![Ansible Lint](https://github.com/Diehlabs/ansible-role-git/actions/workflows/test.yml/badge.svg)](https://github.com/Diehlabs/ansible-role-git/actions/workflows/test.yml)
=========

Installs and configures Git and related items. Windows, Linux, OSX supported.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

Defaults:
| Variable name | Description | Example value | Default value | Required? |
|---|---|---|---|---|
| git_user_email | Your email address for gitconfig | me@spam.org | {{ user_email }} | YES |
| git_user_id | Your user ID for file ownership | myusername | {{ user_id }} | YES |
| git_user_full_name | Your full name for gitconfig | Chris Diehl | {{ user_name }} | YES |
| git_user_home_path | # optional to specify explicit path, otherwise path is derived based on OS from var "git_user_home_path_by_os". | /Users/myuserid |{{ git_user_gid_by_os[ansible_system] }} | NO |
| git_config_items | Dict of items to add to gitconfig. | See git_config_items_default in vars/main.yml for formatting. | [] | NO |
| git_excludes_items | List of items to add to gitexcludes file | ... | [] | NO |


Dependencies
------------

Collection: community.general

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: ansible-role-git
      roles:
         - { role: git, git_user_email: mine@email.org }

License
-------

MIT

Author Information
------------------

[Chris Diehl](https://www.linkedin.com/in/chrisdiehl817/)
