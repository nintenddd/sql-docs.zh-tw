---
title: 事件類型 |Microsoft 文件
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
- EventComplete event [ADO]
- events [ADO], types
- Will events [ADO]
- complete events [ADO]
- WillEvent event [ADO]
ms.assetid: f3327ea0-635a-43d4-bd78-c1674f62f1a2
caps.latest.revision: 9
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 3d093fbea3d4c4c6410f19b842ba8907aaa2229e
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2018
---
# <a name="types-of-events"></a>事件類型
有兩種事件的基本類型。 「 將事件 」 呼叫作業開始之前，通常包含在其名稱中的 」 將"— 比方說， **WillChangeRecordset**或**WillConnect**。 通常已經完成事件後呼叫的事件其名稱中包含 「 完成 」 — 比方說， **RecordChangeComplete**或**ConnectComplete**。 例外狀況存在 — 例如**InfoMessage** — 但相關聯的作業已完成之後，這些會發生。  
  
## <a name="will-events"></a>將事件  
 在作業開始提供您有機會檢查或修改的作業參數，然後取消作業，或允許它在完成之前，就會呼叫事件處理常式。 這些事件處理常式通常會有的名稱格式 **將*事件 * * *。  
  
## <a name="complete-events"></a>完成事件  
 作業完成之後呼叫的事件處理常式可以通知您的應用程式的作業已經結束。 這類事件處理常式也會將事件處理常式取消暫止的作業時收到通知。 這些事件處理常式通常會有的名稱格式 ***事件 * 完成**。  
  
 將和完成的事件通常用於配對。  
  
## <a name="other-events"></a>其他事件  
 其他事件處理常式，也就是事件的名稱不是表單的**將 * 事件*** 或 ***事件 * 完成**— 在作業完成之後，才會呼叫。 這些事件是**中斷連線**， **EndOfRecordset**，和**InfoMessage**。  
  
## <a name="see-also"></a>另請參閱  
 [ADO 事件處理常式摘要](../../../ado/guide/data/ado-event-handler-summary.md)   
 [ADO 事件具現化語言](../../../ado/guide/data/ado-event-instantiation-by-language.md)   
 [事件參數](../../../ado/guide/data/event-parameters.md)   
 [事件處理常式如何協同運作](../../../ado/guide/data/how-event-handlers-work-together.md)
