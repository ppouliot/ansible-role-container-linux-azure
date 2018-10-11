# Ansible Role: container-linux.azure
------------------

An ansible role for deploying Container Linux instances on Azure

## Requirements
------------------

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
------------------

The following variables are configurable.  Please note that the default values are shown.

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

### Azure Resource Group Network CIDR
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
A default password for the Core user.

```
container_linux_admin_password: Fl@tc@rL1nux
```

## Example Playbook
------------------

Here is an example of typical usage.


```
- hosts: localhost
  gather_facts: True
  roles:
    - container-linux.azure
```

## License
------------------

[Apache 2.0](./LICENSE)

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
