---
title: 資料表名稱 |Microsoft 文件
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
- SQL grammar [ODBC], table names
- table names [ODBC]
ms.assetid: f7a5cb0a-3be7-4f46-82f9-64ffdbceaa9b
caps.latest.revision: 7
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 53942dbfedbc630962fe49675620c47ad7e32b2a
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2018
---
# <a name="table-names"></a>資料表名稱
當 dBASE、 Microsoft Excel、 Paradox，或使用驅動程式的文字、 資料表名稱中所發生的 SELECT 或 DELETE FROM 子句之後 INTO 子句中的插入，並更新之後，CREATE TABLE 和 DROP TABLE 可以包含有效的路徑、 主要的名稱，與檔案副檔名.  
  
 使用 SQL 陳述式中的其他位置的資料表名稱不支援的路徑或延伸模組使用，但接受只有主要名稱 (例如，EMP 從 C:\ABC\EMP)。  
  
 可以使用相互關聯名稱 （別名）。 例如：  
  
```  
SELECT *    
FROM C:\ABC\EMP T1    
WHERE T1.COL1 = 'aaa'  
```
