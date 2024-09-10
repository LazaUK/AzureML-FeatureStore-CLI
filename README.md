# Azure Machine Learning - Feature Store (CLI Setup)

**_Feature Store_** in Azure Machine Learning (Azure ML) is a centralised repository for storing, managing and retrieving features used by ML models. It simplifies feature engineering through scalable and efficient way to reuse features across multiple projects.

This tutorial will explain how to setup online and offline feature stores in Azure ML, using Azure command-line interface (Az CLI). Online materialisation is enabled by in-memory key/value management in _Azure Redis Cache_, while offline materialisation utilises _ADLS Gen2_ (Azure Data Lake Storage - 2nd Generation) account.

## Table of contents:
- [Step 1: Installing Az CLI's ML extension](https://github.com/LazaUK/AzureML-FeatureStore-CLI#step-1-installing-az-clis-ml-extension)
- [Step 2: Creating ADLS Gen2 storage account](https://github.com/LazaUK/AzureML-FeatureStore-CLI#step-2-creating-adls-gen2-storage-account)
- [Step 3: Creating container on ADLS Gen2 storage]()
- [Step 4: Creating Redis Cache instance]()
- [Step 5: Creating user-assigned Managed Identity]()
- [Step 6: Creating Azure ML feature store]()
- [HOUSEKEEPING: Deleting feature store]()

## Step 1: Installing Az CLI's ML extension
To interact with Azure ML through Az CLI, you need to install ML extension:
``` Bash
az extension add --name ml
```

## Step 2: Creating ADLS Gen2 storage account
Now create an ADLS Gen2 account, that will be used as a default storage account by your feature store:
``` Bash
az storage account create --name <STORAGE_ACCOUNT_NAME> --enable-hierarchical-namespace true --resource-group <RESOURCE_GROUP_NAME> --location <AZ_REGION> --subscription <AZ_SUBSCRIPTION_ID>
```
> Note: Replace ```<STORAGE_ACCOUNT_NAME>```, ```<RESOURCE_GROUP_NAME>```, ```<AZ_REGION>``` and ```<AZ_SUBSCRIPTION_ID>``` with required Storage account values.

## Step 3: Creating container on ADLS Gen2 storage
Once you created a Storage account, you can setup a blob container that will be used by the feature store for offline materialisation:
``` Bash
az storage fs create --name <STORAGE_CONTAINER_NAME> --account-name <STORAGE_ACCOUNT_NAME> --subscription <AZ_SUBSCRIPTION_ID> --connection-string <CONNECTION_STRING>
```
> Note: Replace ```<STORAGE_CONTAINER_NAME>```, ```<STORAGE_ACCOUNT_NAME>```, ```<CONNECTION_STRING>``` and ```<AZ_SUBSCRIPTION_ID>``` with required Storage account's container values.

