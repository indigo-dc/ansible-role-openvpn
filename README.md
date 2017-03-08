[![License](https://img.shields.io/badge/license-Apache%202-blue.svg)](https://www.apache.org/licenses/LICENSE-2.0)
[![Build Status](https://travis-ci.org/grycap/ansible-role-openvpn.svg?branch=master)](https://travis-ci.org/grycap/ansible-role-openvpn)

OpenVPN Role
============

Ansible role to install OpenVPN to enable deploying hybrid elastic clusters.

Role Variables
--------------

The variables that can be passed to this role and a brief description about them are as follows.

	# Type of the node: front or wn
	openvpn_type_of_node: "front"
	# Hostname of the front node
	openvpn_frontname: "slurmserver"
	# Flag to specify if the wn role will manage the /etc/hosts file to set the VPN net ips
	manage_etc_hosts: true
	# VPN subnet
	openvpn_server_net: 10.8.0.0
	# VPN subnet mask
	openvpn_server_net_mask: 255.255.255.0
	# VPN server IP (must be the first IP of the openvpn_server_net)
	openvpn_server_vpn_ip: 10.8.0.1


Example Playbook
----------------
```
  - hosts: server
  roles:
  - { role: 'indigo-dc.openvpn', openvpn_type_of_node: "front" }
```
```
  - hosts: client
  roles:
  - { role: 'indigo-dc.openvpn', openvpn_type_of_node: "wn" }
```

Contributing to the role
========================
In order to keep the code clean, pushing changes to the master branch has been disabled. If you want to contribute, you have to create a branch, upload your changes and then create a pull request.  
Thanks
