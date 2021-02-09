Terragrunt Apply
================

Applies a terraform configuration using terragrunt apply.

Pre-Requisites
--------------

You should run the [terragrunt-setup](../terragrunt-setup/README.md) template before running this configuration to make sure terragrunt and terraform are installed and configured properly.

Usage
-----

```yaml
resources:
  repositories:
    - repository: templates
      type: github
      name: nycrecords/azure-pipeline-templates
      ref: refs/tags/v1
jobs:
- template: templates/terragrunt-apply/main.yaml@templates
  parameters:
    pool: 
    azure_service_connection: 
    arm_environment: 
    arm_subscription_id: 
    workdir:
    tf_apply_command_options: 
```

Parameters
----------

| Parameter                    | Description                                                                | Default  |
| ---------------------------- | -------------------------------------------------------------------------- | :------: |
| pool[^1]                     | The name of the AKS pool to use to run the pipeline.                       |  `none`  |
| azure_service_connection[^1] | The name of the Azure Service Connection used to perform actions in Azure. |  `none`  |
| arm_environment[^1]          | he Cloud Environment which should be used.                                 | `public` |
| arm_subscription_id[^1]      | The Subscription ID which should be used.                                  |  `none`  |
| workdir                      | The directory in which to run the terragrunt command.                      |   '.'    |
| tf_apply_command_options[^1] | Options to pass into the terraform apply command.                          |  `none`  |

[^1]: These variables are passed in using a Variable Group in our Azure DevOps Library. Contact [@joelbcastillo](https://github.com/joelbcastillo) if you have any questions.
