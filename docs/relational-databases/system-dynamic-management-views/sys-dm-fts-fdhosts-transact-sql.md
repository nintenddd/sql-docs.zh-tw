---
title: sys.dm_fts_fdhosts (TRANSACT-SQL) |Microsoft 文件
ms.custom: ''
ms.date: 03/29/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- dm_fts_fdhosts
- dm_fts_fdhosts_TSQL
- sys.dm_fts_fdhosts
- sys.dm_fts_fdhosts_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_fts_fdhosts dynamic management view
- troubleshooting [SQL Server], full-text search
ms.assetid: d42a6334-4362-4361-83da-f8324fe55ec7
caps.latest.revision: 13
author: douglaslMS
ms.author: douglasl
manager: craigg
monikerRange: = azuresqldb-current || >= sql-server-2016 || = sqlallproducts-allversions
ms.openlocfilehash: 9671d5a411b12b2cdc7225f215a43c27d19de10c
ms.sourcegitcommit: 7019ac41524bdf783ea2c129c17b54581951b515
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/23/2018
---
# <a name="sysdmftsfdhosts-transact-sql"></a>sys.dm_fts_fdhosts (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  傳回伺服器執行個體上篩選背景程式主機之目前活動的相關資訊。  
  
 
|資料行名稱|資料類型|Description|  
|-----------------|---------------|-----------------|  
|**fdhost_id**|**int**|篩選背景程式主機的識別碼。|  
|**fdhost_name**|**nvarchar(120)**|篩選背景程式主機的名稱。|  
|**fdhost_process_id**|**int**|篩選背景程式主機的 Windows 處理序識別碼。|  
|**fdhost_type**|**nvarchar(120)**|篩選背景程式主機正在處理的文件類型，為以下其中一項：<br /><br /> 單一執行緒<br /><br /> 多執行緒<br /><br /> 大型文件|  
|**max_thread**|**int**|篩選背景程式主機中的最大執行緒數目。|  
|**batch_count**|**int**|篩選背景程式主機內正在處理的批次數。|  
  
## <a name="permissions"></a>Permissions  

在[!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)]，需要`VIEW SERVER STATE`權限。   
在[!INCLUDE[ssSDS_md](../../includes/sssds-md.md)]，需要`VIEW DATABASE STATE`資料庫的權限。   

## <a name="examples"></a>範例  
 下列範例會傳回篩選背景程式主機的名稱以及其中的最大執行緒數目。 它也會監視目前在篩選背景程式中處理的批次數。 這項資訊可用來診斷效能。  
  
```  
SELECT fdhost_name, batch_count, max_thread FROM sys.dm_fts_fdhosts;  
GO  
```  
  
## <a name="see-also"></a>另請參閱  
 [全文檢索搜尋和語意搜尋動態管理檢視與函數&#40;Transact SQL&#41;](../../relational-databases/system-dynamic-management-views/full-text-and-semantic-search-dynamic-management-views-functions.md)   
 [全文檢索搜尋](../../relational-databases/search/full-text-search.md)  
  
  
