---
title: ModelingFlag 元素 (ASSL) |Microsoft 文件
ms.date: 05/03/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 84fb8664ac5069c7a648308fced9d22ffec41a8a
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2018
---
# <a name="modelingflag-element-assl"></a>ModelingFlag 元素 (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  包含採礦結構或採礦模型中某個資料行的模型旗標。  
  
## <a name="syntax"></a>語法  
  
```xml  
  
<ModelingFlags>  
   <ModelingFlag xsi:type="MiningModelingFlag">...</ModelingFlag>  
</ModelingFlags>  
```  
  
## <a name="element-characteristics"></a>元素特性  
  
|特性|說明|  
|--------------------|-----------------|  
|資料類型和長度|[MiningModelingFlag](../../../analysis-services/scripting/data-type/miningmodelingflag-data-type-assl.md)|  
|預設值|無|  
|基數|0-n：出現一次以上的選擇性元素。|  
  
## <a name="element-relationships"></a>元素關聯性  
  
|關聯性|元素|  
|------------------|-------------|  
|父元素|[ModelingFlags](../../../analysis-services/scripting/collections/modelingflags-element-assl.md)|  
|子元素|無|  
  
## <a name="remarks"></a>備註  
 在「分析管理物件」(AMO) 物件模型中緊密相關的元素是 <xref:Microsoft.AnalysisServices.MiningModelingFlags>。  
  
## <a name="see-also"></a>另請參閱  
 [MiningModel 元素&#40;ASSL&#41;](../../../analysis-services/scripting/objects/miningmodel-element-assl.md)   
 [MiningStructure 元素&#40;ASSL&#41;](../../../analysis-services/scripting/objects/miningstructure-element-assl.md)   
 [物件 & #40;ASSL & #41;](../../../analysis-services/scripting/objects/objects-assl.md)  
  
  
