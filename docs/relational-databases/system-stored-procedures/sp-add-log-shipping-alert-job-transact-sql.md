---
title: "sp_add_log_shipping_alert_job (Transact-SQL)"
description: "sp_add_log_shipping_alert_job (Transact-SQL)"
author: MashaMSFT
ms.author: mathoma
ms.date: "03/14/2017"
ms.service: sql
ms.subservice: system-objects
ms.topic: "reference"
f1_keywords:
  - "sp_add_log_shipping_alert_job_TSQL"
  - "sp_add_log_shipping_alert_job"
helpviewer_keywords:
  - "sp_add_log_shipping_alert_job"
dev_langs:
  - "TSQL"
---
# sp_add_log_shipping_alert_job (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  This stored procedure checks to see if an alert job has been created on this server. If an alert job does not exist, this stored procedure creates the alert job and adds its job ID to the **log_shipping_monitor_alert** table. The alert job is enabled by default and runs on a schedule of once every two minutes.  
  
 :::image type="icon" source="../../includes/media/topic-link-icon.svg" border="false"::: [Transact-SQL syntax conventions](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## Syntax  
  
```  
  
sp_add_log_shipping_alert_job  
[, [ @alert_job_id = ] alert_job_id OUTPUT ]  
```  
  
## Arguments  
`[ @alert_job_id = ] alert_job_id OUTPUT`
 The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job ID of the log shipping alert job.  
  
## Return Code Values  
 0 (success) or 1 (failure)  
  
## Result Sets  
 None  
  
## Remarks  
 **sp_add_log_shipping_alert_job** must be run from the **master** database on the monitor server.  
  
## Permissions  
 Only members of the **sysadmin** fixed server role can run this procedure.  
  
## Examples  
 This example shows the execution of **sp_add_log_shipping_alert_job** to create an alert job ID.  
  
```  
USE master  
GO  
EXEC sp_add_log_shipping_alert_job;  
```  
  
## See Also  
 [About Log Shipping &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md)   
 [System Stored Procedures &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
