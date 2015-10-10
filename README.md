Ansible AWS training provisioner
================================

A crusty way to quickly provision a bunch of machines in AWS using Ansible.

Usage
-----

Ensure you have boto installed and configured, and that your public key is installed in the target region. The AMI IDs are currently hardcoded to the us-west-2 region, and the subnet is the default VPC of the ansible-ps-test account.

Add users to the users list, and ensure that types matches the kind of training you want to do. Then run:

```
ansible-playbook -i hosts infra-aws.yml -e "name_prefix=(yourname)-training aws_key_name=your-pubkey-name"
```

The playbook will start the instances, configure them for password auth, and dump a file for each user with their IPs and credentials into the current directory.

