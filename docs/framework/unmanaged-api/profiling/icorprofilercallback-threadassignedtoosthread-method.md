---
title: "Метод ICorProfilerCallback::ThreadAssignedToOSThread"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ThreadAssignedToOSThread
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ThreadAssignedToOSThread
helpviewer_keywords:
- ThreadAssignedToOSThread method [.NET Framework profiling]
- ICorProfilerCallback::ThreadAssignedToOSThread method [.NET Framework profiling]
ms.assetid: f9671e5a-7b14-4f5b-8404-58136422c8b2
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c70de2b53fd428361d5404aa406d2b2be67d0914
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackthreadassignedtoosthread-method"></a><span data-ttu-id="bd314-102">Метод ICorProfilerCallback::ThreadAssignedToOSThread</span><span class="sxs-lookup"><span data-stu-id="bd314-102">ICorProfilerCallback::ThreadAssignedToOSThread Method</span></span>
<span data-ttu-id="bd314-103">Уведомляет профилировщик о том, что управляемый поток реализуется с использованием определенного потока операционной системы.</span><span class="sxs-lookup"><span data-stu-id="bd314-103">Notifies the profiler that a managed thread is being implemented using a particular operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd314-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bd314-104">Syntax</span></span>  
  
```  
HRESULT ThreadAssignedToOSThread(  
    [in] ThreadID managedThreadId,  
    [in] DWORD    osThreadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bd314-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bd314-105">Parameters</span></span>  
 `managedThreadId`  
 <span data-ttu-id="bd314-106">[in] Идентификатор управляемого потока.</span><span class="sxs-lookup"><span data-stu-id="bd314-106">[in] The identifier of the managed thread.</span></span>  
  
 `osThreadId`  
 <span data-ttu-id="bd314-107">[in] Идентификатор потока операционной системы.</span><span class="sxs-lookup"><span data-stu-id="bd314-107">[in] The identifier of the operating system thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd314-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="bd314-108">Remarks</span></span>  
 <span data-ttu-id="bd314-109">`ThreadAssignedToOSThread` Имеется обратного вызова, что профилировщик может поддерживать точное сопоставление между волокна потоков операционной системы в управляемые потоки.</span><span class="sxs-lookup"><span data-stu-id="bd314-109">The `ThreadAssignedToOSThread` callback exists so that the profiler can maintain an accurate mapping across fibers of operating system threads to managed threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd314-110">Требования</span><span class="sxs-lookup"><span data-stu-id="bd314-110">Requirements</span></span>  
 <span data-ttu-id="bd314-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd314-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd314-112">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bd314-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bd314-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd314-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd314-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd314-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd314-115">См. также</span><span class="sxs-lookup"><span data-stu-id="bd314-115">See Also</span></span>  
 [<span data-ttu-id="bd314-116">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="bd314-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)