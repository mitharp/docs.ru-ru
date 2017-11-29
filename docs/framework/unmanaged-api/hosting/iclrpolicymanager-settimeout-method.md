---
title: "Метод ICLRPolicyManager::SetTimeout"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRPolicyManager.SetTimeout
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRPolicyManager::SetTimeout
helpviewer_keywords:
- SetTimeout method [.NET Framework hosting]
- ICLRPolicyManager::SetTimeout method [.NET Framework hosting]
ms.assetid: 954404fd-d52d-4e68-b582-8692f3a5f608
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 31dfd4654f849d01958be2690afed0f31c736dfd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrpolicymanagersettimeout-method"></a><span data-ttu-id="f4a07-102">Метод ICLRPolicyManager::SetTimeout</span><span class="sxs-lookup"><span data-stu-id="f4a07-102">ICLRPolicyManager::SetTimeout Method</span></span>
<span data-ttu-id="f4a07-103">Задает значение времени ожидания для указанной операции.</span><span class="sxs-lookup"><span data-stu-id="f4a07-103">Sets a timeout value for the specified operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4a07-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f4a07-104">Syntax</span></span>  
  
```  
HRESULT SetTimeout (  
    [in] EClrOperation operation,  
    [in] DWORD dsMilliseconds  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f4a07-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f4a07-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="f4a07-106">[in] Один из [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) значения, указывает, что операция среды выполнения (CLR) общий язык, для которого требуется задать время ожидания.</span><span class="sxs-lookup"><span data-stu-id="f4a07-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the common language runtime (CLR) operation for which to set a timeout.</span></span> <span data-ttu-id="f4a07-107">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="f4a07-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="f4a07-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="f4a07-108">OPR_AppDomainUnload</span></span>  
  
-   <span data-ttu-id="f4a07-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="f4a07-109">OPR_ProcessExit</span></span>  
  
-   <span data-ttu-id="f4a07-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="f4a07-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
-   <span data-ttu-id="f4a07-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="f4a07-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="f4a07-112">[in] Новое значение времени ожидания в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="f4a07-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="f4a07-113">Значение INFINITE вызывает операции никогда не времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="f4a07-113">A value of INFINITE causes the operation never to time out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f4a07-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f4a07-114">Return Value</span></span>  
  
|<span data-ttu-id="f4a07-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f4a07-115">HRESULT</span></span>|<span data-ttu-id="f4a07-116">Описание</span><span class="sxs-lookup"><span data-stu-id="f4a07-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f4a07-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="f4a07-117">S_OK</span></span>|<span data-ttu-id="f4a07-118">`SetTimeout`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="f4a07-118">`SetTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="f4a07-119">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f4a07-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f4a07-120">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="f4a07-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f4a07-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f4a07-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f4a07-122">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="f4a07-122">The call timed out.</span></span>|  
|<span data-ttu-id="f4a07-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f4a07-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f4a07-124">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="f4a07-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f4a07-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f4a07-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f4a07-126">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="f4a07-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f4a07-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f4a07-127">E_FAIL</span></span>|<span data-ttu-id="f4a07-128">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="f4a07-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f4a07-129">После метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="f4a07-129">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f4a07-130">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f4a07-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f4a07-131">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f4a07-131">E_INVALIDARG</span></span>|<span data-ttu-id="f4a07-132">Невозможно задать время ожидания для указанного `operation`, или было задано недопустимое значение для `operation`.</span><span class="sxs-lookup"><span data-stu-id="f4a07-132">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f4a07-133">Требования</span><span class="sxs-lookup"><span data-stu-id="f4a07-133">Requirements</span></span>  
 <span data-ttu-id="f4a07-134">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4a07-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4a07-135">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f4a07-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f4a07-136">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f4a07-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f4a07-137">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4a07-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4a07-138">См. также</span><span class="sxs-lookup"><span data-stu-id="f4a07-138">See Also</span></span>  
 [<span data-ttu-id="f4a07-139">EClrOperation-перечисление</span><span class="sxs-lookup"><span data-stu-id="f4a07-139">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="f4a07-140">ICLRControl-интерфейс</span><span class="sxs-lookup"><span data-stu-id="f4a07-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="f4a07-141">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="f4a07-141">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)