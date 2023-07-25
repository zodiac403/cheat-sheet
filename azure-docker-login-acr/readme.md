# Azure | Docker login to Azure Container Registry

## Change active subscription

[MS docs | Change the active subscription](https://docs.microsoft.com/en-us/cli/azure/manage-azure-subscriptions-azure-cli#change-the-active-subscription)

```sh
# change the active subscription using the subscription name
az account set --subscription "My Demos"
```

## Get access token for Azure Container Registry

[MS docs | az acr login with --expose-token](https://docs.microsoft.com/en-us/azure/container-registry/container-registry-authentication?tabs=azure-cli#az-acr-login-with---expose-token)

```sh
az acr login --expose-token --name <acrName>
```

## Docker login

```sh
docker login loginServer -u 00000000-0000-0000-0000-000000000000 -p accessToken
```
