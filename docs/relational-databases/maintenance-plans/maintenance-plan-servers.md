---
title: 維護計畫 (伺服器) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: maintenance-plans
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql13.swb.maint.servers.f1
- sql13.swb.maint.maintplanproperties.server.f1
ms.assetid: ac24d1a8-dd2f-4162-b804-c0df1fc1e61d
caps.latest.revision: 7
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 5320b4313a2871a92f8480d3dac5869130e5acf7
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2018
---
# <a name="maintenance-plan-servers"></a>維護計畫 (伺服器)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  使用 **[伺服器]** 對話方塊可選取要執行維護計畫的伺服器。  
  
 若要建立多伺服器維護計畫，必須設定多伺服器環境，其中包含一個主要伺服器以及一或多個目標伺服器。 針對多伺服器維護計畫，本機伺服器應設為主要伺服器。 在多伺服器環境中，這個對話方塊會顯示 **(本機)** 主要伺服器以及所有相對應的目標伺服器。 本機伺服器會建立 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent 作業。 這會視您是否選取 **(本機)** 伺服器而啟用或停用。 如果選取目標伺服器，會建立多伺服器作業並下載到每個選取的目標伺服器。 如果沒有選取目標伺服器，會刪除多伺服器作業。  
  
## <a name="see-also"></a>另請參閱  
 [維護計畫](../../relational-databases/maintenance-plans/maintenance-plans.md)   
 [建立多伺服器環境](http://msdn.microsoft.com/library/edc2b60d-15da-40a1-8ba3-f1d473366ee6)   
 [設為主要伺服器](http://msdn.microsoft.com/library/05739a73-1fdf-4d9d-92a6-70f328380322)   
 [設為目標伺服器](http://msdn.microsoft.com/library/13aabe2d-67fe-4c67-8d49-2928dd705b7a)  
  
  
