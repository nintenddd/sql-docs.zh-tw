---
title: AssociationSet 元素 (CSDLBI) |Microsoft 文件
ms.date: 05/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: tabular-models
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: c2ae4f565a2383284421bb433ed5cc98371196d3
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2018
---
# <a name="associationset-element-csdlbi"></a>AssociationSet 元素 (CSDLBI)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  **AssociationSet** 元素是定義關聯的複雜類型。 在 CSDLBI 資料模型中，關聯是指兩個資料表之間的關聯性。  
  
 模型中每個唯一的關聯性都必須有指定的 **AssociationSet**。 **AssociationSet** 元素會使用 **Association** 元素定義端點。 **AssociationSet** 元素也會定義有關資料模型中關聯性及其使用情形的中繼資料。  
  
## <a name="applicable-attributes"></a>適用的屬性  
 下表列出定義 **AssociationSet** 元素的元素和屬性。  
  
|名稱|是否必要|說明|  
|----------|-----------------|-----------------|  
|State|是|指出關聯是否為使用中的字串。 值是由 State 元素所定義。|  
|Hidden|否|布林值，指出關聯性是否可見。 根據預設，Hidden 的值為 **false**，表示模型中的所有關聯性都可見。|  
  
## <a name="state-element"></a>State 元素  
 **State** 元素是簡單類型，用於描述關聯為使用中且應在計算中使用，或是為非使用中且必須在計算中明確參考。  
  
 如果有多個關聯集連接兩個實體，則只能將一個關聯集標示為「使用中」。 換句話說，如果同樣兩個資料表之間有兩個關聯性，則只能有一個使用中的關聯性。  
  
 下表列出 **State** 元素的值。  
  
|Value|說明|  
|-----------|-----------------|  
|作用中|關聯為使用中。|  
|非使用中|關聯為使用中。|  
  
## <a name="example"></a>範例  
 **表格式**  
  
 下列範例顯示 AdventureWorks 表格式模型中的關聯性 (在 CSDLBI 1.1 版中)。 關聯已標示為「非使用中」，因為有現有的關聯性 (OrderKey 和 Date 之間)。  
  
```  
<AssociationSet   
    Name="InternetSales_Date_Date_Date"  
    Association="Sandbox.InternetSales_Date_Date_Date">  
    <End EntitySet="InternetSales" />  
    <End EntitySet="DimDate" />  
<bi:AssociationSet State="Inactive" />  
</AssociationSet>  
  
```  
  
## <a name="example"></a>範例  
 **多維度**  
  
 下列範例顯示 Contoso Operations Cube 中 Sales 和 Currency 資料表之間定義的關聯性。  
  
```  
<AssociationSet   
    Name ="Sales_Currency_Currency_Currency_Name2"  
    Association ="Sandbox.Sales_Currency_Currency_Currency_Name2">  
    <End EntitySet ="Sales" />  
    <End EntitySet ="Currency" />  
<bi:AssociationSet />  
</AssociationSet>  
```  
  
## <a name="see-also"></a>另請參閱  
 [Csdl 的 BI 註解的技術參考](../../../analysis-services/tabular-model-programming-compatibility-levels-1050-1103/conceptual-schema-definition-language-csdl/technical-reference-for-bi-annotations-to-csdl.md)  
  
  
