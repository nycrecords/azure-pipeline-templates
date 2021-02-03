# Azure Pipeline Templates

Common Azure Pipeline tasks for DevOps automation.

## Usage

The templates are meant to be included into a project pipeline. 

### Best Practices

- Always specify the reference tag when including a pipeline in your template to avoid breaking the workflow when a new template version is released.
- Pipeline templates should not have default values (whenever possible). Assume the upstream pipeline will be providing all the values.

## Current  Templates

N/A

## Contributing

### Create a new template

- Create a folder for your template in the `/templates` directory.
  - The name should be the name of the template (e.g. `terragrunt-deploy`)
- In the folder, create a `yaml` file (the name is not important, but it should be clear)
- In the same folder create a `README` file with:
  - A brief description of the template
  - An example snippet describing the usage of the template
  - A full parameters table
- Add an entry in the `Available Templates` section of the main `README` file (this file) with a link to the `README` of the template you created.

### Testing

TBD

### Release a new version

TBD


