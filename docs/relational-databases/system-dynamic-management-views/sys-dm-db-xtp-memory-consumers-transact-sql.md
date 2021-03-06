---
title: sys.dm_db_xtp_memory_consumers (TRANSACT-SQL) |Microsoft 文件
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sys.dm_db_xtp_memory_consumers
- dm_db_xtp_memory_consumers
- dm_db_xtp_memory_consumers_TSQL
- sys.dm_db_xtp_memory_consumers_stats_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_db_xtp_memory_consumers dynamic management view
ms.assetid: f7ab2eaf-e627-464d-91fe-0e170b3f37bc
caps.latest.revision: 24
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: = azure-sqldw-latest || >= sql-server-2016 || = sqlallproducts-allversions
ms.openlocfilehash: 05632eebe6bd329815016da40db4705be0b935ed
ms.sourcegitcommit: 7019ac41524bdf783ea2c129c17b54581951b515
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/23/2018
---
# <a name="sysdmdbxtpmemoryconsumers-transact-sql"></a>sys.dm_db_xtp_memory_consumers (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2014-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2014-asdb-xxxx-xxx-md.md)]

  報告在 [!INCLUDE[hek_2](../../includes/hek-2-md.md)] 資料庫引擎中的資料庫層級記憶體取用者。 這個檢視會針對資料庫引擎所使用的每個記憶體取用者，各傳回一個資料列。 您可以使用這個 DMV，查看記憶體分散到不同的內部物件的方式。  
  
 如需詳細資訊，請參閱[記憶體內部 OLTP &#40;記憶體內部最佳化&#41;](../../relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)。  
  
|資料行名稱|資料類型|Description|  
|-----------------|---------------|-----------------|  
|memory_consumer_id|**bigint**|記憶體取用者的識別碼 (內部)。|  
|memory_consumer_type|**int**|記憶體取用者的類型：<br /><br /> 0=彙總。 (彙總兩個以上取用者的記憶體使用量。 它不應該顯示)。<br /><br /> 2=VARHEAP (追蹤可變長度堆積的記憶體耗用量)。<br /><br /> 3=HASH (追蹤索引的記憶體耗用量)。<br /><br /> 5=資料庫分頁集區 (追蹤用於執行階段作業之資料庫分頁集區的記憶體耗用量。 例如，資料表變數和一些可序列化的掃描。 每個資料庫只有一個這種類型的記憶體取用者)。|  
|memory_consumer_type_desc|**nvarchar(64)**|記憶體取用者的類型：VARHEAP、HASH 或 PGPOOL。<br /><br /> 0 – (它不應該顯示)。<br /><br /> 2 - VARHEAP<br /><br /> 3 - HASH<br /><br /> 5 - PGPOOL|  
|memory_consumer_desc|**nvarchar(64)**|記憶體取用者執行個體的描述：<br /><br /> VARHEAP: <br />資料庫堆積。 用來配置資料庫的使用者資料 (資料列)。<br />資料庫系統堆積。 用來配置將包含在記憶體傾印中而且不包含使用者資料的資料庫資料。<br />範圍索引堆積。 範圍索引為了配置 BW 頁面所使用的私密堆積。<br /><br /> 雜湊： 沒有描述，因為 object_id 表示資料表和 index_id 雜湊索引本身。<br /><br /> PGPOOL： 針對資料庫都有一個分頁集區資料庫 64k 分頁集區。|  
|object_id|**bigint**|配置的記憶體所歸屬的物件識別碼。 系統物件的負值。|  
|xtp_object_id|**bigint**|記憶體最佳化的資料表物件識別碼。|  
|index_id|**int**|取用者的索引識別碼 (如果有的話)。 基底資料表的 NULL。|  
|allocated_bytes|**bigint**|保留給此取用者的位元組數。|  
|used_bytes|**bigint**|這個取用者使用的位元組。 只適用於 varheap。|  
|allocation_count|**int**|配置的數目。|  
|partition_count|**int**|僅供內部使用。|  
|sizeclass_count|**int**|僅供內部使用。|  
|min_sizeclass|**int**|僅供內部使用。|  
|max_sizeclass|**int**|僅供內部使用。|  
|memory_consumer_address|**varbinary**|取用者的內部位址。 僅供內部使用。|  
|xtp_object_id|**bigint**|記憶體中 OLTP 物件識別碼對應至記憶體最佳化的資料表。|  
  
## <a name="remarks"></a>備註  
 在輸出中，資料庫層級的配置器會參考使用者資料表、索引及系統資料表。 object_id = NULL 的 VARHEAP 會參考配置給具有可變長度資料行之資料表的記憶體。  
  
## <a name="permissions"></a>Permissions  
 如果您具有目前資料庫的 VIEW DATABASE STATE 權限，則會傳回所有資料列。 否則，就會傳回空白資料列集。  
  
 如果您沒有 VIEW DATABASE 權限，則會傳回您具有 SELECT 權限之資料表資料列的所有資料行。  
  
 只針對具有 VIEW DATABASE STATE 權限的使用者傳回系統資料表。  
  
## <a name="general-remarks"></a>一般備註  
 當記憶體最佳化資料表具有資料行存放區索引時，系統會使用會耗用一些記憶體，某些內部資料表來追蹤資料行存放區索引的資料。 如需這些內部資料表和查詢範例顯示其記憶體耗用量的詳細資訊，請參閱[sys.memory_optimized_tables_internal_attributes (TRANSACT-SQL)](../../relational-databases/system-catalog-views/sys-memory-optimized-tables-internal-attributes-transact-sql.md)。
 
  
## <a name="examples"></a>範例  
  
```  
-- memory consumers (database level)  
SELECT OBJECT_NAME(object_id), *   
FROM sys.dm_db_xtp_memory_consumers;  
```  
  
## <a name="user-scenario"></a>使用者案例  
  
```  
-- memory consumers (database level)  
  
select  convert(char(10), object_name(object_id)) as Name,   
convert(char(10),memory_consumer_type_desc ) as memory_consumer_type_desc, object_id,index_id, allocated_bytes,  used_bytes   
from sys.dm_db_xtp_memory_consumers  
```  
  
 下面是資料行子集的輸出。 資料庫層級的配置器會參考使用者資料表、索引及系統資料表。 具有 object_id = NULL 的 VARHEAP (最後一列) 會參考配置給資料表之資料列的記憶體 (在此範例中，它是 t1)。 轉換為 MB 時，已配置的位元組為 1340MB。  
  
```  
Name       memory_consumer_type_desc object_id   index_id    allocated_bytes      used_bytes  
---------- ------------------------- ----------- ----------- -------------------- --------------------  
t3         HASH                      629577281   2           8388608              8388608  
t2         HASH                      597577167   2           8388608              8388608  
t1         HASH                      565577053   2           1048576              1048576  
NULL       HASH                      -6          1           2048                 2048  
NULL       VARHEAP                   -6          NULL        0                    0  
NULL       HASH                      -5          3           8192                 8192  
NULL       HASH                      -5          2           8192                 8192  
NULL       HASH                      -5          1           8192                 8192  
NULL       HASH                      -4          1           2048                 2048  
NULL       VARHEAP                   -4          NULL        0                    0  
NULL       HASH                      -3          1           2048                 2048  
NULL       HASH                      -2          2           8192                 8192  
NULL       HASH                      -2          1           8192                 8192  
NULL       VARHEAP                   -2          NULL        196608               26496  
NULL       HASH                      0           1           2048                 2048  
NULL       PGPOOL                    0           NULL        0                    0  
NULL       VARHEAP                   NULL        NULL        1405943808           1231220560  
  
(17 row(s) affected)  
```  
  
 配置和使用這個 DMV 中的總記憶體是相同的物件層級[sys.dm_db_xtp_table_memory_stats &#40;TRANSACT-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-db-xtp-table-memory-stats-transact-sql.md)。  
  
```  
select  sum(allocated_bytes)/(1024*1024) as total_allocated_MB,   
        sum(used_bytes)/(1024*1024) as total_used_MB  
from sys.dm_db_xtp_memory_consumers  
  
total_allocated_MB   total_used_MB  
-------------------- --------------------  
1358                 1191  
```  
  
## <a name="see-also"></a>另請參閱  
 [記憶體最佳化的資料表動態管理檢視&#40;Transact SQL&#41;](../../relational-databases/system-dynamic-management-views/memory-optimized-table-dynamic-management-views-transact-sql.md)  
  
  
