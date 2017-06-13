# Ansible-ceph

This playbook installs a ceph cluster.


## Requirements

It is necessary to have a paswordless ssh connection to each node.

The hostname must resolve to the corresponding ip.
ie: set-up `/etc/hosts` or dns.

Each machine on the cluster must resolve its hostname to its public ip.
ie: no resolving to 127.0.0.1 as default in `/etc/hosts`.

## Configuration

The following files should be set-up the following way:

- group_vars/ceph -> set the hostnames for each daemon node. It is possible
	to have several services on the same node.
- hosts -> set the hostname of the master node. ceph_all must contain the
	hostnames of all nodes, including the master.
- roles/ceph-common/vars/main.yml -> hash of the password for the admin user, default is `ceph`
## Usage

The playbook should be run using `ansible-playbook ceph.yml -i hosts`.
