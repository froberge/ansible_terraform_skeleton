# Ansible Terraform Config
This repository contains the Terraform code to provision VM on the different cloud providers.

This repository is part of the [Ansible Terraform Cloud VM Deployment Demo](https://github.com/froberge/ansible_terraform_cloud_vm_deployment)

#### How to run the terraform provisioning localy

###### Prerequisite
* Terraform cli
* :warning: __FORK The repository to encrypt your own files__

###### Steps
1. Enter the proper value in the terraform.tfvars file. 
```
access_key = ""
secret_key = ""
```

1. Initialized the current working directory
    ```
    terraform init
    ```
1. Get a preview of what the code will do
    ```
    terraform plan -var-file="terraform.tfvars"
    ```
1. Apply the desired changes
    ```
    terraform apply -var-file="terraform.tfvars" -auto-approve
    ```

1. :warning: Extra steps to destroy what you just created
```
terraform destroy -var-file="terraform.tfvars" -auto-approve
```

---

Encrypt and Decrypt the important file in `Ansible Vault`

* __Encrypt__
    ```
    ansible-vault encrypt terraform.tfstate terraform.tfstate.backup terraform.tfvars
    ```

* __Decrypt__
    ```
    ansible-vault decrypt terraform.tfstate terraform.tfstate.backup terraform.tfvars
    ```

---