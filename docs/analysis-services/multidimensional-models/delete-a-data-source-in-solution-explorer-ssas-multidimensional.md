---
title: 刪除資料來源，在 [方案總管] (SSAS 多維度) |Microsoft 文件
ms.date: 05/02/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: multidimensional-models
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 51510891524b77ee0a2edaa33f024c538dcd4b81
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2018
---
# <a name="delete-a-data-source-in-solution-explorer-ssas-multidimensional"></a>在方案總管中刪除資料來源 (SSAS 多維度)
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
  您可以刪除資料來源物件，以便從 Analysis Services 多維度模型專案中將它永久移除。  
  
 在 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]中，資料來源會提供建構資料來源檢視的基礎，而接著會使用資料來源檢視，於 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 專案或資料庫中定義維度、Cube 和採礦結構。 因此，刪除資料來源會使 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 專案中的其他 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 物件無效。 刪除物件之前，一定要檢閱所提供的相依物件清單。  
  
> [!IMPORTANT]  
>  您無法從 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 以線上模式開啟的 [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] 資料庫中，刪除其他物件所相依的資料來源。 在刪除資料來源之前，您必須先刪除相依於該資料來源之 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 資料庫中的所有物件。 如需線上模式的詳細資訊，請參閱 [在連線模式下連接至 Analysis Services 資料庫](../../analysis-services/multidimensional-models/connect-in-online-mode-to-an-analysis-services-database.md)。  
  
### <a name="to-delete-a-data-source"></a>若要刪除資料來源  
  
1.  在 [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] 中，開啟您想要從中刪除資料來源的專案，或是連接到您想要從中刪除資料來源的資料庫。  
  
2.  在**方案總管**中，展開 [資料來源] 資料夾。  
  
3.  以滑鼠右鍵按一下該資料來源，然後按一下 [刪除]。 [刪除物件] 對話方塊隨即出現，其中顯示刪除資料來源之後將失效的物件。 按一下 [確定] 刪除資料來源之前，請先仔細檢閱這份清單。  
  
4.  儲存專案。  
  
     從 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 專案刪除資料來源之後，您必須儲存修改過的專案，否則下次開啟此專案時會收到錯誤，因為當此專案嘗試載入已刪除的資料來源時，該資料來源的基礎 XML 檔案將會遺失。  
  
## <a name="see-also"></a>另請參閱  
 [多維度模型中的資料來源](../../analysis-services/multidimensional-models/data-sources-in-multidimensional-models.md)   
 [支援的資料來源 &#40;SSAS - 多維度&#41;](../../analysis-services/multidimensional-models/supported-data-sources-ssas-multidimensional.md)  
  
  
