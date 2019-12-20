# arm-templates-sample-app-service-key-vault

ARM templates sample that is combination Azure App Service and Azure Key Vault.

```ps1
$RESOURCE_GROUP="<Put a new resource group name>"
$LOCATION="japaneast"
$PREFIX="<Put prefix string within 9 characters>"

az group create `
  --name $RESOURCE_GROUP `
  --location $LOCATION

az group deployment validate `
  --resource-group $RESOURCE_GROUP `
  --template-file .\template.json `
  --handle-extended-json-format `
  --parameters `
      prefix=$PREFIX

az group deployment create `
  --resource-group $RESOURCE_GROUP `
  --template-file .\template.json `
  --handle-extended-json-format `
  --parameters `
      prefix=$PREFIX
```
