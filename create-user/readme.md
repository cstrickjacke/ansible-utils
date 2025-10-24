# Ansible user creation script

- Add server to hosts.yml 
- Create or obtain public key 
- Pass user info and public key to playbook using `-e` extra vars flag
---

**Example:**
```
# create keypair
ssh-keygen -t ed25519 -C <user> -f <user>.key

# run script
ansible-playbook -e "user=<user>" -e "key_var='$(cat /path/to/public/key/file)'" create-user.yml -i hosts.yml --ask-become-pass -v
```
