# Azure User Assigned Managed Identity Terraform Module

Terraform module to create a User Assigned Managed Identity.

# Table of Contents

- [Azure Resource Naming Convention](#azure-resource-naming-convention)
    - [Format](#Format)
    - [Components](#Components)
- [Requirements](#requirements)
- [Providers](#providers)
- [Modules](#modules)
- [Resources](#resources)
- [Inputs](#inputs)
- [Outputs](#outputs)

## Azure Resource Naming Convention

Resource names should clearly indicate their type, workload, environment, and region. Using a consistent naming convention ensures clarity, uniformity, and easy identification across all repositories.

#### Format

```
<resource_prefix>-<app_or_project>-<environment>-<region>-<optional_unique_suffix>
```

#### Components

| **Component**           | **Description**                                                                      | **Example**             |
|--------------------------|--------------------------------------------------------------------------------------|-------------------------|
| `resource_prefix`        | Short abbreviation for the resource type.                                           | `rg` (Resource Group)   |
| `app_or_project`         | Identifier for the application or project.                                          | `qoh`           |
| `environment`            | Environment where the resource is deployed (`prod`, `dev`, `test`, etc.).           | `prod`                 |
| `region`                 | Azure region where the resource resides (e.g., `cus` for `centralus`).              | `cus`                  |
| `optional_unique_suffix` | Optional unique string for ensuring name uniqueness, often random or incremental.    | `abcd`, `a42n`                 |

## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | >=0.13 |
| <a name="requirement_azurerm"></a> [azurerm](#requirement\_azurerm) | >=4.0.0 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_azurerm"></a> [azurerm](#provider\_azurerm) | >=4.0.0 |

## Modules

No modules.

## Resources

| Name | Type |
|------|------|
| [azurerm_user_assigned_identity.user_assigned_identity](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/user_assigned_identity) | resource |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_location"></a> [location](#input\_location) | (Required) The Azure Region where the User Assigned Identity should exist. Changing this forces a new User Assigned Identity to be created. | `string` | n/a | yes |
| <a name="input_name"></a> [name](#input\_name) | (Required) Specifies the name of this User Assigned Identity. Changing this forces a new User Assigned Identity to be created. | `string` | n/a | yes |
| <a name="input_resource_group_name"></a> [resource\_group\_name](#input\_resource\_group\_name) | (Required) Specifies the name of the Resource Group within which this User Assigned Identity should exist. Changing this forces a new User Assigned Identity to be created. | `string` | n/a | yes |
| <a name="input_tags"></a> [tags](#input\_tags) | (Optional) A mapping of tags to assign to the resource. | `map(any)` | `{}` | no |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_client_id"></a> [client\_id](#output\_client\_id) | The ID of the app associated with the Identity. |
| <a name="output_id"></a> [id](#output\_id) | The ID of the User Assigned Identity. |
| <a name="output_name"></a> [name](#output\_name) | The Name of the User Assigned Identity. |
| <a name="output_principal_id"></a> [principal\_id](#output\_principal\_id) | The ID of the Service Principal object associated with the created Identity. |
| <a name="output_tenant_id"></a> [tenant\_id](#output\_tenant\_id) | The ID of the Tenant which the Identity belongs to. |
