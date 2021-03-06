---
title: KeyNotFound 元素 (ASSL) |Microsoft 文件
ms.date: 5/8/2018
ms.prod: sql
ms.custom: assl
ms.reviewer: owend
ms.technology: analysis-services
ms.topic: reference
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: bfce07b37bd43b18c769212f7647ec311fec4fa3
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2018
---
# <a name="keynotfound-element-assl"></a>KeyNotFound 元素 (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  指定如何[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]遇到參考完整性錯誤時的回應。  
  
## <a name="syntax"></a>語法  
  
```xml  
  
<ErrorConfiguration>  
   ...  
      <KeyNotFound>...</KeyNotFound>  
   ...  
</ErrorConfiguration>  
```  
  
## <a name="element-characteristics"></a>元素特性  
  
|特性|說明|  
|--------------------|-----------------|  
|資料類型和長度|字串 (列舉)|  
|預設值|*ReportAndContinue*|  
|基數|0-1：只能出現一次的選擇性元素。|  
  
## <a name="element-relationships"></a>元素關聯性  
  
|關聯性|元素|  
|------------------|-------------|  
|父元素|[ErrorConfiguration](../../../analysis-services/scripting/objects/errorconfiguration-element-assl.md)|  
|子元素|無|  
  
## <a name="remarks"></a>備註  
 當相依資料表的外部索引鍵值在父資料表中沒有對應的項目時，就會發生參考完整性錯誤。 發生這個錯誤的情況包括：當 [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] 處理某個維度，其中事實資料表參考該維度之維度資料表中不存在的外部索引鍵值時，或者當 [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] 處理某個資料分割時，如果包含在此資料分割中之維度的維度主資料表參考另一個相關聯維度資料表中不存在的索引鍵值  (在具有父子式階層和父屬性之維度的情況中，如果包含在此資料分割中之維度的維度主資料表參考相同維度資料表中不存在的索引鍵值，也可能會發生這個錯誤)。  
  
 這個元素的值限制為下表所列的其中一個字串。  
  
|Value|說明|  
|-----------|-----------------|  
|*IgnoreError*|處理時應該忽略錯誤並繼續。|  
|*ReportAndContinue*|處理時應該報告錯誤並繼續。|  
|*ReportAndStop*|處理時應該報告錯誤並停止。|  
  
 列舉型別對應至允許的值**KeyNotFound**在 「 分析管理物件 (AMO) 物件模型而言， <xref:Microsoft.AnalysisServices.ErrorOption>。  
  
## <a name="see-also"></a>另請參閱  
 [屬性 & #40;ASSL & #41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  
