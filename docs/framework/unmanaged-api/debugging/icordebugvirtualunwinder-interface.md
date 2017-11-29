---
title: "Интерфейс ICorDebugVirtualUnwinder"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a09e9ccc-0b37-43e3-95c1-bc5fa7ee5f42
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d22fa926b300384b7f790468b1b3d0becafdb942
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvirtualunwinder-interface"></a><span data-ttu-id="1da55-102">Интерфейс ICorDebugVirtualUnwinder</span><span class="sxs-lookup"><span data-stu-id="1da55-102">ICorDebugVirtualUnwinder Interface</span></span>
<span data-ttu-id="1da55-103">Предоставляет методы, помогающие очистить стек.</span><span class="sxs-lookup"><span data-stu-id="1da55-103">Provides methods to help in stack unwinding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1da55-104">Методы</span><span class="sxs-lookup"><span data-stu-id="1da55-104">Methods</span></span>  
  
|<span data-ttu-id="1da55-105">Метод</span><span class="sxs-lookup"><span data-stu-id="1da55-105">Method</span></span>|<span data-ttu-id="1da55-106">Имя</span><span class="sxs-lookup"><span data-stu-id="1da55-106">Name</span></span>|  
|------------|----------|  
|[<span data-ttu-id="1da55-107">Метод GetContext</span><span class="sxs-lookup"><span data-stu-id="1da55-107">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-getcontext-method.md)|<span data-ttu-id="1da55-108">Получает текущий контекст этого средства очистки.</span><span class="sxs-lookup"><span data-stu-id="1da55-108">Gets the current context of this unwinder.</span></span>|  
|[<span data-ttu-id="1da55-109">Метод Next</span><span class="sxs-lookup"><span data-stu-id="1da55-109">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-next-method.md)|<span data-ttu-id="1da55-110">Переходит в контекст вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="1da55-110">Advances to the caller's context.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1da55-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="1da55-111">Remarks</span></span>  
 <span data-ttu-id="1da55-112">Элементы интерфейса `ICorDebugVirtualUnwinder` реализуются отладчиком для упрощения очистки стека.</span><span class="sxs-lookup"><span data-stu-id="1da55-112">The members of the `ICorDebugVirtualUnwinder` interface are implemented by the debugger to help in stack unwinding.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1da55-113">Этот интерфейс доступен только в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="1da55-113">This interface is available with .NET Native only.</span></span> <span data-ttu-id="1da55-114">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="1da55-114">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1da55-115">Требования</span><span class="sxs-lookup"><span data-stu-id="1da55-115">Requirements</span></span>  
 <span data-ttu-id="1da55-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1da55-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1da55-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1da55-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1da55-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1da55-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1da55-119">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1da55-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1da55-120">См. также</span><span class="sxs-lookup"><span data-stu-id="1da55-120">See Also</span></span>  
 [<span data-ttu-id="1da55-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="1da55-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="1da55-122">Отладка</span><span class="sxs-lookup"><span data-stu-id="1da55-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)