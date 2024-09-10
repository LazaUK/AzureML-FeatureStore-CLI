# Azure Machine Learning - Feature Store (CLI Setup)

Azure Machine Learning's (Azure ML) **_feature store_** is a centralised repository for storing, managing and retrieving features used in ML models. It simplifies feature engineering through scalable and efficient way to reuse features across multiple projects.

This tutorial will explain how to setup online and offline feature stores in Azure Machine Learning (Azure ML), using Azure command-line interface (Az CLI). Online materialisation is enabled by in-memory key/value management in _Azure Redis Cache_, while offline materialisation utilises ADLS Gen2 (Azure Data Lake Storage - 2nd Generation) account.



