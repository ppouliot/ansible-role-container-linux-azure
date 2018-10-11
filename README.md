# Ansible Role: container-linux.azure

An ansible role for deploying Container Linux instances on Azure

## Requirements

An Azure account with a working Azure Client and Ansible[azure].


## Role Variables

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

```
 defaults file for container-linux.azure
azure_rg: FlatcarVMs
azure_rg_location: Eastus
azure_rg_virt_net_name: FlatcarVMsNetwork001
azure_rg_virt_net_addr: "10.2.0.0/16"
azure_rg_virt_subnet_name: FlatcarVMsSubNet001
azure_rg_virt_subnet_addr: "10.2.1.0/24"
azure_rg_sec_group: FlatcarNetworkSecurityGroup001
azure_vm_size: Standard_B1ms
azure_managed_disk_type: Premium_LRS
coreos_admin_password: Fl@tc@rL1nux
```

## Dependencies

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

## Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```
- hosts: localhost
  gather_facts: True
  roles:
    - container-linux.azure
```

## License

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).