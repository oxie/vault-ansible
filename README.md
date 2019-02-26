### This a collection of Ansible roles to install and configure Consul + Vault

Ansible 2.1 or higher required.
---

The sample command to run when you want to install vault cluster.
   ```
   ansible-playbook -i hosts/HOSTFILE vault-config.yml --user USER --extra-vars "@group_vars/VAR_FILE.yml"
   ```

**HOSTFILE** should be maintained for each environment separately.
You need at least two VMs for the vault cluster and two for the consul cluster.
To make sure the consul agents install on the vault servers the vault server names/ips should be added to the groups vault-consul and consul-agent in the host file.
The consul servers will be installed on the group consul-server.

**USER** needs to have sudo privilege on remote machine. Passing in --user allows for the executor to define the ansible_ssh_user(user that will be used to connect to the remote machine by ansible) at the command line.

**VAR_FILE** defines variables for vault user config and if a consul server and cluster is required.

###### TO DO:
- Put details about the Consul servers setup
- Put details about the Consul agents setup
- Put details about the Vault servers setup