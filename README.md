# Ansible Role: container-linux-azure
------------------

An ansible role for deploying Container Linux instances on Azure



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

The following variables are configurable.  Please note that the default values are shown.

### Create a new Azure Service Principle

Setting the value to true will create a new service principle.

```
azure_create_new_service_principle: False
azure_service_principle_name: <NEW_SERVICE_PRINCIPLE_NAME>
```

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

### Container Linux Admin Password
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
