# Terraform modules

- The infrastructure resources required for DevPortal are added in terraform folder of gcp-dev-portal repo.
We have multiple resources like cloud run services, cloud functions, cloud build triggers, workflows etc.
- The terraform code required for these resources is added in terraform folder. There are two folders named configurations and infrastructure under terraform folder.
-Configurations folder has the terraform code to build different types of configurations.
-Infrastructure folder contains are multiple folders, each folder containing terraform code for different resources.
-To create, modify or delete these resources, make the required terraform changes and merge the changes to gcp-dev-portal repo main branch via Pull request. Create a new release.
- Clone terraform-gcp-dev-portal repository, open ‘terraform-gcp-dev-portal\dev0502\terraform-gcp-dev-portal\env\dev’ folder. 
- Locate the relevant module associated with the changes, update the ref to the latest released version and the merge the changes into main branch via Pull request.
- After the changes are merged Open [terraform registry](https://terraform.wellsky.net/app/wellsky/workspaces/gcp-core-svcs-dev), open gcp-core-svcs-dev workspace and apply the latest run. This will create, modify or delete the resources through the changes made in the terraform.

## Data-importer

This folder contains the terraform code to build a ‘data-importer’ cloud run service, its associated resources like service account, cloud run jobs, scheduler, eventarc trigger.

Its associated module in terraform-gcp-devportal repo is ‘data\_importer’ module.

## Project-builder

This folder contains the terraform code to build a ‘project-creator’ cloud build trigger, its yaml code, service account and permissions associated with it.

Its associated module in terraform-gcp-devportal repo is ‘project\_builder’ module.

## Project-cleanup

This folder contains the terraform code to build a ‘project-cleanup’ cloud build trigger, its yaml code, service account and permissions associated with it.

Its associated module in terraform-gcp-devportal repo is ‘project\_cleanup’ module.

## Project-deleter

This folder contains the terraform code to build a ‘project-delete-notifications’ and ‘project-cleanup’ cloud functions along with its service account and scheduler associated with it.

Its associated module in terraform-gcp-dev-portal repo is ‘project\_deleter’ module.

## Services

- Inside services folder, we have modules/access-request-workflow folder. This folder contains the terraform code to build the devportal-workflow and devportal-reminder-workflow and its associated service account.

- within services folder, we have a modules/website-cloudrun folder. This folder contains the code required for building the cloud run services for both DevPortal ui and api. Module frontend builds the devportal-ui cloud run service whereas module backend builds the devportal-api cloud run service.

- To apply terraform for the services folder changes, make changes to module ‘dev\_portal’ in terraform-gcp-dev-portal repo.
