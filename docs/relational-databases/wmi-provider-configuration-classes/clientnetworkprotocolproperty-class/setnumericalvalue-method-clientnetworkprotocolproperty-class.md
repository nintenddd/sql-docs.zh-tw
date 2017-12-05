---
title: "SetNumericalValue 方法 （ClientNetworkProtocolProperty 類別） |Microsoft 文件"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: wmi
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: reference
apiname: SetNumericalValue Method (ClientNetworkProtocolProperty Class)
apilocation: sqlmgmproviderxpsp2up.mof
apitype: MOFDef
helpviewer_keywords: SetNumericalValue method
ms.assetid: d4d6df52-9e68-4003-9e28-ece6716ba7f1
caps.latest.revision: "12"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 8a4f6f11599423793da335a46d32cb678e2575ea
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/17/2017
---
# <a name="setnumericalvalue-method-clientnetworkprotocolproperty-class"></a>SetNumericalValue 方法 (ClientNetworkProtocolProperty 類別)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]設定所參考之目前屬性的數值[PropertyIdx 屬性 （ClientNetworkProtocolProperty 類別）](../../../relational-databases/wmi-provider-configuration-classes/clientnetworkprotocolproperty-class/propertyidx-property-clientnetworkprotocolproperty-class.md)值。  
  
## <a name="syntax"></a>語法  
  
```  
  
object.SetNumericalValue [= value]  
```  
  
## <a name="parts"></a>組件  
 *物件*  
 A [ClientNetworkProtocolProperty 類別](../../../relational-databases/wmi-provider-configuration-classes/clientnetworkprotocolproperty-class/clientnetworkprotocolproperty-class.md)物件，代表所使用的網路通訊協定的屬性[!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]用戶端。  
  
#### <a name="parameters"></a>參數  
  
|參數|Description|  
|---------------|-----------------|  
|*value*|A **uint32**值，指定參考之屬性的數值。|  
  
## <a name="property-valuereturn-value"></a>屬性值/傳回值  
 A **uint32**值為 0，如果已成功修改此服務，不支援要求，則為 1，而其他數值則表示錯誤。  
  
## <a name="remarks"></a>備註  
  
## <a name="see-also"></a>請參閱＜  
 [設定用戶端通訊協定](../../../database-engine/configure-windows/configure-client-protocols.md)  
  
  