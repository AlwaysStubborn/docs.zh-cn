---
title: "TypeNameFactory 组件类"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: TypeNameFactory Coclass
api_location: mscoree.dll
api_type: COM
f1_keywords: TypeNameFactory
helpviewer_keywords: TypeNameFactory coclass [.NET Framework hosting]
ms.assetid: c853bb58-c9c5-476b-8e80-608aa53ea18d
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c02445a7a46bd9367b84edcf5ef5f012be5232e5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="typenamefactory-coclass"></a><span data-ttu-id="34fe1-102">TypeNameFactory 组件类</span><span class="sxs-lookup"><span data-stu-id="34fe1-102">TypeNameFactory Coclass</span></span>
<span data-ttu-id="34fe1-103">提供用于管理析构的类型名称的接口。</span><span class="sxs-lookup"><span data-stu-id="34fe1-103">Provides an interface for managing the deconstruction of a type name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34fe1-104">语法</span><span class="sxs-lookup"><span data-stu-id="34fe1-104">Syntax</span></span>  
  
```  
coclass TypeNameFactory {  
    [default] interface ITypeNameFactory;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="34fe1-105">接口</span><span class="sxs-lookup"><span data-stu-id="34fe1-105">Interfaces</span></span>  
  
|<span data-ttu-id="34fe1-106">接口</span><span class="sxs-lookup"><span data-stu-id="34fe1-106">Interface</span></span>|<span data-ttu-id="34fe1-107">描述</span><span class="sxs-lookup"><span data-stu-id="34fe1-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="34fe1-108">ITypeNameFactory 接口</span><span class="sxs-lookup"><span data-stu-id="34fe1-108">ITypeNameFactory Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypenamefactory-interface.md)|<span data-ttu-id="34fe1-109">此接口支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="34fe1-109">This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="34fe1-110">要求</span><span class="sxs-lookup"><span data-stu-id="34fe1-110">Requirements</span></span>  
 <span data-ttu-id="34fe1-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="34fe1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34fe1-112">**标头：** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="34fe1-112">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="34fe1-113">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="34fe1-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="34fe1-114">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34fe1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34fe1-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34fe1-115">See Also</span></span>  
 [<span data-ttu-id="34fe1-116">承载组件类</span><span class="sxs-lookup"><span data-stu-id="34fe1-116">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)