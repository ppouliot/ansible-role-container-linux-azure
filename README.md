# Ansible Role: container-linux.azure

An ansible role for deploying Container Linux instances on Azure

## Requirements

An Azure account with a working Azure Client and Ansible[azure].

### Azure Credentials ( ~/.azure/credentials )

```
[default]
subscription_id=$AZURE_SUBSCRIPTION_ID
client_id=$AZURE_CLIENT_ID
secret=$AZURE_SECRET
tenant=$AZURE_TENANT
```


## Role Variables

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

### Azure Resource Group
The name of the Azure Resource Group

```
azure_rg: FlatcarVMs
```

### Azure Resource Group Location
Azure Resource Group Location

```
azure_rg_location: Eastus
```

### Azure Resource Group Network Name
The name of the base network in the Azure resource group.

```
azure_rg_virt_net_name: FlatcarVMsNetwork001
```

### Azure Resource Group Network CIDR"
The network address in CIDR format for the base network in the Azure resource group.

```
azure_rg_virt_net_cidr: "10.2.0.0/16"
```

### Azure Resource Group Network Subnet Name
The name of the subnet in the base network in the Azure resource group.

```
azure_rg_virt_subnet_name: FlatcarVMsSubNet001
```

### Azure Resource Group Network Subnet Address
The network address in CIDR format for the subnet in the base network in the Azure resource group.

```
azure_rg_virt_subnet_addr: "10.2.1.0/24"
```

### Azure Resource Group Security Group Name
The name of the Security group under the Azure resource group.

```
azure_rg_sec_group: FlatcarNetworkSecurityGroup001
```

### Azure Virtual Machine Size
The size of the virtual machine to deploy on Azure.

```
azure_vm_size: Standard_B1ms
```

### Azure Managed Disk Type
The managed disk type to deploy your Azure virtual machine on.

```
azure_managed_disk_type: Premium_LRS
```

### CoreOS Admin Password
A default password for the CoreOS user.

```
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

[Apache 2.0](./LICENSE)

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
