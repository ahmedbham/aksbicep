1. ssh-keygen -m PEM -t rsa -b 4096
2. curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash
3. az login --use-device-code
4. Create an Azure Active Directory application and a service principal:
  1. az ad app create --display-name myOidcApp
  1. SUBSCRIPTION_ID=$(az account show --query id --output tsv) 
  1. TENANT_ID=$(az account show --query tenantId --output tsv)
  1. APPLICATION_ID=$(az ad app list --display-name myOidcApp --query [0].appId --output tsv)
1. export LOCATION=eastus
1. export RESOURCE_GROUP=oidc-rg
1. az group create -g $RESOURCE_GROUP --location $LOCATION