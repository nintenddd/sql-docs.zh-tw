---
title: MarshalOptions 屬性 (ADO) |Microsoft 文件
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
apitype: COM
f1_keywords:
- Recordset15::MarshalOptions
helpviewer_keywords:
- MarshalOptions property [ADO]
ms.assetid: 390c8abf-133e-40da-8b99-8f748a983e4f
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: ca3cb11f425b94145b89638012844d64265bd6b3
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2018
---
# <a name="marshaloptions-property-ado"></a>MarshalOptions 屬性 (ADO)
指出哪一筆記錄的[資料錄集](../../../ado/reference/ado-api/recordset-object-ado.md)是要封送處理至伺服器。  
  
## <a name="settings-and-return-values"></a>設定和傳回值  
 設定或傳回[MarshalOptionsEnum](../../../ado/reference/ado-api/marshaloptionsenum.md)值。 預設值是**adMarshalAll**。  
  
## <a name="remarks"></a>備註  
 使用用戶端時[資料錄集](../../../ado/reference/ado-api/recordset-object-ado.md)，已修改用戶端的記錄寫回至中介層或透過呼叫封送處理封裝和傳送介面方法的程序的技術的網頁伺服器跨執行緒或處理序界限參數。 設定**MarshalOptions**屬性已修改的遠端資料封送處理回中介層或 Web 伺服器更新時，可以改善效能。  
  
> [!NOTE]
>  **遠端資料服務使用量**這個屬性只適用於用戶端**資料錄集**。  
  
## <a name="applies-to"></a>適用於  
 [Recordset 物件 (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)  
  
## <a name="see-also"></a>另請參閱  
 [MarshalOptions 屬性範例 (VB)](../../../ado/reference/ado-api/marshaloptions-property-example-vb.md)   
 [MarshalOptions 屬性範例 (VC++)](../../../ado/reference/ado-api/marshaloptions-property-example-vc.md)   
