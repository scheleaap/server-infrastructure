# Configuration for Servers

## Preparation

### Master Machine

Go to the target directory and run:

```bash
# Install pip3 and pipenv (needed only once)
sudo apt purge python-pip && \
sudo apt install python3-pip && \
pip3 install --user pipenv

# Create venv and activate
PATH=~/.local/bin:$PATH && \
pipenv --three && \
pipenv shell

# Install project dependencies
pipenv update
```


### All Target Machines

1. Create SSH directory:
   ```bash
   cd ~
   install -d -m 700 ~/.ssh
   ```

1. **Run from another machine:**<br>
   Copy public key to authorized_keys:
   ```bash
   cat ~/.ssh/id_rsa.pub | ssh <user>@<host> 'cat >> .ssh/authorized_keys'
   ```


## Running It

```bash
pipenv shell
ansible-galaxy install -r requirements.yml -p roles/
ansible-playbook site.yml -i hosts --ask-become-pass --vault-password-file vault-password-file
```
