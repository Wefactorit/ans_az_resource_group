# Role to manage Azure Resource group
----------------------------------

**This DNS Ansible role**, can allow you to easily create one or many resource group

## Overview
----------------------------------
This role create a resource group in AZURE , if you need more information about resource group in AZURE [here](https://azure.microsoft.com/en-us/updates/resource-groups-in-azure-preview-portal/).


## Requirements
----------------------------------
- Ansible 2.8.4
- AZ cli 2.0.52
- Azure 2.0.0
- python 2.7


## Installation
---------------------------------

First, make sur you have [Ansible](https://www.ansible.com/)  and [azcli](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest) on your machine.


## Usage
---------------------------------


You can use this playbook by modify variables as you need. And tun the command below to provision your resource group:
```
ansible-playbook -i tests/inventory tests/main.yml
```

If you want to delete the Resource group just run:

```
ansible-playbook -i tests/inventory tests/main.yml -e"state=absent"
```
 Note that you can create more than one at once by duplicate the domain name block from defaults variables like this:

```
resource_group_def:
  - resource_group_name: name
    location: northeurope
    tag_contact: contact_name
    tag_project: Project_name
    tag_stage: Dev
    tag_cost_center:  Datacenter_north
```

You can add as many resource group as you need.


## Variables
-----------------------------------------------

#### GENERAL

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-----:|:-----:|
| resource_group_name | Variable for your domain name | string | - | yes |
| location | The resource group targeted for this Resource Group zone | string | - | yes |
| type | The type of the DNS zone private or public| string | - | yes |
| tag_contact |An arbitrary contact tag  | string | - | yes |
| tag_project |Another arbitrary tag| string | - | yes |
| tag_stage   |Another arbitrary tag to identify stage| string | - | yes |
| tag_cost_center | This tag can help you | string | - | yes |








## Contributing
---------------------------------
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.



## Next improvements
----------------------------------

## Author
----------------------------------
- [Sype](https://github.com/sype), DevOps engineer.

## Acknowlegement
----------------------------------
Thank Wefactorit Team.
