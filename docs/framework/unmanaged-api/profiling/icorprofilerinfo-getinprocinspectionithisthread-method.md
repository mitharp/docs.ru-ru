---
title: "Метод ICorProfilerInfo::GetInprocInspectionIThisThread"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetInprocInspectionIThisThread
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetInprocInspectionIThisThread
helpviewer_keywords:
- ICorProfilerInfo::GetInprocInspectionIThisThread method [.NET Framework profiling]
- GetInprocInspectionIThisThread method [.NET Framework profiling]
ms.assetid: badddccd-f85c-416e-9f0f-419eab2c9d42
topic_type: apiref
caps.latest.revision: "20"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9a260143e36939f4201d7949f5783f80e5c20ba7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogetinprocinspectionithisthread-method"></a><span data-ttu-id="ffc43-102">Метод ICorProfilerInfo::GetInprocInspectionIThisThread</span><span class="sxs-lookup"><span data-stu-id="ffc43-102">ICorProfilerInfo::GetInprocInspectionIThisThread Method</span></span>
<span data-ttu-id="ffc43-103">Возвращает объект, который может запрашиваться для ICorDebugThread-интерфейс.</span><span class="sxs-lookup"><span data-stu-id="ffc43-103">Gets an object that can be queried for the ICorDebugThread interface.</span></span> <span data-ttu-id="ffc43-104">Этот метод является устаревшим в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="ffc43-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffc43-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ffc43-105">Syntax</span></span>  
  
```  
HRESULT GetInprocInspectionIThisThread(  
    [out] IUnknown **ppicd);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ffc43-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ffc43-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="ffc43-107">[out](/cpp/atl/iunknown) объекта, который может запрашиваться для `ICorDebugThread` интерфейса.</span><span class="sxs-lookup"><span data-stu-id="ffc43-107">[out](/cpp/atl/iunknown) object that can be queried for the `ICorDebugThread` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ffc43-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="ffc43-108">Remarks</span></span>  
 <span data-ttu-id="ffc43-109">Общеязыковой среды выполнения (CLR), службами отладки поддерживается только в процессе отладки в .NET Framework версии 1.0.</span><span class="sxs-lookup"><span data-stu-id="ffc43-109">The common language runtime (CLR) debugging services supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="ffc43-110">Внутрипроцессная отладка позволяла профилировщику использовать проверочную API отладки.</span><span class="sxs-lookup"><span data-stu-id="ffc43-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="ffc43-111">В результате отзывов клиентов внутрипроцессная отладка были удалены из .NET Framework версии 2.0 и заменена набором функциональных возможностей, которые лучше подходят для API профилирования.</span><span class="sxs-lookup"><span data-stu-id="ffc43-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffc43-112">Требования</span><span class="sxs-lookup"><span data-stu-id="ffc43-112">Requirements</span></span>  
 <span data-ttu-id="ffc43-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ffc43-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffc43-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ffc43-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ffc43-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ffc43-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ffc43-116">**Версия платформы .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="ffc43-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffc43-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ffc43-117">See Also</span></span>  
 [<span data-ttu-id="ffc43-118">ICorProfilerInfo-интерфейс</span><span class="sxs-lookup"><span data-stu-id="ffc43-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)