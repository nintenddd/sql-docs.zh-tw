---
title: "IsGeneration (MDX) |Microsoft 文件"
ms.custom: 
ms.date: 03/02/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- ISGENERATION
dev_langs:
- kbMDX
helpviewer_keywords:
- IsGeneration function
ms.assetid: fd11d2e0-d81d-45af-ac45-c98634d05550
caps.latest.revision: 32
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: bdb02d424cb58aab2e8af8695b9751e495ba7175
ms.contentlocale: zh-tw
ms.lasthandoff: 08/02/2017

---
# <a name="isgeneration-mdx"></a>IsGeneration (MDX)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../includes/tsql-appliesto-ss2008-all-md.md)]

  傳回指定的成員是否在指定的生成集內。  
  
## <a name="syntax"></a>語法  
  
```  
  
IsGeneration(Member_Expression, Generation_Number)   
```  
  
## <a name="arguments"></a>引數  
 *Member_Expression*  
 傳回成員的有效多維度運算式 (MDX) 運算式。  
  
 *Generation_Number*  
 指定用來評估指定成員之生成集的有效數值運算式。  
  
## <a name="remarks"></a>備註  
 **IsGeneration**函式會傳回**true**指定的成員是否在指定層代數目。 否則，函數會傳回**false**。 也，如果指定的成員評估為空成員， **IsGeneration**函式會傳回**false**。  
  
 為了生成集索引用途，分葉成員是生成集索引 0。 如果是非分葉成員，首先從指定成員之所有子成員的聯集，取得最高生成集索引，然後在該索引加 1，決定其生成集索引。 因為已決定非分葉成員的生成集索引，所以特定非分葉成員能夠屬於一個以上的生成集。  
  
## <a name="example"></a>範例  
 如果 [Date].[Fiscal].CurrentMember 是第二個生成集的一部分，下列範例會傳回 TRUE：  
  
 `WITH MEMBER MEASURES.ISGENERATIONDEMO AS`  
  
 `IsGeneration([Date].[Fiscal].CURRENTMEMBER, 2)`  
  
 `SELECT {MEASURES.ISGENERATIONDEMO} ON 0,`  
  
 `[Date].[Fiscal].MEMBERS ON 1`  
  
 `FROM [Adventure Works]`  
  
## <a name="see-also"></a>另請參閱  
 [MDX 函數參考 &#40;MDX &#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
