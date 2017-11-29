---
title: "ISymUnmanagedWriter4 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f7ab7f06ba280675ca8349500e766364d30f9349
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriter4-interface"></a><span data-ttu-id="f6951-102">ISymUnmanagedWriter4 接口</span><span class="sxs-lookup"><span data-stu-id="f6951-102">ISymUnmanagedWriter4 Interface</span></span>
<span data-ttu-id="f6951-103">ISymUnmanagedWriter4 接口。</span><span class="sxs-lookup"><span data-stu-id="f6951-103">ISymUnmanagedWriter4 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6951-104">语法</span><span class="sxs-lookup"><span data-stu-id="f6951-104">Syntax</span></span>  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a><span data-ttu-id="f6951-105">方法</span><span class="sxs-lookup"><span data-stu-id="f6951-105">Methods</span></span>  
 <span data-ttu-id="f6951-106">此接口包含下列方法：</span><span class="sxs-lookup"><span data-stu-id="f6951-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="f6951-107">方法</span><span class="sxs-lookup"><span data-stu-id="f6951-107">Method</span></span>|<span data-ttu-id="f6951-108">描述</span><span class="sxs-lookup"><span data-stu-id="f6951-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f6951-109">GetDebugInfoWithPadding 方法</span><span class="sxs-lookup"><span data-stu-id="f6951-109">GetDebugInfoWithPadding Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-getdebuginfowithpadding-method.md)|<span data-ttu-id="f6951-110">函数与相同[GetDebugInfo 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md)只不过用终止的 null 字符，以使的固定的大小的字符串数据后面的零填充的路径字符串`MAX_PATH`。</span><span class="sxs-lookup"><span data-stu-id="f6951-110">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="f6951-111">填充仅有自身的路径字符串长度是否小于`MAX_PATH`。</span><span class="sxs-lookup"><span data-stu-id="f6951-111">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span><br /><br /> <span data-ttu-id="f6951-112">这会使易于编写该差异 PE 文件的工具。</span><span class="sxs-lookup"><span data-stu-id="f6951-112">This makes it easier to write tools that difference PE files.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f6951-113">要求</span><span class="sxs-lookup"><span data-stu-id="f6951-113">Requirements</span></span>  
 <span data-ttu-id="f6951-114">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f6951-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6951-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f6951-115">See Also</span></span>  
 [<span data-ttu-id="f6951-116">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="f6951-116">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="f6951-117">ISymUnmanagedWriter3 接口</span><span class="sxs-lookup"><span data-stu-id="f6951-117">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)