# Azure Machine Learning - Feature Store (CLI Setup)

Azure Machine Learning's (Azure ML) **_feature store_** is a centralised repository for storing, managing and retrieving features used by ML models. It simplifies feature engineering through scalable and efficient way to reuse features across multiple projects.

This tutorial will explain how to setup online and offline feature stores in Azure Machine Learning (Azure ML), using Azure command-line interface (Az CLI). Online materialisation is enabled by in-memory key/value management in _Azure Redis Cache_, while offline materialisation utilises _ADLS Gen2_ (Azure Data Lake Storage - 2nd Generation) account.

## Table of contents:
- [Step 1: Installing Az CLI's ML extension]()
- [Step 2: Creating ADLS Gen2 storage account]()
- [Step 3: Creating container on ADLS Gen2 storage]()
- [Step 4: Creating Redis Cache instance]()
- [Step 5: Creating user-assigned Managed Identity]()
- [Step 6: Creating Azure ML feature store]()
- [HOUSEKEEPING: Deleting feature store]()

## Step 1: Installing Az CLI's ML extension

