---
title: "階層 |Microsoft 文件"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- analysis-services/multidimensional-tabular
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e3e50e89-f85d-485b-a271-1e0550520212
caps.latest.revision: 13
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 5ce337737331ecf67332e4f012993a28d59715b0
ms.contentlocale: zh-tw
ms.lasthandoff: 09/01/2017

---
# <a name="hierarchies"></a>階層
  表格式模型中的階層是中繼資料，可定義資料表中兩個 (含) 以上的資料行之間的關聯性。 在報表用戶端欄位清單中，階層可以與其他資料行分開顯示，讓用戶端使用者更易於導覽及包含在報表中。  
  
##  <a name="bkmk_benefits"></a> 優點  
 資料表可以包含數十個或甚至數百個具有不常見資料行名稱的資料行，且沒有明顯的順序。 這可能會導致未排序的報表用戶端欄位清單外觀，讓使用者很難在報表中尋找及包含資料。 階層可以針對複雜的資料結構，提供簡單直覺式的檢視。  
  
 例如，您可以在 Date 資料表中建立 Calendar 階層。 Calendar Year 做為最上層的父層級，而 Month、Week 和 Day 則加入做為子層級 (Calendar Year->Month->Week->Day)。 此階層顯示從 [日曆年度] 到 [天] 的邏輯關聯性。 用戶端使用者可以接著從 [欄位清單] 中選取 [日曆年度]，以在樞紐分析表中包含所有層級，或者展開階層，然後僅選取要包含在樞紐分析表中的特定層級。  
  
 由於階層中的每個層級各代表資料表中的一個資料行，因此您可以重新命名層級。 重新命名並不僅限於階層 (表格式模型中的任何資料行都可以重新命名)，而重新命名階層層級可讓使用者更容易在報表中尋找及包含層級。 重新命名層級只會讓層級更容易識別，並不會重新命名層級參考的資料行。 以 [日曆年度] 階層為例，在 [資料檢視] 的 Date 資料表中，[CalendarYear]、[CalendarMonth]、[CalendarWeek] 及 [CalendarDay] 資料行已分別重新命名為 [日曆年度]、[月]、[週] 及 [天]，因此更容易識別。 重新命名層級還有一個優點，那就是提供報表內容的一致性，因為使用者比較不可能需要變更資料行名稱，以便在樞紐分析表、圖表等中更容易閱讀。  
  
 階層可以包含在檢視方塊中。 檢視方塊會定義可檢視之模型子集，對模型提供具體的商務特有或應用程式特有視點。 例如，檢視方塊可以根據使用者特定的報表需求，提供必要資料項目的可檢視清單 (階層)。 如需詳細資訊，請參閱[檢視方塊](../../analysis-services/tabular-models/perspectives-ssas-tabular.md)。  
  
 階層並非用來做為安全性機制，而是用來提供較佳使用者體驗的工具。 特定階層的所有安全性，都是繼承自基礎模型。 如果使用者沒有模型物件的存取權，階層也無法提供這些存取權。 必須先解決模型資料庫的安全性，才能透過階層提供模型中物件的存取權。 您可使用安全性角色來保護模型中繼資料和資料的安全。 如需詳細資訊，請參閱[角色](../../analysis-services/tabular-models/roles-ssas-tabular.md)。  
  
##  <a name="bkmk_define"></a> Defining hierarchies  
 您可以在 [圖表檢視] 中，使用模型設計師建立及管理階層。 不支援在模型設計師的 [資料檢視] 中建立及管理階層。 若要在 [圖表檢視] 中檢視模型設計師，請按一下 **[模型]** 功能表，指向 **[模型檢視]**，然後按一下 **[圖表檢視]**。  
  
 若要建立階層，請以滑鼠右鍵按一下您要指定為父層級的資料行，然後按一下 [建立階層]。 您可以 (在單一資料表內) 複選要包含的任意資料行數目，您也可稍後按一下資料行並拖曳至父層級，以將資料行加入為子層級。 選取多個資料行時，會根據基數順序自動加入資料行。 您可以按一下資料行 (層級) 並拖曳至其他順序，或使用操作功能表上的 [向上] 和 [向下] 導覽控制項，來變更順序。 您可以透過將資料行拖放至父層級上，使用自動偵測將資料行加入為子層級。  
  
 一個資料行可以出現在多個階層中。 階層無法包含非資料行物件，例如量值或 KPI。 階層是僅以單一資料表內的資料行為基礎。 如果您複選量值及一個或多個資料行，或者選取多個資料表的資料行，即會停用操作功能表中的 [建立階層] 命令。 若要加入不同資料表的資料行，請使用 RELATED DAX 函數加入參考相關資料表之資料行的導出資料行。 此函數使用下列語法： `=RELATED(TableName[ColumnName])`。 如需詳細資訊，請參閱 RELATED 函數。  
  
 根據預設，新階層會命名為「階層 1」、「階層 2」等。您應變更階層名稱，以反映父子式關聯性的本質，讓使用者更容易識別。  
  
 建立階層之後，您可以使用 [在 Excel 中進行分析] 功能測試階層的功效。 如需詳細資訊，請參閱[在 Excel 中的進行分析](../../analysis-services/tabular-models/analyze-in-excel-ssas-tabular.md)。  
  
##  <a name="bkmk_related_tasks"></a> 相關工作  
  
|工作|Description|  
|----------|-----------------|  
|[建立及管理階層](../../analysis-services/tabular-models/create-and-manage-hierarchies-ssas-tabular.md)|描述如何在 [圖表檢視] 中，使用模型設計師建立及管理階層。|  
  
## <a name="see-also"></a>另請參閱  
 [表格式模型設計師](../../analysis-services/tabular-models/tabular-model-designer-ssas.md)   
 [檢視方塊](../../analysis-services/tabular-models/perspectives-ssas-tabular.md)   
 [角色](../../analysis-services/tabular-models/roles-ssas-tabular.md)  
  
  