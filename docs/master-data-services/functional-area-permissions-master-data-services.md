---
title: 功能區域權限 (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: mds
ms.component: non-specific
ms.reviewer: ''
ms.suite: sql
ms.technology:
- master-data-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- functional area permissions [Master Data Services], about functional area permissions
- functional area permissions [Master Data Services]
- permissions [Master Data Services], functional areas
ms.assetid: a80b87b3-b904-4cda-8582-0761c2617c57
caps.latest.revision: 10
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: 8076491b0cce0bc80b0c775271fe46c672c7f88a
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2018
---
# <a name="functional-area-permissions-master-data-services"></a>功能區域權限 (Master Data Services)

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

  您可以將權限指派給 [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] 使用者介面 (UI) 的每個功能區域。 下列是功能區域：  
  
-   **總管**  
  
-   **版本管理**  
  
-   **整合管理**  
  
-   **系統管理**  
  
-   **使用者及群組的權限**  
  
-   **進階使用者**  
  
 當您將權限指派給功能區域時，您會讓使用者或群組看到 UI 的區域。  
  
 在總管功能區域中，指派給模型物件和階層成員的其他權限會決定使用者可以存取的資料。 在所有其他功能區域中，使用者必須是模型管理員，才能檢視及操作模型。 如需詳細資訊，請參閱 [管理員 &#40;Master Data Services&#41;](../master-data-services/administrators-master-data-services.md)，您就可以在群組中加入及移除使用者。  
  
> [!IMPORTANT]  
>  具有進階使用者權限的使用者實際上具有所有模型的系統管理員權限，而且具有所有其他功能權限。  
  
 使用者或群組至少必須擁有 [模型] 索引標籤上的一個功能區域和一個模型的權限，才能存取 [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]。  
  
## <a name="see-also"></a>另請參閱  
 [指派功能區域權限 &#40;Master Data Services&#41;](../master-data-services/assign-functional-area-permissions-master-data-services.md)   
 [模型物件權限 &#40;Master Data Services&#41;](../master-data-services/model-object-permissions-master-data-services.md)   
 [階層成員權限 &#40;Master Data Services&#41;](../master-data-services/hierarchy-member-permissions-master-data-services.md)   
 [如何決定權限 &#40;Master Data Services&#41;](../master-data-services/how-permissions-are-determined-master-data-services.md)  
  
  
