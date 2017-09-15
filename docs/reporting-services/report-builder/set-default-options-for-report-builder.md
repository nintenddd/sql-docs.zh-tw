---
title: "設定預設選項，報表產生器 |Microsoft 文件"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- "10427"
ms.assetid: 423360de-9bed-462e-921f-60a5abab004f
caps.latest.revision: 15
author: maggiesMSFT
ms.author: maggies
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 38dd786c1f1caabb5e949784bb4c9dd98eab7281
ms.contentlocale: zh-tw
ms.lasthandoff: 08/09/2017

---
# <a name="set-default-options-for-report-builder"></a>設定報表產生器的預設選項
  在報表產生器中，您可以設定許多實用的預設值，來更輕鬆快速地撰寫報表。  例如，如果您設定或變更預設報表伺服器，除非您另外指定，否則報表產生器會自動將您的報表儲存到相同的報表伺服器。  
  
-   在 報表產生器中，按一下 **檔案** > **選項**。  
  
## <a name="uielement-list"></a>UIElement 清單  
 **預設使用此報表伺服器或 SharePoint 網站**  
 您的管理員可能已經設定這個選項。 此值可以是以 http:// 或 https:// 為開頭的正確格式 URL。 這項設定會決定預設顯示在資料表/矩陣和圖表精靈中的資料來源連接。 此外，您的報表將在這個伺服器上處理，而且您可以參考來自這個伺服器的資源。  
  
 如果您選取不同的報表伺服器，可能必須重新啟動報表產生器，才能讓這項變更生效。  
  
 **預設發行報表組件到這個資料夾**  
 報表產生器會儲存您發行到這個資料夾的報表組件。 如果此資料夾尚未存在，而且您有權在報表伺服器上建立資料夾，報表產生器將會建立這個資料夾。  
  
 您不需要重新啟動報表產生器，這項設定也會生效。  
  
 **顯示下列數量之最近使用的網站和伺服器**  
 指定要顯示在 [開啟報表] 和 [另存為報表] 對話方塊中的最近使用之網站和連接的數目。  
  
 **顯示下列數量之最近使用的共用資料集和資料來源連接**  
 指定要顯示在 [資料集屬性] 對話方塊和資料區域精靈之 [選擇與資料來源的連接] 頁面中的最近使用之共用資料集和資料來源連接的數目。  
  
 **顯示下列數量之最近使用的文件**  
 指定要在您按一下 [報表產生器] 按鈕時顯示的最近使用之文件的數目。  
  
 **清除所有最近使用的項目清單**  
 清除最近使用之網站和伺服器、共用資料集和共用資料來源連接以及文件的目前清單。  
  
## <a name="see-also"></a>請參閱＜  
 [啟動報表產生器](../../reporting-services/report-builder/start-report-builder.md)  
  
  