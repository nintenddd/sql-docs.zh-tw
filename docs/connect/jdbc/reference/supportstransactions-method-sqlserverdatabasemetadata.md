---
title: supportsTransactions 方法 (SQLServerDatabaseMetaData) |Microsoft 文件
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
apiname:
- SQLServerDatabaseMetaData.supportsTransactions
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 57d28ee5-c2f6-4740-b42d-cead1aade809
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 09fbf05d24d5213b93ddc79fd48dd0e87d27f933
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2018
---
# <a name="supportstransactions-method-sqlserverdatabasemetadata"></a>supportsTransactions 方法 (SQLServerDatabaseMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  擷取值，此值指出這個資料庫是否支援交易。  
  
## <a name="syntax"></a>語法  
  
```  
  
public boolean supportsTransactions()  
```  
  
## <a name="return-value"></a>傳回值  
 **true**受支援。 否則為 **false**。  
  
## <a name="exceptions"></a>例外狀況  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>備註  
 這個 supportsTransactions 方法是由 java.sql.DatabaseMetaData 介面中 supportsTransactions 方法指定。  
  
## <a name="see-also"></a>另請參閱  
 [SQLServerDatabaseMetaData 方法](../../../connect/jdbc/reference/sqlserverdatabasemetadata-methods.md)   
 [SQLServerDatabaseMetaData 成員](../../../connect/jdbc/reference/sqlserverdatabasemetadata-members.md)   
 [SQLServerDatabaseMetaData 類別](../../../connect/jdbc/reference/sqlserverdatabasemetadata-class.md)  
  
  
