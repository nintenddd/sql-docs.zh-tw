---
title: J o b s (TRANSACT-SQL) |Microsoft 文件
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-tables
ms.reviewer: ''
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: language-reference
applies_to:
- SQL Server
f1_keywords:
- MSdynamicsnapshotjobs_TSQL
- MSdynamicsnapshotjobs
dev_langs:
- TSQL
helpviewer_keywords:
- MSdynamicsnapshotjobs system table
ms.assetid: 4f36a325-0e3c-46c4-aeeb-416346cce0bc
caps.latest.revision: 26
author: edmacauley
ms.author: edmaca
manager: craigg
ms.openlocfilehash: 8cdfc74bad45bcb3e77bfdf8b438df45e1491633
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2018
---
# <a name="msdynamicsnapshotjobs-transact-sql"></a>MSdynamicsnapshotjobs (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  **MSdynamicsnapshotjobs**資料表會追蹤產生篩選的資料快照集所參數化資料列篩選器資訊。 這份資料表儲存在發行集和訂閱資料庫中。  
  
|資料行名稱|資料類型|Description|  
|-----------------|---------------|-----------------|  
|**id**|**int**|篩選資料快照集作業的識別碼。|  
|**name**|**sysname**|篩選資料快照集作業的名稱。|  
|**pubid**|**uniqueidentifier**|這個發行集的唯一識別碼。|  
|**job_id**|**uniqueidentifier**|在散發者的 SQL Server Agent 作業識別碼。|  
|**agent_id**|**int**|SQL Server Agent 的識別碼。|  
|**dynamic_filter_login**|**sysname**|值，用來評估[SUSER_SNAME](../../t-sql/functions/suser-sname-transact-sql.md)函式參數化資料列篩選器中定義發行集。|  
|**dynamic_filter_hostname**|**sysname**|值，用來評估[HOST_NAME](../../t-sql/functions/host-name-transact-sql.md)函式參數化資料列篩選器中定義發行集。|  
|**dynamic_snapshot_location**|**nvarchar(255)**|如果使用已篩選資料快照集的話，便是要讀取之快照集檔案的資料夾路徑。|  
|**partition_id**|**int**|作業所屬的資料分割識別碼。|  
  
## <a name="see-also"></a>另請參閱  
 [複寫資料表 &#40;Transact-SQL&#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)  
  
  
