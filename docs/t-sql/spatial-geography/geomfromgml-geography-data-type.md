---
title: GeomFromGML (geography 資料類型) | Microsoft Docs
ms.custom: ''
ms.date: 07/30/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.component: t-sql|spatial-geography
ms.reviewer: ''
ms.suite: sql
ms.technology: t-sql
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- GeomFromGML_TSQL
- GeomFromGML
dev_langs:
- TSQL
helpviewer_keywords:
- GeomFromGML (geography Data Type)
- GeomFromGML method
ms.assetid: 470d0997-3cb0-4d34-9a45-b332fe432b14
caps.latest.revision: 18
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 59856edcca0915b0c347e381943ec2e44bb5a564
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2018
---
# <a name="geomfromgml-geography-data-type"></a>GeomFromGML (geography 資料類型)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

在提供了地理標記語言 (GML) [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 子集中的表示法時，建構 **geography** 執行個體。
  
如需有關 GML 的詳細資訊，請參閱以下開放地理空間協會規格：[OGC 規格，地理標記語言](http://go.microsoft.com/fwlink/?LinkId=93629) \(英文\)
  
這個 **geography** 資料類型方法可支援 **FullGlobe** 執行個體或大於半球的空間執行個體。
  
## <a name="syntax"></a>語法  
  
```  
  
GeomFromGml ( GML_input, SRID )  
```  
  
## <a name="arguments"></a>引數  
 *GML_input*  
 這是 XML 輸入，GML 將會從此輸入傳回值。  
  
 *SRID*  
 這是 **int** 運算式，表示要傳回之 **geography** 執行個體的空間參考識別碼 (SRID)。  
  
## <a name="return-types"></a>傳回類型  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 傳回類型：**geography**  
  
 CLR 傳回類型：**SqlGeography**  
  
## <a name="remarks"></a>Remarks  
 如果輸入的格式不正確，這個方法將會擲回 **FormatException**。  
  
 如果輸入包含對蹠邊緣，這個方法會擲回 **ArgumentException**。  
  
## <a name="examples"></a>範例  
 下列範例會使用 `GeomFromGml()` 建立 `geography` 例項。  
  
```  
DECLARE @g geography;  
DECLARE @x xml;  
SET @x = '<LineString xmlns="http://www.opengis.net/gml"><posList>47.656 -122.36 47.656 -122.343</posList></LineString>';  
SET @g = geography::GeomFromGml(@x, 4326);  
SELECT @g.ToString();  
```  
  
 下列範例會使用 `GeomFromGml()` 建立 `FullGlobe``geography` 例項。  
  
```  
DECLARE @g geography;  
DECLARE @x xml;  
SET @x = '<FullGlobe xmlns="http://schemas.microsoft.com/sqlserver/2011/geography" />';  
SET @g = geography::GeomFromGml(@x, 4326);  
SELECT @g.ToString();  
```  
  
## <a name="see-also"></a>另請參閱  
 [擴充的靜態地理方法](../../t-sql/spatial-geography/extended-static-geography-methods.md)  
  
  
