---
title: 教學課程：建立基本資料表報表 (報表產生器) | Microsoft Docs
ms.custom: ''
ms.date: 06/23/2016
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.component: reporting-services
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
- SQL Server 2016
ms.assetid: d9e30521-f8ae-4c45-89c3-d40727f622f7
caps.latest.revision: 16
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e03e955d70e46dea954dcc4cce83faece6c2e2ea
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2018
---
# <a name="tutorial-creating-a-basic-table-report-report-builder"></a>教學課程：建立基本資料表報表 (報表產生器)
本教學課程將教導您根據範例銷售資料建立基本資料表報表。 下圖顯示您將建立的報表。  
  
![SSRS_Tutorial_Basic_Table_Report](../reporting-services/media/ssrs-tutorial-basic-table-report.png)  
  

完成這個教學課程的估計時間：30 分鐘。  
  
## <a name="requirements"></a>需求  
如需需求的詳細資訊，請參閱[教學課程的必要條件 &#40;報表產生器&#41;](../reporting-services/prerequisites-for-tutorials-report-builder.md)。  
  
## <a name="CreateTable"></a>1.使用精靈建立報表  
使用資料表或矩陣精靈建立資料表報表。 模式有兩種：報表設計和共用資料集設計。 在報表設計模式中，您可以在 [報表資料] 窗格中指定資料，並且在設計介面上指定報表配置。 在共用資料集設計模式中，您可以建立資料集查詢，以便與其他人共用。 在本教學課程中，您將使用報表設計模式。  
  
### <a name="to-create-a-report"></a>建立報表  
  
1.  從您的電腦、[!INCLUDE[ssRSnoversion_md](../includes/ssrsnoversion-md.md)] Web 入口網站或 SharePoint 整合模式[啟動報表產生器](../reporting-services/report-builder/start-report-builder.md)。  
  
    [新報表或資料集] 對話方塊隨即開啟。  
  
    如果您看不到 [新增報表或資料集] 對話方塊，請按一下 [檔案] 功能表 > [新增]。  
  
2.  在左窗格中，確認已選取 **[新增報表]** 。  
  
3.  在右窗格中，選取 [資料表或矩陣精靈]。  
  
## <a name="DataConnection"></a>1a. 在資料表精靈中指定資料連接  
資料連接包含連接至外部資料來源的資訊，例如 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] 資料庫。 通常您會向資料來源擁有者取得連接資訊以及要使用的認證類型。 若要指定資料連接，您可以使用來自報表伺服器的共用資料來源，或是建立僅在此報表中使用的內嵌資料來源。  
  
在本教學課程中，您將使用內嵌資料來源。 若要深入了解如何使用共用資料來源，請參閱[取得資料連線的替代方式 &#40;報表產生器&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md)。  
  
### <a name="to-create-an-embedded-data-source"></a>建立內嵌資料來源  
  
1.  在 **[選擇資料集]** 頁面上，選取 **[建立資料集]**，然後按 **[下一步]**。 **[選擇與資料來源的連接]** 頁面隨即開啟。  
  
2.  按一下 **[新增]**。 **[資料來源屬性]** 對話方塊隨即開啟。  
  
3.  在 [名稱] 中鍵入 **Product_Sales** 作為資料來源的名稱。  
  
4.  在 [選取連線類型] 中，驗證已選取 [Microsoft SQL Server]。  
  
5.  在 [連接字串] 中鍵入下列文字，其中 \<servername> 是 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] 執行個體的名稱：  
  
    ```  
    Data Source=<servername>  
    ```  
  
    由於您將使用包含資料的查詢，而不是從資料庫擷取資料，因此連接字串不會包含資料庫名稱。 如需詳細資訊，請參閱[教學課程的必要條件 &#40;報表產生器&#41;](../reporting-services/prerequisites-for-tutorials-report-builder.md)。  
  
6.  按一下 [認證] 索引標籤。輸入您存取外部資料來源所需的認證。  
  
7. 再按一次 [一般] 索引標籤。 若要確認您能夠連接至資料來源，請按一下 **[測試連接]**。  
  
    「成功建立連接」訊息就會出現。  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
    您會回到 [選擇與資料來源的連線] 頁面，並選取了新的資料來源。  
  
9. 按 [下一步] 。  
  
## <a name="Query"></a>1b. 在資料表精靈中建立查詢  
在報表中，您可以使用擁有預先定義查詢的共用資料集，或是建立只在此一報表中使用的內嵌資料集。 在本教學課程中，您將建立內嵌資料集。  
  
> [!NOTE]  
> 在本教學課程中，查詢會包含資料值，因此不需要外部資料來源。 這樣會使查詢相當冗長。 在商業環境中，查詢不會包含資料。 這僅供教學之用。  
  
### <a name="to-create-a-query"></a>建立查詢  
  
1.  [設計查詢] 頁面上會開啟關聯式查詢設計工具。 在這個教學課程中，您將使用以文字為基礎的查詢設計工具。  
  
    按一下 [當成文字編輯]。 以文字為基礎的查詢設計工具會顯示查詢窗格和結果窗格。  
  
2.  將下列 [!INCLUDE[tsql](../includes/tsql-md.md)] 查詢貼入上方空白方塊。  
  
    ```  
    SELECT CAST('2009-01-05' AS date) as SalesDate, 'Accessories' as Subcategory,   
       'Carrying Case' as Product, CAST(9924.60 AS money) AS Sales, 68 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Tripod' as Product, CAST(1350.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2009-01-11' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Lens Adapter' as Product, CAST(1147.50 AS money) AS Sales, 17 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Mini Battery Charger' as Product, CAST(1056.00 AS money) AS Sales, 44 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Accessories' as Subcategory,  
       'Telephoto Conversion Lens' as Product, CAST(1380.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,'Accessories' as Subcategory,    
       'USB Cable' as Product, CAST(780.00 AS money) AS Sales, 26 as Quantity  
    UNION SELECT CAST('2009-01-08' AS date) as SalesDate, 'Accessories' as Subcategory,   
       'Budget Movie-Maker' as Product, CAST(3798.00 AS money) AS Sales, 9 as Quantity  
    UNION SELECT CAST('2009-01-09' AS date) as SalesDate, 'Camcorders' as Subcategory,   
       'Business Videographer' as Product, CAST(10400.00 AS money) AS Sales, 13 as Quantity  
    UNION SELECT CAST('2009-01-10' AS date) as SalesDate, 'Camcorders' as Subcategory,   
       'Social Videographer' as Product, CAST(3000.00 AS money) AS Sales, 60 as Quantity  
    UNION SELECT CAST('2009-01-11' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Advanced Digital' as Product, CAST(7234.50 AS money) AS Sales, 39 as Quantity  
    UNION SELECT CAST('2009-01-07' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Compact Digital' as Product, CAST(10836.00 AS money) AS Sales, 84 as Quantity  
    UNION SELECT CAST('2009-01-08' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Consumer Digital' as Product, CAST(2550.00 AS money) AS Sales, 17 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Digital' as Subcategory,   
       'Slim Digital' as Product, CAST(8357.80 AS money) AS Sales, 44 as Quantity  
    UNION SELECT CAST('2009-01-09' AS date) as SalesDate, 'Digital SLR' as Subcategory,   
       'SLR Camera 35mm' as Product, CAST(18530.00 AS money) AS Sales, 34 as Quantity  
    UNION SELECT CAST('2009-01-07' AS date) as SalesDate, 'Digital SLR' as Subcategory,   
       'SLR Camera' as Product, CAST(26576.00 AS money) AS Sales, 88 as Quantity  
  
    ```  
  
3.  在查詢設計工具工具列上，按一下 **[執行]** \(**!**)。  
  
    查詢隨即執行，並顯示 SalesDate、Subcategory、Product、Sales 和 Quantity 欄位的結果集。  
  
    在結果集中，欄標題是依據查詢中的名稱而定。 在資料集中，欄標題會變成欄位名稱，並且儲存在報表中。 完成精靈後，您可以使用 [報表資料] 窗格檢視資料集欄位的集合。  
  
4.  按 [下一步] 。  
  
## <a name="Groups"></a>1c. 在資料表精靈中將資料組織成群組  
選取做為群組對象的欄位時，您會設計包含資料列和資料行的資料表，以顯示詳細資料和彙總資料。  
  
### <a name="to-organize-data-into-groups"></a>若要將資料組織為群組  
  
1.  在 [排列欄位] 頁面上，將 [Product] 拖曳至 [值]。  
  
2.  將 [Quantity] 拖曳至 [值] 並放置在 [Product] 之下。  
  
    Sum 函數 (數值欄位的預設彙總) 會自動彙總 [Quantity]。 值為 [Sum(Quantity)]。  
  
    選取 [Sum(Quantity)] 旁的箭號，以檢視其他可用的彙總函式。 請不要變更彙總函式。  
  
3.  將 [Sales] 拖曳至 [值] 並放置在 [Sum(Quantity)] 之下。  
  
    [Sales] 是透過 Sum 函數彙總。 值為 [Sum(Sales)]。  
  
    步驟 1、2 和 3 會指定要在資料表中顯示的資料。  
  
4.  將 [SalesDate] 拖曳至 [資料列群組]。  
  
5.  將 [Subcategory] 拖曳至 [資料列群組] 並放置在 [SalesDate] 之下。  
  
    步驟 4 和 5 會先依日期，再依該日期的產品子類別組織欄位的值。  
  
6.  按 [下一步] 。  
  
## <a name="Subtotals"></a>1d. 在資料表精靈中加入小計和總計資料列  
建立群組之後，您可以加入並格式化要顯示欄位彙總值的資料列。 您可以選擇要顯示所有資料，或是讓使用者以互動方式展開和摺疊分組資料。  
  
### <a name="to-add-subtotals-and-totals"></a>加入小計和總計  
  
1.  在 **[選擇配置]** 頁面的 **[選項]** 下方，確定已選取 **[顯示小計和總計]** 。  
  
2.  驗證已選取 [區塊式，小計位於下方]。  
  
    精靈的 [預覽] 窗格會顯示含有五個資料列的資料表。 當您執行報表時，每個資料列都會以下列方式顯示：  
  
    1.  第一個資料列會針對資料表重複一次，以顯示資料行標題。  
  
    2.  第二個資料列會針對銷售訂單中的每一行項目重複一次，並顯示產品名稱、訂單數量和行總計。  
  
    3.  第三個資料列會針對每筆銷售訂單重複一次，以顯示每筆訂單的小計。  
  
    4.  第四個資料列則會針對每個訂貨日期重複一次，以顯示每天的小計。  
  
    5.  第五個資料列會針對資料表重複一次，以顯示總計。  
  
3.  清除 [展開/摺疊群組] 選項。 在本教學課程中，您建立的報表不會使用向下鑽研功能，此功能可讓使用者展開父群組階層，以顯示子群組資料列和詳細資料列。  
  
4.  按一下 [下一步] 預覽資料表，然後按一下 [完成]。  
  
資料表會加入至設計介面。 這個資料表有 5 個資料行和 5 個資料列。 [資料列群組] 窗格會顯示三個資料列群組：[SalesDate]、[Subcategory] 和 [Details]。 詳細資料是資料集查詢擷取的所有資料。  
  
## <a name="FormatCurrency"></a>2.將資料格式化為貨幣  
根據預設，[Sales] 欄位的摘要資料會顯示一般數字。 格式化該欄位，將數字顯示為貨幣。   
  
### <a name="to-format-a-currency-field"></a>格式化貨幣欄位  
  
1.  若要在 [設計] 檢視中查看格式化文字方塊及預留位置文字顯示範例值，請在 [主資料夾] 索引標籤的 [數字] 群組中，按一下**預留位置樣式**圖示旁的箭號 > [範例值]。  
  
2.   在 [Sales] 資料行中，按一下第二列的資料格 (位於欄標題資料列底下)，然後向下拖曳以選取包含 `[Sum(Sales)]`的所有資料格。  
  
3.  在 [主資料夾] 索引標籤的 [數字] 群組中，按一下 [貨幣] 按鈕。 這些資料格就會變更為顯示格式化貨幣。  
  
    如果您的地區設定為 [英文 (美國)]，則預設範例文字會是 [**$12,345.00**]。 如果看不到範例貨幣值，請在 [主資料夾] 索引標籤的 [數字] 群組中，按一下**預留位置樣式**圖示旁的箭號 > [範例值]。  
  
4.  按一下 [執行] 以預覽報表。  
  
[Sales] 的摘要值會顯示為貨幣。  
  
## <a name="FormatDate"></a>3.將資料格式化為日期  
根據預設，[SalesDate] 欄位會同時顯示日期和時間。 您可以將該欄位格式化，以便只顯示日期。  
  
### <a name="to-format-a-date-field-as-the-default-format"></a>將日期欄位格式化成預設格式  
  
1.  按一下 **[設計]** 返回 [設計] 檢視。  
  
2.  按一下包含 `[SalesDate]`的資料格。  
  
3.  在功能區上，於 [主資料夾] 索引標籤的 [數字] 群組中，按一下箭號並選取 [日期]。  
  
    資料格就會顯示範例日期 **[1/31/2000]**。 如果看不到範例日期，請在 [主資料夾] 索引標籤的 [數字] 群組中，按一下**預留位置樣式**圖示旁的箭號 > [範例值]。  
  
4.  按一下 **[執行]** 預覽報表。  
  
SalesDate 值會以預設的日期格式顯示。  
  
### <a name="to-change-the-date-format-to-a-custom-format"></a>若要將日期格式變更為自訂格式  
  
1.  按一下 **[設計]** 返回 [設計] 檢視。  
  
2.  選取包含 `[SalesDate]`的資料格。  
  
3.  在 [主資料夾] 索引標籤的 [數字] 群組中，按一下右下角的箭號以開啟對話方塊。  
  
    [文字方塊屬性] 對話方塊隨即開啟。  
  
4.  在 [類別目錄] 窗格中，驗證已選取 [日期]。  
  
5.  在 [類型] 窗格中，選取 [January 31, 2000]。  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
    資料格就會顯示範例日期 **[January 31, 2000]**。  
  
7.  按一下 [執行] 以預覽報表。  
  
SalesDate 值會顯示月份的名稱，而不是月份的數字。  
  
## <a name="Width"></a>4.變更資料行寬度  
根據預設，資料表中的每個資料格都會包含一個文字方塊。 頁面轉譯時，文字方塊會垂直展開以容納文字。 在轉譯的報表中，每一個資料列都會依照資料列中最高的轉譯文字方塊高度展開。 設計介面上資料列的高度對於轉譯報表中資料列的高度並無影響。  
  
若要減少每個資料列佔用的垂直空間數量，請展開資料行寬度以容納一行上資料行中預期的文字方塊內容。  
  
### <a name="to-change-the-width-of-table-columns"></a>變更資料表資料行的寬度  
  
1.  按一下 **[設計]** 返回 [設計] 檢視。  
  
2.  按一下資料表，使資料行和資料列控點出現在資料表的上面和旁邊。  
  
    沿著資料表頂端和側邊的灰色長條是資料行和資料列控點。  
  
3.  指向資料行控點之間的線條，使游標變成雙箭頭。 將資料行拖曳為所需的寬度。 例如，您可以展開產品的資料行，以便在同一行顯示產品名稱。  
  
4.  按一下 [執行] 以預覽報表。  
  
## <a name="Title"></a>5.加入報表標題  
報表標題會出現在報表的頂端。 您可以將報表標題放置在報表頁首，如果報表不使用報表頁首，則可以放置在報表主體頂端的文字方塊中。 在本教學課程中，您將使用自動放置在報表主體頂端的文字方塊。  
  
您可以將不同的字型樣式、大小和色彩套用到文字的片語和個別字元，進一步加強文字。 如需詳細資訊，請參閱[在文字方塊中將文字格式化 &#40;報表產生器及 SSRS&#41;](../reporting-services/report-design/format-text-in-a-text-box-report-builder-and-ssrs.md)。  
  
### <a name="to-add-a-report-title"></a>若要加入報表標題  
  
1.  在設計介面上，按一下 **[按一下以加入標題]**。  
  
2.  輸入 **Product Sales**，然後按一下文字方塊外部。  
  
3.  以滑鼠右鍵按一下包含 [Product Sales] 的文字方塊，然後按一下 [文字方塊屬性]。  
  
4.  在 [文字方塊屬性] 對話方塊中，按一下 [字型]。  
  
5.  在 [大小] 清單中，選取 [18pt]。  
  
6.  在 [色彩] 清單中，選取 [矢菊花藍]。  
  
7.  選取 [粗體]。  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
## <a name="Save"></a>6.儲存報表  
將報表儲存至報表伺服器或您的電腦。 如果沒有將報表儲存到報表伺服器，就無法使用數個 [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 功能，例如報表組件和子報表。  
  
### <a name="to-save-the-report-on-a-report-server"></a>若要將報表儲存在報表伺服器上  
  
1.  按一下 [檔案] > [另存新檔]。  
  
2.  按一下 **[最近使用的網站和伺服器]**。  
  
3.  選取或輸入您有權儲存報表之報表伺服器的名稱。  
  
    「正在連接到報表伺服器」訊息隨即顯示。 連接完成時，您就會看見報表伺服器管理員指定為預設報表位置之報表資料夾的內容。  
  
4.  在 [名稱] 中，以 **Product_Sales** 取代 [未命名]。  
  
5.  按一下 **[儲存]**。  
  
報表就會儲存至報表伺服器。 您連接之報表伺服器的名稱會顯示在視窗底部的狀態列中。  
  
### <a name="to-save-the-report-on-your-computer"></a>將報表儲存到您的電腦上  
  
1.  按一下 [檔案] > [另存新檔]。  
  
2.  按一下 [桌面]、[我的文件] 或 [我的電腦]，然後瀏覽到您要儲存報表的資料夾。  
  
3.  在 [名稱] 中，以 **Product Sales** 取代 [未命名]。  
  
4.  按一下 **[儲存]**。  
  
## <a name="Export"></a>7.匯出報表  
報表可匯出為不同的格式，例如 Microsoft Excel 和逗號分隔值 (CSV) 檔案。 如需詳細資訊，請參閱[匯出報表 &#40;報表產生器及 SSRS&#41;](../reporting-services/report-builder/export-reports-report-builder-and-ssrs.md)。  
  
在本教學課程中，您會將報表匯出到 Excel，並且設定報表上的屬性，為活頁簿索引標籤提供自訂名稱。  
  
### <a name="to-specify-the-workbook-tab-name"></a>指定活頁簿索引標籤名稱  
  
1.  按一下 **[設計]** 返回 [設計] 檢視。  
  
2.  按一下設計介面上報表外部的任何位置。  
  
3.  在 [屬性] 窗格中，尋找 InitialPageName 屬性並輸入 **Product Sales Excel**。  
  
    > [!NOTE]  
    > 如果看不到 [屬性] 窗格，請選取 **[檢視]** 索引標籤上的 **[屬性]**。  
    > 如果在 [屬性] 窗格中看不到屬性，請嘗試選取窗格頂端的 [字母順序] 按鈕，依字母順序排列所有屬性。   
  
### <a name="to-export-a-report-to-excel"></a>將報表匯出到 Excel  
  
1.  按一下 **[執行]** 預覽報表。  
  
2.  在功能區上按一下 [匯出] > [Excel]。  
  
    隨即開啟。  
  
3.  在 [另存新檔] 對話方塊中，瀏覽至您要儲存檔案的位置。  
  
4.  在 [檔案名稱] 方塊中，鍵入 **Product_Sales_Excel**。  
  
5.  驗證檔案類型為 **Excel (\*.xlsx)**。  
  
6.  按一下 **[儲存]**。  
  
### <a name="to-view-the-report-in-excel"></a>若要在 Excel 中檢視報表  
  
1.  開啟您儲存活頁簿的資料夾並按兩下 **Product_Sales_Excel.xlsx**。  
  
2.  確認活頁簿索引標籤的名稱是 **Product Sales Excel**。  
  
## <a name="next-steps"></a>Next Steps  
以上總結如何建立基本資料表報表的逐步解說。 如需資料表的詳細資訊，請參閱[資料表、矩陣和清單 &#40;報表產生器及 SSRS&#41;](../reporting-services/report-design/tables-matrices-and-lists-report-builder-and-ssrs.md)。  
  
## <a name="see-also"></a>另請參閱  
[報表產生器教學課程](../reporting-services/report-builder-tutorials.md)  
[SQL Server 2016 的報表產生器](../reporting-services/report-builder/report-builder-in-sql-server-2016.md)  
  

