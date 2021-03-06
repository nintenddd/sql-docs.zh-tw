---
title: MSmerge_conflicts_info (TRANSACT-SQL) |Microsoft 文件
ms.custom: ''
ms.date: 03/16/2017
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
- MSmerge_conflicts_info_TSQL
- MSmerge_conflicts_info
dev_langs:
- TSQL
helpviewer_keywords:
- MSmerge_conflicts_info system table
ms.assetid: 6b76ae96-737a-4000-a6b6-fcc8772c2af4
caps.latest.revision: 19
author: edmacauley
ms.author: edmaca
manager: craigg
ms.openlocfilehash: d5990e8dc08545597e18832e6f6b44bfbfce6514
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2018
---
# <a name="msmergeconflictsinfo-transact-sql"></a>MSmerge_conflicts_info (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  **MSmerge_conflicts_info**資料表會追蹤在同步處理合併式發行集的訂閱時，會發生的衝突。 針對衝突遺失的資料列資料會儲存在[MSmerge_conflict_publication_article](../../relational-databases/system-tables/msmerge-conflict-publication-article-transact-sql.md)發生衝突之發行項的資料表。 這份資料表儲存在發行集資料庫的發行者端，以及訂閱資料庫的訂閱者端。  
  
|資料行名稱|資料類型|Description|  
|-----------------|---------------|-----------------|  
|**tablenick**|**int**|已發行資料表的暱稱。|  
|**rowguid**|**uniqueidentifier**|衝突資料列的識別碼。|  
|**origin_datasource**|**nvarchar(255)**|引發衝突變更的資料庫名稱。|  
|**conflict_type**|**int**|發生衝突的類型，它可以是下列項目之一：<br /><br /> **1** = 更新衝突： 在資料列層級偵測衝突。<br /><br /> **2** = 資料行更新衝突： 在資料行層級偵測到衝突。<br /><br /> **3** = 更新刪除成功衝突： 刪除在衝突中獲勝。<br /><br /> **4** = 更新成功刪除衝突： 衝突失敗且已刪除的 rowguid 會記錄在此資料表。<br /><br /> **5** = 上傳插入失敗： 訂閱者的插入無法套用在發行者端。<br /><br /> **6** = 下載插入失敗： 發行者的插入無法套用在訂閱者。<br /><br /> **7** = 上傳刪除失敗： 訂閱者端的刪除無法上傳到 「 發行者 」。<br /><br /> **8** = 下載刪除失敗： 發行者端的刪除無法下載到訂閱者。<br /><br /> **9** = 上傳更新失敗： 無法在發行者端套用訂閱者端的更新。<br /><br /> **10** = 下載更新失敗： 發行者端的更新無法套用到訂閱者。<br /><br /> **11** = 解決<br /><br /> **12** = 邏輯記錄更新成功刪除： 衝突失敗且已刪除邏輯記錄會記錄在此資料表。<br /><br /> **13** = 邏輯記錄衝突插入更新： 插入邏輯記錄衝突與更新。<br /><br /> **14** = 邏輯記錄刪除成功更新衝突： 衝突失敗且更新邏輯記錄會記錄在此資料表。|  
|**reason_code**|**int**|可為內容相關的錯誤碼。 在更新與更新以及更新與刪除衝突的情況下使用這個資料行的值是相同**conflict_type**。 但是，對於無法變更衝突，原因代碼將為錯誤，以防止「合併代理程式」套用變更。 例如，如果 「 合併代理程式 」 無法套用 「 訂閱者 」 端的插入，因為主索引鍵違規，就會記錄**conflict_type**為 6 （「 下載插入失敗 」） 和**reason_code** 2627，也就是的[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]主索引鍵違規的內部錯誤訊息: 「 違反 %ls 條件約束 ' %.* ls'。 無法在物件中插入重複的索引鍵 ' %。\*ls'。 」|  
|**reason_text**|**nvarchar(720)**|可為內容相關的錯誤描述。|  
|**pubid**|**uniqueidentifier**|發行集的識別碼。|  
|**MSrepl_create_time**|**datetime**|發生衝突的時間。|  
|**origin_datasource_id**|**uniqueidentifier**|引發衝突變更的資料庫識別碼。|  
  
## <a name="see-also"></a>另請參閱  
 [複寫資料表&#40;Transact SQL&#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [複寫檢視 &#40;Transact-SQL&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
