---
title: "建立儲存 FILESTREAM 資料的資料表 | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- dbe-blob
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FILESTREAM [SQL Server], table storage
ms.assetid: 029c3059-5c83-43e2-a859-9027031b7de1
caps.latest.revision: 16
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 7dd390bcb61a1e8f320fb6aa3a4c0209dfab3d77
ms.contentlocale: zh-tw
ms.lasthandoff: 06/22/2017

---
# <a name="create-a-table-for-storing-filestream-data"></a>建立儲存 FILESTREAM 資料的資料表
  此主題說明如何建立儲存 FILESTREAM 資料的資料表。  
  
 當檔案庫中已有 FILESTREAM 檔案群組時，您就可以建立或修改資料表，以便儲存 FILESTREAM 檔案。 若要指定包含 FILESTREAM 資料的資料行，您可以建立 **varbinary(max)** 資料行，並加入 FILESTREAM 屬性。  
  
### <a name="to-create-a-table-to-store-filestream-data"></a>建立可儲存 FILESTREAM 資料的資料表  
  
1.  在 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]中，按一下 [新增查詢]  顯示 [查詢編輯器]。  
  
2.  將下列範例的 [!INCLUDE[tsql](../../includes/tsql-md.md)] 程式碼複製到 [查詢編輯器] 中。 這個 [!INCLUDE[tsql](../../includes/tsql-md.md)] 程式碼會建立稱為 Records 的啟用 FILESTREAM 資料表。  
  
3.  若要建立此資料表，請按一下 **[執行]**。  
  
## <a name="example"></a>範例  
 下列程式碼範例示範如何建立名為 `Records`的資料表。 `Id` 資料行是 `ROWGUIDCOL` 資料行，而且必須搭配 Win32 API 使用 FILESTREAM 資料。 `SerialNumber` 資料行屬於 `UNIQUE INTEGER`。 `Chart` 資料行是 `FILESTREAM` 資料行，而且可用來將 `Chart` 儲存在檔案系統中。  
  
> [!NOTE]  
>  這個範例參考在 [建立啟用 FILESTREAM 的資料庫](../../relational-databases/blob/create-a-filestream-enabled-database.md)中建立的 Archive 資料庫。  
  
 [!code-sql[FILESTREAM#FS_CreateTable](../../relational-databases/blob/codesnippet/tsql/create-a-table-for-stori_1.sql)]  
  
## <a name="see-also"></a>另請參閱  
 [CREATE TABLE &#40;Transact-SQL&#41;](../../t-sql/statements/create-table-transact-sql.md)   
 [ALTER TABLE &#40;Transact-SQL&#41;](../../t-sql/statements/alter-table-transact-sql.md)  
  
  