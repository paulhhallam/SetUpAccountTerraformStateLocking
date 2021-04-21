To configure the terraform state locking using S3 
This should be run before any other account terraform setup.

1)      Set the required variables in ../accountdetails.tfvars
	An example file is available as "../default_accountdetails.tfvars"

	The unique account_id value must be defined in this file and it must be a unique name as it is used for an S3 bucket name.

This file will:

A) Create an S3 bucket with versioning and encryption enabled called account-state-file

B) Create a dynamodb table called State_Locks to hold the Terraform lock id.

Run the command:
        terraform apply -var-file="../accountdetails.tfvars"

