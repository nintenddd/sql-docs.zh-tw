---
title: 使用預存程序與更新計數 |Microsoft 文件
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 64cf4877-5995-4bfc-8865-b7618a5c8d01
caps.latest.revision: 26
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: d858b255d5bdd6ce74509d36f4d0497220350694
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2018
---
# <a name="using-a-stored-procedure-with-an-update-count"></a>使用預存程序與更新計數
[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

  若要修改的資料[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]使用預存程序，資料庫[!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)]提供[SQLServerCallableStatement](../../connect/jdbc/reference/sqlservercallablestatement-class.md)類別。 藉由使用 SQLServerCallableStatement 類別，您可以呼叫預存程序修改包含在資料庫中的資料，並傳回受影響的資料列數目的計數也稱為更新計數。  
  
 您已經設定預存程序的呼叫使用 SQLServerCallableStatement 類別之後，您可以使用，然後呼叫預存程序[執行](../../connect/jdbc/reference/execute-method-sqlserverstatement.md)或[executeUpdate](../../connect/jdbc/reference/executeupdate-method-sqlserverstatement.md)方法。 ExecuteUpdate 方法會傳回**int**並不會包含受到預存程序，但是 execute 方法中的資料列數目的值。 如果您使用 execute 方法，而且想要取得受影響的資料列數目的計數，您可以呼叫[getUpdateCount](../../connect/jdbc/reference/getupdatecount-method-sqlserverstatement.md)方法之後執行預存程序。  
  
> [!NOTE]  
>  如果想要 JDBC 驅動程式傳回所有更新計數 (包括任何可能已引發之觸發程序所傳回的更新計數)，請將 lastUpdateCount 連接字串屬性設為 "false"。 如需 lastUpdateCount 屬性的詳細資訊，請參閱[設定連接屬性](../../connect/jdbc/setting-the-connection-properties.md)。  
  
 例如，建立下列資料表和預存程序，並同時插入範例資料中的[!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal_md.md)]範例資料庫：  
  
```  
CREATE TABLE TestTable   
   (Col1 int IDENTITY,   
    Col2 varchar(50),   
    Col3 int);  
  
CREATE PROCEDURE UpdateTestTable  
   @Col2 varchar(50),  
   @Col3 int  
AS  
BEGIN  
   UPDATE TestTable  
   SET Col2 = @Col2, Col3 = @Col3  
END;  
INSERT INTO dbo.TestTable (Col2, Col3) VALUES ('b', 10);  
```  
  
 在下列範例中，開啟連接[!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal_md.md)]範例資料庫會傳遞至函式、 execute 方法用於呼叫 UpdateTestTable 預存程序，然後 getUpdateCount 方法用來傳回的資料列的計數受影響預存程序。  
  
 [!code[JDBC#UsingSprocWithUpdateCount1](../../connect/jdbc/codesnippet/Java/using-a-stored-procedure_0_1.java)]  
  
## <a name="see-also"></a>另請參閱  
 [搭配使用陳述式與預存程序](../../connect/jdbc/using-statements-with-stored-procedures.md)  
  
  
