# expect-scripts

### deploy_ssh_key.exp
**Script do the following tasks:**
- connect to remote system (remote_host) with ssh client as user (remote_user) with user password (remote_user_password)
- as user root create new account (deployed_user_name) and set new password for new account (deployed_user_password)
- change (su) to new account (deployed_user_name) and create SSH key pair (ssh-keygen)
- odhlasi sa zo vzdialeneho stroja
- disconnect from remote system (remote_host)

**Usage**
<pre>
# ./deploy_ssh_key.exp [remote_user] [remote_user_password] [remote_root_password] [remote_host] [deployed_user_name] [deployed_user_password]
# ./deploy_ssh_key.exp lala lalapass rootpass 10.0.0.95 system-monitor pass
</pre>

### scp_remotefile_to_localfile.exp
**Script do the following tasks:**
- connect to remote system (remote_host) with scp client as user (remote_user) with user password (remote_user_password)
- downloads remote file (remote_file) from remote directory (remote_path) to local directory (local_path) and set name for downloaded file based on pattern "filename-user@host"

**Usage**
<pre>
# ./scp_remotefile_to_localfile.exp [remote_user] [remote_user_password] [remote_host] [remote_file] [remote_path] [local_path]
# ./scp_remotefile_to_localfile.exp system-monitor pass 10.0.0.95 id_dsa /home/system-monitor/.ssh /home/ares/.ssh
</pre>

> Note: Do not use final slash in paths.

### Full example of settings remote system environment for SSH key-based authentication
<pre>
# ./deploy_ssh_key.exp lala lala-password root-password 10.0.0.95 system-monitor system-monitor-password
# ./download_ssh_key.exp system-monitor system-monitor-password 10.0.0.95 id_dsa /home/system-monitor/.ssh /home/ares/.ssh
# ssh system-monitor@10.0.0.95 -i /home/ares/.ssh/id_dsa-system-monitor\@10.0.0.95
</pre>
