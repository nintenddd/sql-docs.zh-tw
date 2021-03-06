---
title: sys.parameters (TRANSACT-SQL) |Microsoft 文件
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.component: system-catalog-views
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sys.parameters_TSQL
- sys.parameters
- parameters
- parameters_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.parameters catalog view
- table-valued parameters,sys.parameters
ms.assetid: 24e2764b-c8e5-4322-97a4-7407d8b8a92b
caps.latest.revision: 49
author: edmacauley
ms.author: edmaca
manager: craigg
monikerRange: '>= aps-pdw-2016 || = azuresqldb-current || = azure-sqldw-latest || >= sql-server-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: 2a86fe34d867fcda8e416065e73e780f2cbee851
ms.sourcegitcommit: f1caaa156db2b16e817e0a3884394e7b30fb642f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="sysparameters-transact-sql"></a>sys.parameters (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  針對接受參數之物件的每個參數，各包含一個資料列。 如果物件是純量函數，也會有一個描述傳回值的單一資料列。 該資料列都會有**parameter_id**值為 0。  
  
|資料行名稱|資料類型|Description|  
|-----------------|---------------|-----------------|  
|**object_id**|**int**|這個參數所屬物件的識別碼。|  
|**name**|**sysname**|參數的名稱。 在物件中，這是唯一的。<br /><br /> 如果物件是純量函數，參數名稱就是代表傳回值之資料列中的空字串。|  
|**parameter_id**|**int**|參數的識別碼。 在物件中，這是唯一的。<br /><br /> 如果物件是純量函數， **parameter_id** = 0 就代表傳回的值。|  
|**system_type_id**|**tinyint**|參數系統類型的識別碼。|  
|**user_type_id**|**int**|使用者所定義的參數類型識別碼。<br /><br /> 若要傳回的型別名稱，加入[sys.types](../../relational-databases/system-catalog-views/sys-types-transact-sql.md)目錄檢視這個資料行。|  
|**max_length**|**smallint**|參數的最大長度 (以位元組為單位)。<br /><br /> 值 =-1，當資料行資料類型是**varchar （max)**， **nvarchar （max)**， **varbinary （max)**，或**xml**。|  
|**有效位數**|**tinyint**|如果是以數值為基礎，便是參數的有效位數；否則，便是 0。|  
|**scale**|**tinyint**|如果是以數值為基礎，便是參數的小數位數；否則，便是 0。|  
|**is_output**|**bit**|1 = 參數是 OUTPUT 或 RETURN，否則就是 0。|  
|**is_cursor_ref**|**bit**|1 = 參數是一個資料指標參考參數。|  
|**has_default_value**|**bit**|1 = 參數有預設值。<br /><br /> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 只會在此目錄檢視中保留 CLR 物件的預設值；因此，對於 [!INCLUDE[tsql](../../includes/tsql-md.md)] 物件，此資料行的值為 0。 若要檢視中的參數的預設值[!INCLUDE[tsql](../../includes/tsql-md.md)]物件，請查詢**定義**資料行[sys.sql_modules](../../relational-databases/system-catalog-views/sys-sql-modules-transact-sql.md)目錄檢視，或使用[OBJECT_DEFINITION](../../t-sql/functions/object-definition-transact-sql.md)系統函數。|  
|**is_xml_document**|**bit**|1 = 內容是完整的 XML 文件集。<br /><br /> 0 = 內容是文件片段，或者資料行的資料類型不是**xml**。|  
|**default_value**|**sql_variant**|如果**has_default_value**為 1，此資料行值的預設參數的值，否則為 NULL。|  
|**xml_collection_id**|**int**|非零參數的資料類型是否**xml**且 XML 具備類型。 這個值是包含參數的驗證 XML 結構描述命名空間之集合的識別碼。<br /><br /> 0 = 沒有 XML 結構描述集合。|  
|**is_readonly**|**bit**|1 = 參數為 READONLY，否則就是 0。|  
|**is_nullable**|**bit**|1 = 參數不可為 Null  (預設值)。<br /><br /> 0 = 參數不可為 Null，適用於原生編譯預存程序更有效率的執行。|  
  
## <a name="permissions"></a>Permissions  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] 如需相關資訊，請參閱 [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md)。  
  
## <a name="see-also"></a>另請參閱  
 [物件目錄檢視 &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/object-catalog-views-transact-sql.md)   
 [目錄檢視 &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [查詢 SQL Server 系統目錄 FAQ](../../relational-databases/system-catalog-views/querying-the-sql-server-system-catalog-faq.md)   
 [sys.all_parameters &#40;Transact SQL&#41;](../../relational-databases/system-catalog-views/sys-all-parameters-transact-sql.md)   
 [sys.system_parameters &#40;Transact SQL&#41;](../../relational-databases/system-catalog-views/sys-system-parameters-transact-sql.md)  
  
  
