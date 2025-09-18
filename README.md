## About this repository

This repository contains files, automation code, and utility scripts which I use for my home lab environment and I maintain on a regular basis as part of my lab grooming activities. You are welcome to use any of this a reference to build your own lab

## Repository Structure
This is the current repository structure. This repository is being refactored on a regular cadence, so expect this repository structure to continously evolve.

__ansible_inventory/hosts__ ->  Global ansible inventory used by all these playbooks. \
__ansible_roles__ ->  Roles which I have developed to support my use-cases. \
__playbooks_base_infrastructure__ ->  Playbooks used to setup my home lab infrastructure. Not everything is 100% automated since its always evolving. \
__playbooks_plex_server__ -> Playbooks used to deploy and configure a RHEL Plex server.  Yes, I have one of those too. \
__playbooks_vm_provisioning__ -> Playbooks used to deploy kvm/libvirt virtual machines. \
__playbooks_rh_openstack__ -> Playbooks used to initialize the base infrastructure for a Red Hat OpenStack Platform 16 or 17 home lab deployment. 

```
.
├── LICENSE
├── README.md
├── ansible.cfg
├── ansible_inventory
│   └── hosts
├── ansible_roles
│   ├── centos-bifrost
│   ├── host-setup-common
│   ├── install-osp16-director
│   ├── install-osp17-director
│   ├── kvm-vm-provisioning
│   ├── lab-dns-infra
│   ├── rhel-plex-server-config
│   └── rpi-host-config
├── ansible_vault
│   └── vaulted-vars.yml
├── playbooks_base_infrastructure
│   ├── configure-base-infrastructure-rhel-hosts.yml
│   ├── configure-base-infrastructure-rpi-hosts.yml
│   └── vars
├── playbooks_bifrost
│   ├── configure-bifrost-vm.yml
│   ├── deploy-c9-bifrost-vm.yml
│   └── vars
├── playbooks_kolla_ansible_openstack
│   ├── deploy-director-software-osp17.yml
│   ├── deploy-kvm-rocky-9-single-node.yml
│   └── vars
├── playbooks_plex_server
│   ├── configure-plex-vm.yml
│   ├── deploy-plex-vm.yml
│   └── vars
├── playbooks_rh_openstack
│   ├── deploy-director-software-osp16.yml
│   ├── deploy-director-software-osp17.yml
│   ├── deploy-kvm-openstack-controllers.yml
│   ├── deploy-kvm-osp16-director-vm.yml
│   ├── deploy-kvm-osp17-director-vm.yml
│   └── vars
├── playbooks_vm_provisioning
│   ├── README.md
│   ├── deploy-centos-7-vm.yml
│   ├── deploy-centos-8-streams-vm.yml
│   ├── deploy-centos-9-streams-vm.yml
│   ├── deploy-debian-12-vm.yml
│   ├── deploy-rhel-7-7.vm.yml
│   ├── deploy-rhel-8-vm.yml
│   ├── deploy-rhel-9-vm.yml
│   └── vars
└── repo_assets
    └── diagrams
```

## Lab Diagram and References

This is at best a very high level diagram of my home lab environment. Each line representing a network connections is a mere representation of physical connectivity between hosts, network switch, and network radios.

In reality there is a bit more complexity in the networking design as there are in some cases than one physical network link between the host and its upstream switch port where that switch port is designed to transport both routable and non-routable networks with the primary mechanism for network isolation being 802.1q (vlan encapsulation).

One last remark; The RHEL KVM nodes are standalone RHEL hosts and there is no clustering or high availaiblity mechanism such as o-virt, proxmox, or other similar virtualization management software. Each baremetal node is a standalone baremetal machine designed to be light-weight KVM based virtualization hosts for the intent and purposes of this lab environment.

I hope this is helpful and if any questions, you can always email at berto@acanorex.io. 

![alt text](https://raw.githubusercontent.com/hybridpollo/homelab_infra_automation/main/repo_assets/diagrams/home_lab_diagram_with_border.png "Home Lab Diagram Rev 0.5")

### Use of contents of this repository
You are welcome to copy, fork, ridicule any of the contents of this repository but do not expect any support for any of the code found in this repository. 

### Use of secrets, vaults, and passwords
This repository avoids the use of plain text passwords, secrets, and or any other information that could in some eyes considered details which should not be publicly visible.  To that I say, learn how to secure your shit! and most importantly, do not expose anything in Git{hub,lab} that you do not want to be seen. 


25 directories, 26 files
