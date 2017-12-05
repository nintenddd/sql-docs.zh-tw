---
title: "sys.dm_os_nodes (TRANSACT-SQL) |Microsoft 文件"
ms.custom: 
ms.date: 07/19/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: dmv's
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sys.dm_os_nodes
- dm_os_nodes_TSQL
- dm_os_nodes
- sys.dm_os_nodes_TSQL
dev_langs: TSQL
helpviewer_keywords: sys.dm_os_nodes dynamic management view
ms.assetid: c768b67c-82a4-47f5-850b-0ea282358d50
caps.latest.revision: "33"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 5cf36f7156f9297231fc232e8fecafee5e77427c
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/17/2017
---
# <a name="sysdmosnodes-transact-sql"></a>sys.dm_os_nodes (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  名為 SQLOS 的內部元件會建立模擬硬體處理器位置的節點結構。 您可以使用軟體 NUMA 來建立自訂節點配置，藉以變更這些結構。  
  
 下表提供有關這些節點的資訊。  
  
> **注意：**呼叫從這個 DMV[!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)]或[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]，使用名稱**sys.dm_pdw_nodes_os_nodes**。  
  
|資料行名稱|資料類型|Description|  
|-----------------|---------------|-----------------|  
|node_id|**smallint**|節點的識別碼。|  
|node_state_desc|**nvarchar(256)**|節點狀態的描述。 系統會先顯示互斥的值，然後再顯示可結合的值。 例如：<br /><br /> Online, Thread Resources Low, Lazy Preemptive<br /><br /> 有四個互斥的 node_state_desc 值。 列在底下與它們的描述。<br /><br /> 節點已上線的線上：<br /><br /> 離線： 節點已離線<br /><br /> 閒置： 節點沒有任何暫止的工作要求，而且已進入閒置狀態。<br /><br /> IDLE_READY： 節點沒有任何暫止的工作要求，並已準備好進入閒置狀態。<br /><br /> 有五個可結合的 node_state_desc 值，其描述與下面所列。<br /><br /> DAC： 此節點被保留給專用管理連接。<br /><br /> THREAD_RESOURCES_LOW： 新的執行緒上建立這個節點由於記憶體不足的狀況。<br /><br /> HOT ADDED： 表示已加入節點來回應 hot add CPU 事件。|  
|memory_object_address|**varbinary （8)**|與這個節點相關聯之記憶體物件的位址。 與 sys.dm_os_memory_objects.memory_object_address 的一對一關聯。|  
|memory_clerk_address|**varbinary （8)**|與這個節點相關聯之記憶體 Clerk 的位址。 與 sys.dm_os_memory_clerks.memory_clerk_address 的一對一關聯。|  
|io_completion_worker_address|**varbinary （8)**|指派給這個節點之 IO 完成的工作者位址。 與 sys.dm_os_workers.worker_address 的一對一關聯。|  
|memory_node_id|**smallint**|這個節點所屬之記憶體節點的識別碼。 與 sys.dm_os_memory_nodes.memory_node_id 的一對多關聯。|  
|cpu_affinity_mask|**bigint**|識別與這個節點相關之 CPU 的點陣圖。|  
|online_scheduler_count|**smallint**|這個節點所管理之線上排程器的數目。|  
|idle_scheduler_count|**smallint**|沒有使用中工作者之線上排程器的數目。|  
|active_worker_count|**int**|在這個節點所管理之所有排程器上使用中的工作者數目。|  
|avg_load_balance|**int**|這個節點上每個排程器的平均工作數目。|  
|timer_task_affinity_mask|**bigint**|識別可指派計時器工作給本身之排程器的點陣圖。|  
|permanent_task_affinity_mask|**bigint**|識別可指派永久工作給本身之排程器的點陣圖。|  
|resource_monitor_state|**bit**|每個節點都具有一個指派給本身的資源監視器。 資源監視器可能是執行中或閒置。 值 1 是表示執行中，而值 0 則表示閒置。|  
|online_scheduler_mask|**bigint**|識別這個節點的處理序相似性遮罩。|  
|processor_group|**smallint**|識別這個節點的處理器群組。|  
|cpu_count |**int** |此節點可用的 Cpu 數目。 |
|pdw_node_id|**int**|此發行版本上的節點識別碼。<br /><br /> **適用於**: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)]，[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]|  
  
## <a name="permissions"></a>Permissions  
在[!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)]，需要`VIEW SERVER STATE`權限。   
在[!INCLUDE[ssSDS_md](../../includes/sssds-md.md)]Premium 層需要`VIEW DATABASE STATE`資料庫的權限。 在[!INCLUDE[ssSDS_md](../../includes/sssds-md.md)]標準和基本層，需要**伺服器管理員**或**Azure Active Directory 系統管理員**帳戶。  
  
## <a name="see-also"></a>請參閱＜  
  
 [SQL Server 作業系統相關的動態管理檢視 &#40;TRANSACT-SQL &#41;](../../relational-databases/system-dynamic-management-views/sql-server-operating-system-related-dynamic-management-views-transact-sql.md)   
 [軟體 NUMA &#40;SQL Server&#41;](../../database-engine/configure-windows/soft-numa-sql-server.md)  
  
  

