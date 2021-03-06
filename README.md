# Ansible Role: container-linux-azure
------------------

An ansible role for deploying multiple Container Linux instances on Azure.

## Requirements
------------------

An Azure account with credentials.  Locally installed and working Azure Client and Ansible[azure].

* Azure Credentials ( ~/.azure/credentials )

```
[default]
subscription_id=$AZURE_SUBSCRIPTION_ID
client_id=$AZURE_CLIENT_ID
secret=$AZURE_SECRET
tenant=$AZURE_TENANT
```

* Azure Credentials ( Environment Variables )

```
AZURE_CLIENT_ID=<YOUR_AZURE_CLIENT_ID>
AZURE_SECRET=<YOUR_AZURE_PASSWORD>
AZURE_SUBSCRIPTION_ID=<YOUR_AZURE_SUBSCRIPTION_ID>
AZURE_TENANT=<YOUR_AZURE_TENANT_ID>
```

## Role Variables
------------------

The following variables are configurable.

### Virtual Machine Name Prefix
The prefix to use for the virtual machine name.  Secondary part of the name is provided by the squence number.

```
virtual_machine_naming_prefix: containerlinux`
```

### Create a new Azure Service Principle

Setting the value to true will create a new service principle.

```
azure_create_new_service_principle: False
azure_service_principle_name: <NEW_SERVICE_PRINCIPLE_NAME>
```

### Azure Install Dynamic Inventory
Download and install the dynamic inventory script.

```
azure_install_dynamic_inventory: False
```

### Azure Resource Group
The name of the Azure Resource Group

```
azure_rg: ContainerLinuxVMs
```

### Azure Resource Group Location
Azure Resource Group Location

```
azure_rg_location: Eastus
```

### Azure Resource Group Network Name
The name of the base network in the Azure resource group.

```
azure_rg_virt_net_name: ContainerLinuxVMsNetwork001
```

### Azure Resource Group Network CIDR
The network address in CIDR format for the base network in the Azure resource group.

```
azure_rg_virt_net_cidr: "10.2.0.0/16"
```

### Azure Resource Group Network Subnet Name
The name of the subnet in the base network in the Azure resource group.

```
azure_rg_virt_subnet_name: ContainerLinuxVMsSubNet001
```

### Azure Resource Group Network Subnet Address
The network address in CIDR format for the subnet in the base network in the Azure resource group.

```
azure_rg_virt_subnet_addr: "10.2.1.0/24"
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

### Azure Virtual Machines Total
The total number of Azure Container Linux virtual machines to be created

```
azure_virtual_machines_total: 2
```

### Container Linux Admin Password
A default password for the Core user.

```
container_linux_admin_password: Fl@tc@rL1nux
```

### Container Linux SKU
Define which Container Linux SKU to use on Azure.  'stable','beta' and 'alpha' are valid options.  'Default is to use the 'alpha'

```
container_linux_sku: 'alpha'
```

### Container Linux Version
Define a specific version of container linux on Azure.  Default is to use the latest version of Container Linux.


```
container_linux_version: latest

```


## Example Playbook
------------------

Here is an example of typical usage.


```
- hosts: localhost
  gather_facts: True
  roles:
    - container-linux-azure
```

## Contributors
------------

 * Peter Pouliot <peter@pouliot.net>

## Copyright and License
---------------------

Copyright (C) 2018 Peter J. Pouliot

Peter Pouliot can be contacted at: peter@pouliot.net

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

  http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
