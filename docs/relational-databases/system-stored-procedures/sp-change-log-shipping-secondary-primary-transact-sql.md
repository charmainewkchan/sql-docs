---
title: "sp_change_log_shipping_secondary_primary (Transact-SQL)"
description: "sp_change_log_shipping_secondary_primary (Transact-SQL)"
author: MashaMSFT
ms.author: mathoma
ms.date: "03/14/2017"
ms.service: sql
ms.subservice: system-objects
ms.topic: "reference"
f1_keywords:
  - "sp_change_log_shipping_secondary_primary"
  - "sp_change_log_shipping_secondary_primary_TSQL"
helpviewer_keywords:
  - "sp_change_log_shipping_secondary_primary"
dev_langs:
  - "TSQL"
---
# sp_change_log_shipping_secondary_primary (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Changes secondary database settings.  
  
 :::image type="icon" source="../../includes/media/topic-link-icon.svg" border="false"::: [Transact-SQL syntax conventions](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## Syntax  
  
```  
  
sp_change_log_shipping_secondary_primary  
[ @primary_server = ] 'primary_server',  
[ @primary_database = ] 'primary_database',  
[, [ @backup_source_directory = ] 'backup_source_directory']  
[, [ @backup_destination_directory = ] 'backup_destination_directory']  
[, [ @file_retention_period = ] file_retention_period]  
[, [ @monitor_server_security_mode = ] monitor_server_security_mode]  
[, [ @monitor_server_login = ] 'monitor_server_login']  
[, [ @monitor_server_password = ] 'monitor_server_password']  
```  
  
## Arguments  
`[ @primary_server = ] 'primary_server'`
 The name of the primary instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] in the log shipping configuration. *primary_server* is **sysname** and cannot be NULL.  
  
`[ @primary_database = ] 'primary_database'`
 Is the name of the database on the primary server. *primary_database* is **sysname**, with no default.  
  
`[ @backup_source_directory = ] 'backup_source_directory'`
 The directory where transaction log backup files from the primary server are stored. *backup_source_directory* is **nvarchar(500)** and cannot be NULL.  
  
`[ @backup_destination_directory = ] 'backup_destination_directory'`
 The directory on the secondary server where backup files are copied to. *backup_destination_directory* is **nvarchar(500)** and cannot be NULL.  
  
`[ @file_retention_period = ] 'file_retention_period'`
 Is the length of time in minutes in which the backup files will be retained. *file_retention_period* is **int**, with a default of NULL. A value of 14420 will be used if none is specified.  
  
`[ @monitor_server_security_mode = ] 'monitor_server_security_mode'`
 The security mode used to connect to the monitor server.  
  
 1 = Windows Authentication;  
  
 0 = [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication. *monitor_server_security_mode* is **bit** and cannot be NULL.  
  
`[ @monitor_server_login = ] 'monitor_server_login'`
 Is the username of the account used to access the monitor server.  
  
`[ @monitor_server_password = ] 'monitor_server_password'`
 Is the password of the account used to access the monitor server.  
  
## Return Code Values  
 0 (success) or 1 (failure)  
  
## Result Sets  
 None  
  
## Remarks  
 **sp_change_log_shipping_secondary_primary** must be run from the **master** database on the secondary server. This stored procedure does the following:  
  
1.  Changes settings in the **log_shipping_secondary** records as necessary.  
  
2.  If the monitor server is different from the secondary server, changes monitor record in **log_shipping_monitor_secondary** on the monitor server using supplied arguments, if necessary.  
  
## Permissions  
 Only members of the **sysadmin** fixed server role can run this procedure.  
  
## See Also  
 [About Log Shipping &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md)   
 [System Stored Procedures &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
