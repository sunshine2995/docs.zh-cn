---
title: "ICorProfilerCallback::ThreadCreated 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ThreadCreated
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ThreadCreated
helpviewer_keywords:
- ICorProfilerCallback::ThreadCreated method [.NET Framework profiling]
- ThreadCreated method [.NET Framework profiling]
ms.assetid: cca0f799-09b8-4689-a33c-6d6537943a9b
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b62d5d1129bb71a95ac4e98624558272b08f0683
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackthreadcreated-method"></a><span data-ttu-id="f5ead-102">ICorProfilerCallback::ThreadCreated 方法</span><span class="sxs-lookup"><span data-stu-id="f5ead-102">ICorProfilerCallback::ThreadCreated Method</span></span>
<span data-ttu-id="f5ead-103">通知探查器已创建线程。</span><span class="sxs-lookup"><span data-stu-id="f5ead-103">Notifies the profiler that a thread has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5ead-104">语法</span><span class="sxs-lookup"><span data-stu-id="f5ead-104">Syntax</span></span>  
  
```  
HRESULT ThreadCreated(  
    [in] ThreadID threadId);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="f5ead-105">参数</span><span class="sxs-lookup"><span data-stu-id="f5ead-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="f5ead-106">[in]已创建线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="f5ead-106">[in] The ID of the thread that has been created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5ead-107">备注</span><span class="sxs-lookup"><span data-stu-id="f5ead-107">Remarks</span></span>  
 <span data-ttu-id="f5ead-108">`threadId`值是否立即有效。</span><span class="sxs-lookup"><span data-stu-id="f5ead-108">The `threadId` value is immediately valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5ead-109">要求</span><span class="sxs-lookup"><span data-stu-id="f5ead-109">Requirements</span></span>  
 <span data-ttu-id="f5ead-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f5ead-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5ead-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f5ead-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f5ead-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5ead-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5ead-113">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5ead-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5ead-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f5ead-114">See Also</span></span>  
 [<span data-ttu-id="f5ead-115">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="f5ead-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="f5ead-116">ThreadDestroyed 方法</span><span class="sxs-lookup"><span data-stu-id="f5ead-116">ThreadDestroyed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)