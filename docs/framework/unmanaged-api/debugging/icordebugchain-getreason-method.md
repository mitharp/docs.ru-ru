---
title: "Метод ICorDebugChain::GetReason"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugChain.GetReason
api_location: mscordbi.dll
api_type: COM
f1_keywords: GetReason
helpviewer_keywords:
- GetReason method [.NET Framework debugging]
- ICorDebugChain::GetReason method [.NET Framework debugging]
ms.assetid: 9f9f62b9-113a-4a98-8f9b-b593cef27b03
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7f0543f31c7b0e5d51f2b12f589ce6dce8552405
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugchaingetreason-method"></a><span data-ttu-id="eddd8-102">Метод ICorDebugChain::GetReason</span><span class="sxs-lookup"><span data-stu-id="eddd8-102">ICorDebugChain::GetReason Method</span></span>
<span data-ttu-id="eddd8-103">Возвращает причину происхождения данной вызывающей цепи.</span><span class="sxs-lookup"><span data-stu-id="eddd8-103">Gets the reason for the genesis of this calling chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eddd8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eddd8-104">Syntax</span></span>  
  
```  
HRESULT GetReason (  
    [out] CorDebugChainReason *pReason  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eddd8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="eddd8-105">Parameters</span></span>  
 `pReason`  
 <span data-ttu-id="eddd8-106">[out] Указатель на значение (побитовое сочетание) CorDebugChainReason перечисления, указывающее причину происхождения данной вызывающей цепи.</span><span class="sxs-lookup"><span data-stu-id="eddd8-106">[out] A pointer to a value (a bitwise combination) of the CorDebugChainReason enumeration that indicates the reason for the genesis of this calling chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eddd8-107">Требования</span><span class="sxs-lookup"><span data-stu-id="eddd8-107">Requirements</span></span>  
 <span data-ttu-id="eddd8-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eddd8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eddd8-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eddd8-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eddd8-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eddd8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eddd8-111">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eddd8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>