---
title: ASSL 物件和物件特性 |Microsoft 文件
ms.date: 05/02/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 55150d0835fc0a9e3324acfb8007a1d22e9b55d8
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2018
---
# <a name="assl-objects-and-object-characteristics"></a>ASSL 物件和物件特性
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  Analysis Services 指令碼語言 (ASSL) 中的物件會遵循有關物件群組、繼承、命名、擴展和處理的特定指導方針。  
  
## <a name="object-groups"></a>物件群組  
 所有[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]物件都有 XML 表示。 這些物件分為兩個群組：  
  
 **主要物件**  
 主要物件可以獨立建立、改變和刪除。 主要物件包括：  
  
-   伺服器  
  
-   資料庫  
  
-   維度  
  
-   Cube  
  
-   量值群組  
  
-   資料分割  
  
-   檢視方塊  
  
-   採礦模型  
  
-   角色  
  
-   與伺服器或資料庫相關聯的命令  
  
-   資料來源  
  
 主要物件具有下列可追蹤其記錄與狀態的屬性。  
  
-   **CreatedTimestamp**  
  
-   **LastSchemaUpdate**  
  
-   **LastProcessed** （適當的話）  
  
> [!NOTE]  
>  將物件分類為主要物件會影響 [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] 的執行個體處理 (Treat)該物件的方式，以及如何以物件定義語言處理 (Handle) 該物件。 不過，這個分類無法保證 [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] 管理與開發工具，將允許獨立地建立、修改或刪除這些物件。  
  
 **次要物件**  
 次要物件只能在父主要物件的建立、修改或刪除過程中，建立、修改或刪除。 次要物件包括：  
  
-   階層和層級  
  
-   屬性  
  
-   [量值]  
  
-   採礦模型資料行  
  
-   與 Cube 相關聯的命令  
  
-   Aggregations  
  
## <a name="object-expansion"></a>物件展開  
 **ObjectExpansion**限制可用來控制由伺服器傳回的 ASSL XML 展開程度。 這個限制具有下表中所列的選項。  
  
|列舉值|允許\<Alter >|Description|  
|-----------------------|---------------------------|-----------------|  
|*ReferenceOnly*|否|只會為要求的物件以及為所有包含的主要物件，遞迴地傳回名稱、識別碼和時間戳記。|  
|*ObjectProperties*|是|展開要求的物件與所含的次要物件，但是不會傳回所含的主要物件。|  
|*ExpandObject*|否|與相同*ObjectProperties*，但也會傳回名稱、 識別碼和包含的主要物件的時間戳記。|  
|*ExpandFull*|是|以遞迴方式完全展開要求的物件以及所有包含的物件。|  
  
 這個 ASSL 參考章節描述*ExpandFull*表示法。 所有其他**ObjectExpansion**層級都衍生自這個層級。  
  
## <a name="object-processing"></a>物件處理  
 ASSL 包括的唯讀元素或是屬性 (例如， **LastProcessed**) 可以讀取從[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]執行個體，但命令指令碼提交到執行個體時，會省略。 [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] 會在沒有警告或錯誤的情況下，忽略唯讀元素已修改的值。  
  
 [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] 也會忽略不適當或是不相關的屬性，而不會引發驗證錯誤。 例如，X 元素應該只有在 Y 元素具有特定值時才出現。 [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] 執行個體會忽略 X 元素，而不會針對 Y 元素值來驗證該元素。  
  
  
