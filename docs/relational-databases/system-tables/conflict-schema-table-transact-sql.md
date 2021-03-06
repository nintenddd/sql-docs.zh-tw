---
title: conflict_&lt;結構描述&gt;_&lt;資料表&gt;(TRANSACT-SQL) |Microsoft 文件
ms.custom: ''
ms.date: 01/15/2016
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-tables
ms.reviewer: ''
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- conflict_
- conflict_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- conflict_<schema>_<table>
ms.assetid: 15ddd536-db03-454e-b9b5-36efe1f756d7
caps.latest.revision: 12
author: edmacauley
ms.author: edmaca
manager: craigg
ms.openlocfilehash: 64d89c82ffa149c55c8834ca46a11607f33459c8
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2018
---
# <a name="conflictltschemagtlttablegt-transact-sql"></a>conflict_&lt;結構描述&gt;_&lt;資料表&gt;(TRANSACT-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Conflict_\<結構描述 > _\<資料表 > 資料表包含衝突資料列，在端對端複寫相關資訊。 發行集中每個複寫的資料表都有衝突資料表，衝突資料表的名稱是附加在結構描述和發行項名稱後面。 發行項特定的衝突資料表會存在於每一個發行集資料庫內。  
  
 如果是點對點複寫，則在預設情況下，當散發代理程式偵測到衝突時，就會發生失敗。 衝突錯誤會記錄到錯誤記錄檔中，但是不會將任何衝突資料記錄到衝突資料表中；因此，此資料表無法供人檢視。 如果允許散發代理程式繼續進行，會將衝突記錄在本機中偵測到衝突的每一個節點上。 如需詳細資訊，請參閱＜ [Conflict Detection in Peer-to-Peer Replication](../../relational-databases/replication/transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md)＞中的「處理衝突」。  
  
|資料行名稱|資料類型|Description|  
|-----------------|---------------|-----------------|  
|__$originator_id|**int**|引發衝突變更之節點的識別碼。 如需識別碼的清單，請執行[sp_help_peerconflictdetection](../../relational-databases/system-stored-procedures/sp-help-peerconflictdetection-transact-sql.md)。|  
|__$origin_datasource|**int**|引發衝突變更的節點。|  
|__$tranid|**nvarchar (40)**|衝突變更的記錄序號 (LSN) (當套用到 __$origin_datasource 時)。|  
|__$conflict_type|**int**|衝突的類型，它可以是下列其中一個值：<br /><br /> 1：更新失敗，因為另一項更新變更了本機資料列，或是已經刪除再重新插入此資料列。<br /><br /> 2：更新失敗，因為本機資料列已被刪除。<br /><br /> 3：刪除失敗，因為另一項更新變更了本機資料列，或是已經刪除再重新插入此資料列。<br /><br /> 4：刪除失敗，因為本機資料列已被刪除。<br /><br /> 5：插入失敗，因為本機資料列已經插入，或是已經插入後再更新。|  
|__$is_winner|**bit**|指出此資料表中的資料列是否為衝突的贏家，這表示它已套用到本機節點。|  
|__$pre_version|**varbinary (32)**|引發衝突變更的資料庫版本。|  
|__$reason_code|**int**|此衝突的解決程式碼。 可以是下列其中一個值：<br /><br /> 0<br /><br /> 1<br /><br /> 2<br /><br /> <br /><br /> 如需詳細資訊，請參閱 **__ reason_text**。|  
|__$reason_text|**nvarchar (720)**|此衝突的解決方法。 可以是下列其中一個值：<br /><br /> 已解決 (1)<br /><br /> 未解決 (2)<br /><br /> 未知 (0)|  
|__$update_bitmap|**varbinary (** *n* **)**。 大小會視內容而有所不同。|指出當發生更新與更新之間的衝突時，已更新哪一個資料行的點陣圖。|  
|__$inserted_date|**datetime**|衝突資料列插入此資料表的日期和時間。|  
|__$row_id|**timestamp**|與產生衝突之資料列有關聯的資料列版本。|  
|__$change_id|**binary (8)**|如果是本機資料列，這個值會等於與此本機資料列衝突之傳入資料列的 __$row_id。 如果是傳入資料列，這個值會是 NULL。|  
|\<基底資料表資料行名稱 >|\<基底資料表資料行類型 >|衝突資料表針對基底資料表中的每個資料行各包含一個資料行。|  
  
## <a name="see-also"></a>另請參閱  
 [複寫資料表&#40;Transact SQL&#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [複寫檢視 &#40;Transact-SQL&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
