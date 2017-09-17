---
title: "CursorLocation 屬性 (ADO) |Microsoft 文件"
ms.prod: sql-non-specified
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
apitype: COM
f1_keywords:
- Connection15::CursorLocation
- Recordset15::CursorLocation
helpviewer_keywords:
- CursorLocation property [ADO]
ms.assetid: 39c8d86e-7ee9-4182-be5e-aad5ce952f84
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 6679a7a8a83f954039587776e5e668bd5ed05365
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="cursorlocation-property-ado"></a>CursorLocation 屬性 (ADO)
指出資料指標服務的位置。  
  
## <a name="settings-and-return-values"></a>設定和傳回值  
 設定或傳回**長**值，可以設定為其中一個[CursorLocationEnum](../../../ado/reference/ado-api/cursorlocationenum.md)值。  
  
## <a name="remarks"></a>備註  
 這個屬性可讓您選擇各種提供者可存取的資料指標程式庫。 通常，您可以選擇使用用戶端資料指標程式庫或位於伺服器上。  
  
 此屬性設定會影響已經設定的屬性之後，才建立連線。 變更**CursorLocation**屬性具有不會影響現有的連接。  
  
 所傳回的資料指標[Execute](../../../ado/reference/ado-api/execute-method-ado-connection.md)方法繼承此設定。 **資料錄集**物件會自動繼承此設定及其相關聯的連接。  
  
 這個屬性是讀/寫上[連接](../../../ado/reference/ado-api/connection-object-ado.md)或已關閉[資料錄集](../../../ado/reference/ado-api/recordset-object-ado.md)，且在開啟唯讀**資料錄集**。  
  
> [!NOTE]
>  **遠端資料服務使用量**使用用戶端時**資料錄集**或**連接**物件**CursorLocation**屬性只可以設定為**adUseClient**。  
  
## <a name="applies-to"></a>適用於  
  
|||  
|-|-|  
|[連接物件 (ADO)](../../../ado/reference/ado-api/connection-object-ado.md)|[資料錄集物件 (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)|  
  
## <a name="see-also"></a>另請參閱  
 [附錄 a： 提供者](../../../ado/guide/appendixes/appendix-a-providers.md)