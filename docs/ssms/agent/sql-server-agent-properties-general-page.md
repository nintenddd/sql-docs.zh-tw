---
title: SQL Server Agent 屬性 (一般頁面) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.component: ssms-agent
ms.reviewer: ''
ms.suite: sql
ms.technology: ssms
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql13.ag.agent.general.f1
ms.assetid: b51601e9-5454-43c6-bb5e-24eb2ff043c8
caps.latest.revision: 4
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: = azuresqldb-mi-current || >= sql-server-2016 || = sqlallproducts-allversions
ms.openlocfilehash: 9fae50bb7b88e7ea2f291fc0baa375b46f0a380c
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2018
---
# <a name="sql-server-agent-properties-general-page"></a>SQL Server Agent 屬性 (一般頁面)
[!INCLUDE[appliesto-ss-asdbmi-xxxx-xxx-md](../../includes/appliesto-ss-asdbmi-xxxx-xxx-md.md)]

> [!IMPORTANT]  
> [Azure SQL Database 受控執行個體](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance)目前支援多數 (但非全部) 的 SQL Server Agent 功能。 如需詳細資料，請參閱 [Azure SQL Database 受控執行個體與 SQL Server 之間的 T-SQL 差異](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance-transact-sql-information#sql-server-agent)。

使用此頁面來檢視和修改 [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent 服務的一般屬性。  
  
## <a name="options"></a>選項。  
**服務狀態**  
顯示 [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent 服務的目前狀態。  
  
**如果 SQL Server 非預期地停止，則自動予以重新啟動**  
[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] 如果 [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] 非預期地停止，Agent 就會重新啟動 [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] 。  
  
**如果 SQL Server Agent 非預期地停止，則自動予以重新啟動**  
[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] 如果 [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent 非預期地停止，就會重新啟動 [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent。  
  
**檔名**  
指定錯誤記錄檔的檔案名稱。  
  
**...**  
瀏覽錯誤記錄檔。  
  
**包含執行追蹤訊息**  
在錯誤記錄檔中包含執行追蹤訊息。 追蹤訊息提供 [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent 作業的詳細資訊。 因此，選取此選項時，記錄檔需要更多磁碟空間。 只有在疑難排解與 [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent 相關的問題時，才應該選取此選項。  
  
**寫入 OEM 檔**  
將錯誤記錄檔寫成非 Unicode 檔案。 如此可減少記錄檔所用的磁碟空間大小。 不過，啟用此選項時，可能更難以讀取包含 Unicode 資料的訊息。  
  
**Net Send 收件者**  
鍵入接收 [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent 寫入記錄檔之訊息的 Net Send 通知的操作員名稱。  
  
## <a name="see-also"></a>另請參閱  
[運算子](../../ssms/agent/operators.md)  
[SQL Server Agent 錯誤記錄檔](../../ssms/agent/sql-server-agent-error-log.md)  
  
