---
title: Azure PostgreSQL libraries for Python
description: 
keywords: Azure, Python, SDK, API, SQL, database, PostGres, PostgreSQL
author: lisawong19
ms.author: liwong
manager: douge
ms.date: 06/12/2017
ms.topic: article
ms.prod: azure
ms.technology: azure
ms.devlang: python
ms.service: postgresql
---

#Azure PostgreSQL libraries for Python

## Overview
The recommended client library for accessing Azure Database for PostgreSQL is the Microsoft [ODBC driver](https://docs.microsoft.com/azure/sql-database/sql-database-connect-query-python#install-the-python-and-database-communication-libraries). Use the ODBC driver to connect to the database and execute SQL statements directly.

Learn more about [Azure Database for PostgreSQL](https://docs.microsoft.com/azure/postgresql/).

## Install the libraries
```bash
pip install azure-mgmt-rdbms
```
## Example
Connect to a Azure Database for PostgreSQL and select all records in the sales table. You can get the ODBC connection string for the database from the Azure Portal.

```python
server = SERVER_NAME+'.postgres.database.azure.com'
database = DATABASE_NAME
username = USER_NAME
password = PASSWORD
driver = '{PostgreSQL ODBC Driver}'

cnxn = pyodbc.connect(
    'DRIVER=' + driver + ';PORT=5432;SERVER=' + server + ';PORT=5432;DATABASE=' + database + ';UID=' + username + ';PWD=' + password)
cursor = cnxn.cursor()
selectsql = "SELECT * FROM SALES"
cursor.execute(selectsql)
```


Explore more [sample Python code](https://azure.microsoft.com/resources/samples/?platform=python) you can use in your apps.
