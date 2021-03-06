---
title: CalculationPassValue (MDX) |Microsoft 文件
ms.date: 05/30/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 88d7d8c52105feb14c982586f9a819977fc81ed0
ms.sourcegitcommit: 808d23a654ef03ea16db1aa23edab496b73e5072
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/02/2018
ms.locfileid: "34577230"
---
# <a name="calculationpassvalue-mdx"></a>CalculationPassValue (MDX)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  針對指定的 Cube 計算行程進行評估之後，傳回多維度運算式 (MDX) 運算式的數值或字串值。  
  
## <a name="syntax"></a>語法  
  
```  
  
      Numeric syntax  
CalculationPassValue(Numeric_Expression,Pass_Value [, ABSOLUTE | RELATIVE [,ALL]])  
String syntax  
CalculationPassValue(String_Expression ,Pass_Value [, ABSOLUTE | RELATIVE [,ALL]])  
```  
  
## <a name="arguments"></a>引數  
 *Numeric_Expression*  
 有效的數值運算式，這通常是傳回數字之資料格座標的多維度運算式 (MDX) 運算式。  
  
 *String_Expression*  
 有效的字串運算式，這通常是傳回數字 (以字串表示) 之資料格座標的有效多維度運算式 (MDX) 運算式。  
  
 *Pass_Value*  
 指定計算行程數目的有效數值運算式。  
  
 ABSOLUTE  
 存取旗標值，它會指定*Pass_Value*參數包含的計算行程的以零為起始的索引。 如果沒有指定存取旗標值，ABSOLUTE 就是預設存取旗標值。  
  
 RELATIVE  
 存取旗標值，它會指定*Pass_Value*參數包含觸發計算的計算行程相對位移。 如果位移解析成小於 0 的計算行程索引，則會使用計算行程 0 而且不會發生錯誤。  
  
 ALL  
 當設定此旗標時，除了儲存引擎載入的值，所有值都是 Null。 沒有設定時，會在不套用任何計算的情況下彙總值。  
  
## <a name="remarks"></a>備註  
 如果提供了數值運算式，此函數會評估指定的計算行程中之指定的 MDX 數值運算式，並且選擇性地存取旗標和存取旗標修飾詞加以修改，來傳回數值。  
  
 如果提供的字串運算式，則函式藉由評估指定的 MDX 字串運算式，指定的計算行程中，傳回字串值，並選擇性地存取旗標和存取旗標修飾詞加以修改 *。*  
  
 使用自動遞迴解析功能[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]，此函式具有不具實用性。  
  
> [!NOTE]  
>  只有系統管理員可以使用**CalculationPassValue** MDX 指令碼內的函式。 如果在不具有系統管理員權限的角色內容中，執行包含此函數的 MDX 指令碼，就會發生錯誤。  
  
## <a name="see-also"></a>另請參閱  
 [CalculationCurrentPass &#40;MDX&#41;](../mdx/calculationcurrentpass-mdx.md)   
 [IIf &#40;MDX&#41;](../mdx/iif-mdx.md)   
 [MDX 函數參考&#40;MDX&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
