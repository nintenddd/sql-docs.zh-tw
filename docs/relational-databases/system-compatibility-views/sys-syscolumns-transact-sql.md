---
title: sys.syscolumns (TRANSACT-SQL) |Microsoft 文件
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-enginel, sql-data-warehouse, pdw
ms.component: system-compatibility-views
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sys.syscolumns
- sys.syscolumns_TSQL
- syscolumns_TSQL
- syscolumns
dev_langs:
- TSQL
helpviewer_keywords:
- syscolumns system table
- sys.syscolumns compatibility view
ms.assetid: 863fd87b-ff33-4ac5-9aa9-df21140681da
caps.latest.revision: 32
author: rothja
ms.author: jroth
manager: craigg
monikerRange: '>= aps-pdw-2016 || = azure-sqldw-latest || >= sql-server-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: ab6fb39894c7cbe10be6d00d5fc74e782ca5650e
ms.sourcegitcommit: f1caaa156db2b16e817e0a3884394e7b30fb642f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="syssyscolumns-transact-sql"></a>sys.syscolumns (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-ss2008-xxxx-asdw-pdw-md.md)]

  針對每份資料表和檢視中的每個資料行，各傳回一個資料列；針對資料庫內預存程序中的每個參數，各傳回一個資料列。  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssnoteCompView](../../includes/ssnotecompview-md.md)]  
  
|資料行名稱|資料類型|Description|  
|-----------------|---------------|-----------------|  
|**name**|**sysname**|資料行或程序參數的名稱。|  
|**id**|**int**|這個資料行所屬資料表的物件識別碼，或這個參數相關聯預存程序的識別碼。|  
|**xtype**|**tinyint**|從實體儲存體類型**sys.types**。|  
|**typestat**|**tinyint**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**xusertype**|**smallint**|擴充使用者自訂資料類型的識別碼。 如果資料類型的數目超過 32,767，則會造成溢位或傳回 NULL。|  
|**長度**|**smallint**|從最大實體儲存體長度**sys**。**型別**。|  
|**xprec**|**tinyint**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**xscale**|**tinyint**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**colid**|**smallint**|資料行或參數識別碼。|  
|**xoffset**|**smallint**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**bitpos**|**tinyint**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**保留**|**tinyint**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**colstat**|**smallint**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**cdefault**|**int**|這個資料行之預設值的識別碼。|  
|**網域**|**int**|這個資料行的規則或 CHECK 條件約束的識別碼。|  
|**number**|**smallint**|程序分組時的子程序號碼。<br /><br /> 0 = 非程序項目|  
|**colorder**|**smallint**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**autoval**|**varbinary(8000)**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**offset**|**smallint**|這個資料行出現在其中的資料列內位移。|  
|**collationid**|**int**|資料行定序的識別碼。 以非字元為基礎的資料行是 NULL。|  
|**status**|**tinyint**|用來描述資料行或參數屬性的點陣圖：<br /><br /> 0x08 = 資料行允許 Null 值。<br /><br /> 0x10 = ANSI 填補生效時**varchar**或**varbinary**加入資料行。 保留尾端空白**varchar**保留尾端零**varbinary**資料行。<br /><br /> 0x40 = 參數是 OUTPUT 參數。<br /><br /> 0x80 = 資料行是一個識別欄位。|  
|**type**|**tinyint**|從實體儲存體類型**sys**。**型別**。|  
|**usertype**|**smallint**|從使用者定義資料類型的識別碼**sys.types**。 如果資料類型的數目超過 32,767，則會造成溢位或傳回 NULL。|  
|**printfmt**|**varchar(255)**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**prec**|**smallint**|這個資料行的有效位數層級。<br /><br /> -1 = **xml**或大數值類型。|  
|**scale**|**int**|這個資料行的小數位數。<br /><br /> NULL = 資料類型是非數值。|  
|**iscomputed**|**int**|這是一個旗標，指出這個資料行是否為計算資料行：<br /><br /> 0 = 非計算<br /><br /> 1 = 計算|  
|**isoutparam**|**int**|指出程序參數是否為輸出參數：<br /><br /> 1 = True<br /><br /> 0 = False|  
|**isnullable**|**int**|指出資料行是否允許 Null 值：<br /><br /> 1 = True<br /><br /> 0 = False|  
|**定序**|**sysname**|資料行的定序名稱。 如果不是以字元為基礎的資料行，便是 NULL。|  
  
## <a name="see-also"></a>另請參閱  
 [將系統資料表對應至系統檢視表&#40;Transact SQL&#41;](../../relational-databases/system-tables/mapping-system-tables-to-system-views-transact-sql.md)   
 [相容性檢視 &#40;Transact-SQL&#41;](~/relational-databases/system-compatibility-views/system-compatibility-views-transact-sql.md)  
  
  
