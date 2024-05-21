# Get started
```
execute in azure cloud shell:
az ad sp create-for-rbac --name sp_dev101 --role Contributor --scopes /subscriptions/<subs-id>
{
  "appId": "sp-clientid",
  "displayName": "sp_dev101",
  "passw0rd": "sp-pass",
  "tenant": "tenant-id"
}

execute in your local sandbox bash terminal:
az login --service-principal -u "sp-clientid" --tenant "tenant-id"
az account set -s subs-id

clone repo and execute terraform
terraform init -upgrade
terraform plan -out main.tfplan
terraform apply main.tfplan
terraform apply -destroy
```