# Ansible Inventory

Inventories organize managed nodes in centralized files that provide Ansible with system information and network locations. Using an inventory file, Ansible can manage a large number of hosts with a single command.

To complete the following steps, you will need the IP address or fully qualified domain name (FQDN) of at least one host system.

As you can see, this inventory file configures Ansible to connect to two different hosts using SSH (local and remote), specifying the user and private key () for each host. Using SSH keys for authentication is a common and secure practice for managing access to remote servers.

## local_node

local_node is the alias for the first host defined in the file. This alias is used in playbooks to specifically refer to this host.

• __ansible_user=k3s__ : Specifies the user (k3s) to use for the SSH connection to local_node.

• __ansible_ssh_host=192.168.1.51__ : Indicates the IP address (192.168.1.51) of local_node. This is the address Ansible uses to establish the SSH connection.

• __ansible_ssh_private_key_file=~/.ssh/id_rsa__ : Path to the SSH private key (~/.ssh/id_rsa) to use for authentication with local_node. This path must be accessible from the machine from which you are running Ansible.

## remote_node

remote_node functions similarly to local_node but refers to a different host, presumably located in a remote network or on the Internet.

• __ansible_user=netgroup__ : Specifies the user (netgroup) to use for the SSH connection to remote_node.

• __ansible_ssh_host=130.192.225.117__ : Provides the IP address (130.192.225.117) of remote_node. This is the address Ansible will use to attempt the SSH connection.

• __ansible_ssh_private_key_file=~/.ssh/id_rsa__ : Path to the SSH private key, the same one used for local_node, for authentication with remote_node.
