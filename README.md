# expect-scripts

### deploy_ssh_key.exp
**Script do the following tasks:**
- connect to remote system (remote_host) with ssh client as user (remote_user) with user password (remote_user_password)
- as user root create new account (deployed_user_name) and set new password for new account (deployed_user_password)
- change (su) to new account (deployed_user_name) and create SSH key pair (ssh-keygen)
- odhlasi sa zo vzdialeneho stroja
- disconnect from remote system (remote_host)

**Usage**

