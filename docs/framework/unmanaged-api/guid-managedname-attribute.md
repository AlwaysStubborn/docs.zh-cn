---
title: GUID_ManagedName 特性
ms.date: 03/30/2017
api_name:
- GUID_ManagedName
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GUID_ManagedName
helpviewer_keywords:
- GUID_ManagedName attribute
ms.assetid: 11e18095-e444-47bc-aff6-b887ac5dc01e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3bae50f695de81856d4fddcb2af3d1188d896642
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430006"
---
# <a name="guidmanagedname-attribute"></a>GUID_ManagedName 特性
定义指定的组件对象模型 (COM) 库的管理的命名空间名称的自定义接口属性。  
  
## <a name="syntax"></a>语法  
  
```  
[  
   custom(GUID_ManagedName, value)  
]  
```  
  
#### <a name="parameters"></a>参数  
 `value`  
 库管理的命名空间名称。  
  
## <a name="definition"></a>定义  
 `GUID_ManagedName` 在定义 Cor.h，如下所示：  
  
```  
// {0F21F359-AB84-41e8-9A78-36D110E6D2F9}  
EXTERN_GUID(GUID_ManagedName, 0xf21f359, 0xab84, 0x41e8, 0x9a, 0x78, 0x36, 0xd1, 0x10, 0xe6, 0xd2, 0xf9);  
```  
  
## <a name="remarks"></a>备注  
 自定义接口特性定义的类型库中的对象的元数据。  
  
 使用<xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType>或<xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType>可从该属性检索托管的名称。  
  
 有关详细信息，请参阅[接口属性](/cpp/windows/interface-attributes)Visual c + + 参考文档。  
  
## <a name="example"></a>示例  
 下面的示例演示库定义使用`GUID_ManagedName`属性。  
  
```  
[  
   ...  
   custom(GUID_ManagedName, Microsoft.VisualStudio.CommandBars.dll")  
]  
library Microsoft_VisualStudio_CommandBars  
{  
   ...  
}  
```  
  
## <a name="requirements"></a>要求  
 **标头：** Cor.h
