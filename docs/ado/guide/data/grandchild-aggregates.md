---
title: 身為下下層的彙總 |Microsoft 文件
ms.prod: sql
ms.prod_service: connectivity
ms.component: ado
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- grandchild aggregates [ADO]
- data shaping [ADO], grandchild aggregates
ms.assetid: 4162d35f-2ce1-4218-80a5-b6933348837e
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 79f5d0d06631f6fcdbdcd85c726a03bdc834faeb
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2018
---
# <a name="grandchild-aggregates"></a>身為下下層的彙總
建立圖形命令的子句中的章節資料行可能提供*章別名*（通常是使用 AS 關鍵字）。 您可以識別任何資料行中的形狀任何章**資料錄集**識別包含資料行的子系的完整名稱。 例如，如果父章 chap1，包含子章節，chap2，都具有 amount 資料行時，amt，就限定的名稱會是 chap1.chap2.amt。限定的名稱可用做為引數，其中彙總函式 （SUM、 AVG、 MAX、 MIN、 計數、 STDEV、 或任何）。  
  
## <a name="see-also"></a>另請參閱  
 [資料成形範例](../../../ado/guide/data/data-shaping-example.md)
