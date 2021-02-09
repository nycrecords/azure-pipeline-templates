# Install and Configure Terraform and Terragrunt

Install and configure Terraform and Terragrunt on a pool based runner

## Pre-Requisites

The repository using this template needs to have a `.tool-versions` in its root directory with versions defined for Terraform and Terragrunt.

e.g.

``` shell
terragrunt 0.26.7
terraform 0.14.3
```

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
- template: templates/terragrunt-setup/main.yaml@templates
  parameters:
    ssh_private_key_pipelines:
    aws_service_connection: 

```

Parameters
----------

| Parameter                    | Description                                                                | Default  |
| ---------------------------- | -------------------------------------------------------------------------- | :------: |
| ssh_private_key_pipelines[^1] | Name of the private key to use to connect to servers via SSH. | `ssh_automation` |
| aws_service_connection[^1] | Name of the service connection to use to connect to AWS. | `none` |

[^1]: These variables are passed in using a Variable Group in our Azure DevOps Library. Contact [@joelbcastillo](https://github.com/joelbcastillo) if you have any questions.
