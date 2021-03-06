---
title: 資料行散發 （資料採礦） |Microsoft 文件
ms.date: 05/01/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: data-mining
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 83da6c1ba0a278d2d6b80f309a7bc7f6a1688ba4
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2018
---
# <a name="column-distributions-data-mining"></a>資料行散發 (資料採礦)
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
  在 [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 中，您可以在採礦結構中定義資料行散發，以影響您建立採礦模型時演算法如何處理這些資料行中的資料。 針對某些演算法，若已知資料行包含值的通用散發，則在處理模型前先定義任何連續資料行的散發很有用。 如果您未定義散發，則產生之採礦模型所做出的預測，可能不如定義了散發的預測那般精確，因為演算法能用來解譯資料的資訊比較少。  
  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 中可用的演算法支援下列散發類型：  
  
 **一般**  
 連續資料行的值形成含有一般分佈的長條圖。  
  
 ![使用常態分佈的長條圖](../../analysis-services/data-mining/media/normal-distribution.gif "常態分佈的長條圖")  
  
 **Log Normal**  
 連續資料行的值形成長條圖，其曲線在上端伸長，朝下端偏斜。  
  
 ![使用對數常態分佈的長條圖](../../analysis-services/data-mining/media/log-normal-distribution.gif "使用對數常態分佈的長條圖")  
  
 **Uniform**  
 連續資料行的值形成平坦曲線，其中所有值的機率都相當之。  
  
 ![使用統一分佈的長條圖](../../analysis-services/data-mining/media/uniform-distribution.gif "使用統一分佈的長條圖")  
  
 如需 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]提供的演算法的詳細資訊，請參閱[資料採礦演算法 &#40;Analysis Services - 資料採礦&#41;](../../analysis-services/data-mining/data-mining-algorithms-analysis-services-data-mining.md)。  
  
## <a name="see-also"></a>另請參閱  
 [內容類型 & #40; 資料採礦 & #41;](../../analysis-services/data-mining/content-types-data-mining.md)   
 [採礦結構 & #40;Analysis Services-資料採礦 & #41;](../../analysis-services/data-mining/mining-structures-analysis-services-data-mining.md)   
 [離散化方法 & #40; 資料採礦 & #41;](../../analysis-services/data-mining/discretization-methods-data-mining.md)   
 [分佈 & #40; DMX & #41;](../../dmx/distributions-dmx.md)   
 [採礦結構資料行](../../analysis-services/data-mining/mining-structure-columns.md)  
  
  
