---
title: 是 (MDX) |Microsoft 文件
ms.date: 05/30/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 5c36a5f45e34d6d78043f6ce8a3e3fb040ecc9f6
ms.sourcegitcommit: 808d23a654ef03ea16db1aa23edab496b73e5072
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/02/2018
ms.locfileid: "34578590"
---
# <a name="is-mdx"></a>IS (MDX)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  在兩個物件運算式上執行邏輯比較。  
  
## <a name="syntax"></a>語法  
  
```  
  
Expression1 IS ( Expression2 | NULL )  
```  
  
#### <a name="parameters"></a>參數  
 *Expression1*  
 傳回 MDX 物件參考的有效多維度運算式 (MDX) 運算式。  
  
 *Expression2*  
 傳回 MDX 物件參考的有效 MDX 運算式。  
  
## <a name="return-value"></a>傳回值  
 布林值，傳回**true**如果這兩個引數都參考相同的物件; 否則**false**。 如果**NULL**指定關鍵字，則運算子會傳回**true**如果*Expression1*是**null**，否則**false**。  
  
## <a name="remarks"></a>備註  
 **IS**運算子通常用來判定 tuple 及成員是否具有等冪性，這表示它們完全相同。  
  
## <a name="examples"></a>範例  
 下列範例示範如何使用**IS**運算子來檢查軸上的目前成員是否為特定的成員：  
  
 `With`  
  
 `//Returns TRUE if the currentmember is Bikes`  
  
 `Member [Measures].[IsBikes?] AS`  
  
 `[Product].[Category].CurrentMember IS [Product].[Category].&[1]`  
  
 `SELECT`  
  
 `{[Measures].[IsBikes?]} ON 0,`  
  
 `[Product].[Category].[Category].Members ON 1`  
  
 `FROM`  
  
 `[Adventure Works]`  
  
## <a name="see-also"></a>另請參閱  
 [MDX 運算子參考&#40;MDX&#41;](../mdx/mdx-operator-reference-mdx.md)  
  
  
