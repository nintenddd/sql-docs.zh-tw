---
title: setAsciiStream 方法 （int，java.io.InputStream，long） |Microsoft 文件
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 9dfa7781-d72f-407a-a8d4-1c78c9446d09
caps.latest.revision: 22
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 48ae2a487526b990086698969981c972e354f646
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2018
---
# <a name="setasciistream-method-int-javaioinputstream-long"></a>setAsciiStream 方法 (int, java.io.InputStream, long)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  將指定的參數編號設定為指定的 java.io.InputStream 物件與指定的位元組數目。  
  
## <a name="syntax"></a>語法  
  
```  
  
public final void setAsciiStream(int parameterIndex,  
                                 java.io.InputStream x,  
                                    long length)  
```  
  
#### <a name="parameters"></a>參數  
 *parameterIndex*  
  
 **Int** ，指出參數編號。  
  
 *x*  
  
 Java.io.InputStream 物件。  
  
 *長度*  
  
 A**長**，指出位元組數目。  
  
## <a name="exceptions"></a>例外狀況  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>備註  
 這個 setAsciiStream 方法 setAsciiStream 方法 java.sql.PreparedStatement 介面中所指定。  
  
 如果資料流的長度就是不同於以指定的內容*長度*參數，JDBC 驅動程式會擲回例外狀況時更新或插入資料列。  
  
 如果資料流長度未知，*長度*參數可能會設定為-1，指出驅動程式應該接受資料流，無論其長度為何。 針對 sqljdbc4.jar，我們建議您使用 JDBC 4.0 方法[setAsciiStream 方法&#40;int，java.io.InputStream&#41; ](../../../connect/jdbc/reference/setasciistream-method-int-java-io-inputstream.md)應用程式要從長度未知的資料流的資料行的更新。  
  
## <a name="see-also"></a>另請參閱  
 [setAsciiStream 方法&#40;SQLServerPreparedStatement&#41;](../../../connect/jdbc/reference/setasciistream-method-sqlserverpreparedstatement.md)   
 [SQLServerPreparedStatement 成員](../../../connect/jdbc/reference/sqlserverpreparedstatement-members.md)  
  
  
