---
title: "Метод ICLRTask::YieldTask"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.YieldTask
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::YieldTask
helpviewer_keywords:
- ICLRTask::YieldTask method [.NET Framework hosting]
- YieldTask method [.NET Framework hosting]
ms.assetid: b8eb4095-3a8f-4be3-9446-63e9893dce7d
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6a02a69329958593aec546ca9c60e3d201ce2a92
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskyieldtask-method"></a><span data-ttu-id="e88c2-102">Метод ICLRTask::YieldTask</span><span class="sxs-lookup"><span data-stu-id="e88c2-102">ICLRTask::YieldTask Method</span></span>
<span data-ttu-id="e88c2-103">Запросы, что общеязыковой среды выполнения (CLR) отложить задачу, текущий [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) представляет экземпляр и сделать доступным для других задач процессорного времени.</span><span class="sxs-lookup"><span data-stu-id="e88c2-103">Requests that the common language runtime (CLR) put aside the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents, and make the processor time available to other tasks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e88c2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e88c2-104">Syntax</span></span>  
  
```  
HRESULT YieldTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e88c2-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e88c2-105">Return Value</span></span>  
  
|<span data-ttu-id="e88c2-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e88c2-106">HRESULT</span></span>|<span data-ttu-id="e88c2-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e88c2-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e88c2-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="e88c2-108">S_OK</span></span>|<span data-ttu-id="e88c2-109">`YieldTask`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="e88c2-109">`YieldTask` returned successfully.</span></span>|  
|<span data-ttu-id="e88c2-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e88c2-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e88c2-111">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="e88c2-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e88c2-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e88c2-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e88c2-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="e88c2-113">The call timed out.</span></span>|  
|<span data-ttu-id="e88c2-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e88c2-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e88c2-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="e88c2-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e88c2-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e88c2-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e88c2-117">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="e88c2-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e88c2-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e88c2-118">E_FAIL</span></span>|<span data-ttu-id="e88c2-119">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="e88c2-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e88c2-120">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="e88c2-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e88c2-121">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e88c2-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e88c2-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="e88c2-122">Remarks</span></span>  
 <span data-ttu-id="e88c2-123">Узел вызывает `YieldTask` для запроса ресурсов процессора для других задач или процессов.</span><span class="sxs-lookup"><span data-stu-id="e88c2-123">A host calls `YieldTask` to request processor resources for other tasks or processes.</span></span> <span data-ttu-id="e88c2-124">Этот метод в основном предназначен для предоставления времени ЦП долго выполняющихся кодом.</span><span class="sxs-lookup"><span data-stu-id="e88c2-124">This method is primarily intended to allow long-running code to give up CPU time.</span></span> <span data-ttu-id="e88c2-125">Среда выполнения пытается перевести задачу, текущий `ICLRTask` представляет экземпляр в состоянии, где его сможет выделить время обработки, но не гарантирует успешности.</span><span class="sxs-lookup"><span data-stu-id="e88c2-125">The runtime attempts to put the task that the current `ICLRTask` instance represents in a state where it can yield processing time, but makes no guarantee of success.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e88c2-126">Требования</span><span class="sxs-lookup"><span data-stu-id="e88c2-126">Requirements</span></span>  
 <span data-ttu-id="e88c2-127">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e88c2-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e88c2-128">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e88c2-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e88c2-129">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e88c2-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e88c2-130">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e88c2-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e88c2-131">См. также</span><span class="sxs-lookup"><span data-stu-id="e88c2-131">See Also</span></span>  
 [<span data-ttu-id="e88c2-132">ICLRTask-интерфейс</span><span class="sxs-lookup"><span data-stu-id="e88c2-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="e88c2-133">ICLRTaskManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="e88c2-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="e88c2-134">IHostTask-интерфейс</span><span class="sxs-lookup"><span data-stu-id="e88c2-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="e88c2-135">IHostTaskManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="e88c2-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)