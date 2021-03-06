---
title: ERROR_NUMBER (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/16/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.component: t-sql|functions
ms.reviewer: ''
ms.suite: sql
ms.technology: t-sql
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- ERROR_NUMBER_TSQL
- ERROR_NUMBER
dev_langs:
- TSQL
helpviewer_keywords:
- errors [SQL Server], line number
- messages [SQL Server], numbers
- TRY...CATCH [SQL Server]
- ERROR_NUMBER function
- CATCH block
ms.assetid: 1de85fff-1ca2-4b31-841b-926e571cb150
caps.latest.revision: 50
author: edmacauley
ms.author: edmaca
manager: craigg
monikerRange: '>= aps-pdw-2016 || = azuresqldb-current || = azure-sqldw-latest || >= sql-server-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: 45ad8be1da81b29b446ed18dd0c4688013a18875
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2018
---
# <a name="errornumber-transact-sql"></a>ERROR_NUMBER (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  傳回造成執行 TRY…CATCH 建構的 CATCH 區塊之錯誤的錯誤號碼。  
  
 ![主題連結圖示](../../database-engine/configure-windows/media/topic-link.gif "主題連結圖示") [Transact-SQL 語法慣例](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>語法  
  
```  
ERROR_NUMBER ( )  
```  
  
## <a name="return-types"></a>傳回類型  
 **int**  
  
## <a name="return-value"></a>傳回值  
 當它在 CATCH 區塊中被呼叫時，會傳回造成執行 CATCH 區塊之錯誤訊息的錯誤號碼。  
  
 如果是在 CATCH 區塊範圍之外呼叫，便傳回 NULL。  
  
## <a name="remarks"></a>Remarks  
 可以在 CATCH 區塊範圍內的任何位置呼叫這個函數。  
  
 ERROR_NUMBER 不論執行多少次，也不論是在 CATCH 區塊範圍內的任何位置執行，都會傳回錯誤號碼。 這有別於 @@ERROR，因為其只會在緊接於發生錯誤的陳述式之後的陳述式中，或在 CATCH 區塊的第一個陳述式中傳回錯誤號碼。  
  
 在巢狀 CATCH 區塊中，ERROR_NUMBER 會傳回參考它的 CATCH 區塊範圍特定的錯誤號碼。 例如，外部 TRY...CATCH 建構的 CATCH 區塊可能會有巢狀的 TRY...CATCH 建構。 在巢狀 CATCH 區塊內，ERROR_NUMBER 會從呼叫巢狀 CATCH 區塊的錯誤傳回號碼。 如果 ERROR_NUMBER 是在外部 CATCH 區塊內執行，它會從叫用 CATCH 區塊的錯誤傳回號碼。  
  
## <a name="examples"></a>範例  
  
### <a name="a-using-errornumber-in-a-catch-block"></a>A. 在 CATCH 區塊中使用 ERROR_NUMBER  
 下列程式碼範例會顯示產生除以零之錯誤的 `SELECT` 陳述式。 傳回錯誤的編號。  
  
```  
BEGIN TRY  
    -- Generate a divide-by-zero error.  
    SELECT 1/0;  
END TRY  
BEGIN CATCH  
    SELECT ERROR_NUMBER() AS ErrorNumber;  
END CATCH;  
GO  
```  
  
### <a name="b-using-errornumber-in-a-catch-block-with-other-error-handling-tools"></a>B. 在含有其他錯誤處理工具的 CATCH 區塊中使用 ERROR_NUMBER  
 下列程式碼範例會顯示產生除以零之錯誤的 `SELECT` 陳述式。 錯誤的相關訊息會隨同錯誤號碼而一起傳回。  
  
```  
  
BEGIN TRY  
    -- Generate a divide-by-zero error.  
    SELECT 1/0;  
END TRY  
BEGIN CATCH  
    SELECT  
        ERROR_NUMBER() AS ErrorNumber,  
        ERROR_SEVERITY() AS ErrorSeverity,  
        ERROR_STATE() AS ErrorState,  
        ERROR_PROCEDURE() AS ErrorProcedure,  
        ERROR_LINE() AS ErrorLine,  
        ERROR_MESSAGE() AS ErrorMessage;  
END CATCH;  
GO  
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>範例：[!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] 和 [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
### <a name="c-using-errornumber-in-a-catch-block-with-other-error-handling-tools"></a>C. 在含有其他錯誤處理工具的 CATCH 區塊中使用 ERROR_NUMBER  
 下列程式碼範例會顯示產生除以零之錯誤的 `SELECT` 陳述式。 錯誤的相關訊息會隨同錯誤號碼而一起傳回。  
  
```  
  
BEGIN TRY  
    -- Generate a divide-by-zero error.  
    SELECT 1/0;  
END TRY  
BEGIN CATCH  
    SELECT  
        ERROR_NUMBER() AS ErrorNumber,  
        ERROR_SEVERITY() AS ErrorSeverity,  
        ERROR_STATE() AS ErrorState,  
        ERROR_PROCEDURE() AS ErrorProcedure,  
        ERROR_MESSAGE() AS ErrorMessage;  
END CATCH;  
GO  
```  
  
## <a name="see-also"></a>另請參閱  
 [sys.messages &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/messages-for-errors-catalog-views-sys-messages.md)   
 [TRY...CATCH &#40;Transact-SQL&#41;](../../t-sql/language-elements/try-catch-transact-sql.md)   
 [ERROR_LINE &#40;Transact-SQL&#41;](../../t-sql/functions/error-line-transact-sql.md)   
 [ERROR_MESSAGE &#40;Transact-SQL&#41;](../../t-sql/functions/error-message-transact-sql.md)   
 [ERROR_PROCEDURE &#40;Transact-SQL&#41;](../../t-sql/functions/error-procedure-transact-sql.md)   
 [ERROR_SEVERITY &#40;Transact-SQL&#41;](../../t-sql/functions/error-severity-transact-sql.md)   
 [ERROR_STATE &#40;Transact-SQL&#41;](../../t-sql/functions/error-state-transact-sql.md)   
 [RAISERROR &#40;Transact-SQL&#41;](../../t-sql/language-elements/raiserror-transact-sql.md)   
 [@@ERROR &#40;Transact-SQL&#41;](../../t-sql/functions/error-transact-sql.md)  
  
  

