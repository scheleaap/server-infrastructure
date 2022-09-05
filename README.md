# Server Infrastructure

This is an Ansible Playbook for my server infrastructure.


## Running it

1. Copy all files whose name ends with `.default` and fill in the values as appropriate.
1. ```sh
   pipenv run ansible-galaxy install -r requirements.yml -p roles/
   pipenv run ansible-playbook site.yml -i hosts --ask-become-pass --vault-password-file vault-password-file
   ```


## Setup

See the [home infrastructure's README](https://github.com/scheleaap/home-infrastructure/blob/master/README.md#setup) for instructions.


## Development

To encrypt and decrypt files, use these commands:
```sh
ansible-vault decrypt <path>/vault.yml --vault-password-file vault-password-file
ansible-vault encrypt <path>/vault.yml --vault-password-file vault-password-file
```
