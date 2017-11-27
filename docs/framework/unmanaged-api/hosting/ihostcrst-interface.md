---
title: "IHostCrst 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostCrst
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostCrst
helpviewer_keywords: IHostCrst interface [.NET Framework hosting]
ms.assetid: ac298ebd-0815-47e4-a823-30b31baab903
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 59485d7a642ba8b3233d5d077062e89fb2ac9b14
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ihostcrst-interface"></a><span data-ttu-id="13221-102">IHostCrst 接口</span><span class="sxs-lookup"><span data-stu-id="13221-102">IHostCrst Interface</span></span>
<span data-ttu-id="13221-103">用作主机的表示形式的线程处理关键部分。</span><span class="sxs-lookup"><span data-stu-id="13221-103">Serves as the host's representation of a critical section for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="13221-104">方法</span><span class="sxs-lookup"><span data-stu-id="13221-104">Methods</span></span>  
  
|<span data-ttu-id="13221-105">方法</span><span class="sxs-lookup"><span data-stu-id="13221-105">Method</span></span>|<span data-ttu-id="13221-106">描述</span><span class="sxs-lookup"><span data-stu-id="13221-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="13221-107">Enter 方法</span><span class="sxs-lookup"><span data-stu-id="13221-107">Enter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|<span data-ttu-id="13221-108">进入临界区。</span><span class="sxs-lookup"><span data-stu-id="13221-108">Enters the critical section.</span></span>|  
|[<span data-ttu-id="13221-109">Leave 方法</span><span class="sxs-lookup"><span data-stu-id="13221-109">Leave Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|<span data-ttu-id="13221-110">离开临界区。</span><span class="sxs-lookup"><span data-stu-id="13221-110">Leaves the critical section.</span></span>|  
|[<span data-ttu-id="13221-111">SetSpinCount 方法</span><span class="sxs-lookup"><span data-stu-id="13221-111">SetSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|<span data-ttu-id="13221-112">设置临界区的重试次数。</span><span class="sxs-lookup"><span data-stu-id="13221-112">Sets the spin count for the critical section.</span></span>|  
|[<span data-ttu-id="13221-113">TryEnter 方法</span><span class="sxs-lookup"><span data-stu-id="13221-113">TryEnter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|<span data-ttu-id="13221-114">若要立即输入关键部分中，以及报告是成功还是失败的尝试。</span><span class="sxs-lookup"><span data-stu-id="13221-114">Attempts to enter the critical section, and reports success or failure immediately.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13221-115">备注</span><span class="sxs-lookup"><span data-stu-id="13221-115">Remarks</span></span>  
 <span data-ttu-id="13221-116">`IHostCrst`允许公共语言运行时 (CLR) 与主机的表示形式关键部分，直接进行通信，而不是如使用 Win32 函数`EnterCriticalSection`或`LeaveCriticalSection`。</span><span class="sxs-lookup"><span data-stu-id="13221-116">`IHostCrst` allows the common language runtime (CLR) to communicate directly with the host's representation of a critical section, rather than using Win32 functions such as `EnterCriticalSection` or `LeaveCriticalSection`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13221-117">要求</span><span class="sxs-lookup"><span data-stu-id="13221-117">Requirements</span></span>  
 <span data-ttu-id="13221-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="13221-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13221-119">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="13221-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="13221-120">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="13221-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="13221-121">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13221-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13221-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="13221-122">See Also</span></span>  
 [<span data-ttu-id="13221-123">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="13221-123">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="13221-124">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="13221-124">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="13221-125">承载接口</span><span class="sxs-lookup"><span data-stu-id="13221-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)