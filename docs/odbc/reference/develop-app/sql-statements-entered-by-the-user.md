---
title: 使用者所輸入 SQL 陳述式 |Microsoft 文件
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- user-entered SQL statements [ODBC]
- SQL statements [ODBC], constructing
- SQL statements [ODBC], entered by user
ms.assetid: 109af162-93ba-425a-8fe5-49c7dc7cc784
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 1be7159d7f56226c94b6cbfa335883b73df15de1
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2018
---
# <a name="sql-statements-entered-by-the-user"></a>使用者所輸入的 SQL 陳述式
也常執行臨機操作分析的應用程式可讓使用者直接輸入 SQL 陳述式。 例如：  
  
```  
SQLCHAR *     Statement, SqlState[6], Msg[SQL_MAX_MESSAGE_LENGTH];  
SQLSMALLINT   i, MsgLen;  
SQLINTEGER    NativeError;  
SQLRETURN     rc1, rc2;  
  
// Prompt user for SQL statement.  
GetSQLStatement(Statement);  
  
// Execute the statement directly. Because it will be executed only once,  
// do not prepare it.  
rc1 = SQLExecDirect(hstmt, Statement, SQL_NTS);  
  
// Process any errors or returned information.  
if ((rc1 == SQL_ERROR) || rc1 == SQL_SUCCESS_WITH_INFO) {  
   i = 1;  
   while ((rc2 = SQLGetDiagRec(SQL_HANDLE_STMT, hstmt, i, SqlState, &NativeError,  
         Msg, sizeof(Msg), &MsgLen)) != SQL_NO_DATA) {  
      DisplayError(SqlState, NativeError, Msg, MsgLen);  
      i++;  
   }  
}  
```  
  
 這種方法可簡化撰寫程式碼應用程式。應用程式必須在使用者建立 SQL 陳述式和資料來源，檢查陳述式的有效性。 因為很難撰寫圖形化使用者介面，可以充分地公開複雜的 SQL，只需要求使用者輸入 SQL 陳述式文字可能更理想的替代方式。 不過，這需要使用者知道，而不是只是 SQL 查詢的資料來源的結構描述。 某些應用程式提供圖形化使用者介面的使用者可以建立基本的 SQL 陳述式，並也提供的使用者可以修改它的文字介面。
