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
| Variable Name       | Info     |
| :------------- | :------------- |
| git_user_email | chris@gmail.com |
| git_user_id | chris |
| git_user_full_name | Chris Diehl |
| git_user_home_path | # optional to specify explicit path, otherwise path is derived based on OS from var "git_user_home_path_by_os". |
| git_ssl_verify | "true" |
| git_config_scope | system |

Vars:
| Variable Name       | Info     |
| :------------- | :------------- |
| git_user_home_path_default: | "{{ git_user_home_path_by_os[ansible_system] }}"
| git_user_home_path_by_os.Darwin: | /Users/{{ git_user_id }} |
| git_user_home_path_by_os.Linux: | /home/{{ git_user_id }} |
| git_user_home_path_by_os.Windows: | \Users\{{ git_user_id }} |

Dependencies
------------

Collection: community.general

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: git, git_user_email: mine@email.org }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
