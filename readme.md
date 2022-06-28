# Machine configuration data [WIP]

This is a repo that contains the machine configuration data. It is a work in progress.

To serve machine configuration data to the machinegen CLI tool, you need to maintain the following structure:

- A `tables` folder
- A `terraform` folder
- A `templates` folder

## Config Definition tables

This tables are used by the prereqs build script to load as required configs and understand what needs to be done where, and to generate the schema for the user-provided config file. They can be found under the `./tables` directory.

The `tables` folder must containing three `.csv` files:

- `files.csv`
- `replace.csv`
- `templates.csv`

Check the [folder in this repo](https://github.com/nodoambiental/machinegen-config/tree/master/tables) for more information.

## Templates

The templates are used by the prereqs build script as a way to process recurrent data and config files for its need while being able to include user-provided data. They can be found under the `./templates` directory.

The `templates` folder must containing `.template` files as defined by the `templates.csv` file. In this config it has:

- `metadata.yaml.template`
- `nebula-config.yaml.template`
- `terraform-config.tf.template`
- `user-data.yaml.template`

Check the [folder in this repo](https://github.com/nodoambiental/machinegen-config/tree/master/templates) for more information.

## Terraform

The `terraform` folder must containin the base needed files to build the terraform project. This means a `main.tf` is required, but you can also include here stuff like `variables.tf` and `providers.tf`. this folder will be used to init, plan and apply the project, so make sure the files work.
