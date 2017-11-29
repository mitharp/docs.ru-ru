---
title: "Метод ICorDebugThread::GetActiveChain"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.GetActiveChain
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::GetActiveChain
helpviewer_keywords:
- ICorDebugThread::GetActiveChain method [.NET Framework debugging]
- GetActiveChain method [.NET Framework debugging]
ms.assetid: f50de1f7-40ef-4949-b542-1d9a61f7bfef
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f3f104933bc70682a531c0853cfc6eabcd357831
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthreadgetactivechain-method"></a><span data-ttu-id="84c38-102">Метод ICorDebugThread::GetActiveChain</span><span class="sxs-lookup"><span data-stu-id="84c38-102">ICorDebugThread::GetActiveChain Method</span></span>
<span data-ttu-id="84c38-103">Получает указатель интерфейса активной (последней) цепи стека для этого объекта ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="84c38-103">Gets an interface pointer to the active (most recent) stack chain on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84c38-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="84c38-104">Syntax</span></span>  
  
```  
HRESULT GetActiveChain (  
    [out] ICorDebugChain **ppChain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="84c38-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="84c38-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="84c38-106">[out] Указатель на адрес объекта ICorDebugChain, который представляет цепочка стека.</span><span class="sxs-lookup"><span data-stu-id="84c38-106">[out] A pointer to the address of an ICorDebugChain object that represents the stack chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84c38-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="84c38-107">Remarks</span></span>  
 <span data-ttu-id="84c38-108">`ppChain` Параметр имеет значение null, если нет цепочка стека в данный момент активна.</span><span class="sxs-lookup"><span data-stu-id="84c38-108">The `ppChain` parameter is null if no stack chain is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84c38-109">Требования</span><span class="sxs-lookup"><span data-stu-id="84c38-109">Requirements</span></span>  
 <span data-ttu-id="84c38-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84c38-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84c38-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84c38-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84c38-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84c38-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84c38-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84c38-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>