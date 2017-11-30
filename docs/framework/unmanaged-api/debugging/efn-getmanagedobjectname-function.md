---
title: "Функция _EFN_GetManagedObjectName"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _EFN_GetManagedObjectName
api_location: mscordbi.dll
api_type: COM
f1_keywords: _EFN_GetManagedObjectName
helpviewer_keywords: _EFN_GetManagedObjectName function [.NET Framework debugging]
ms.assetid: 6e7c6bee-7ced-495f-bf6c-2a5f0c716f7e
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 80e36f6c60c4c305cad9176cd7f185d8b6d2fdf2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="efngetmanagedobjectname-function"></a><span data-ttu-id="306e4-102">Функция _EFN_GetManagedObjectName</span><span class="sxs-lookup"><span data-stu-id="306e4-102">_EFN_GetManagedObjectName Function</span></span>
<span data-ttu-id="306e4-103">Возвращает имя типа с помощью предоставленного указателя управляемого объекта.</span><span class="sxs-lookup"><span data-stu-id="306e4-103">Gets the name of a type using the provided managed object pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="306e4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="306e4-104">Syntax</span></span>  
  
```  
HRESULT _EFN_GetManagedObjectName(  
    [in]  PDEBUG_CLIENT  Client,  
    [in]  ULONG64        objAddr,  
    [out] __out_ecount(cbName) PSTR szName,  
    [out] ULONG          cbName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="306e4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="306e4-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="306e4-106">[in] Указатель на клиенте отладки.</span><span class="sxs-lookup"><span data-stu-id="306e4-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="306e4-107">[in] Указатель на управляемый объект.</span><span class="sxs-lookup"><span data-stu-id="306e4-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="306e4-108">szName</span><span class="sxs-lookup"><span data-stu-id="306e4-108">szName</span></span>  
 <span data-ttu-id="306e4-109">[out] Имя типа.</span><span class="sxs-lookup"><span data-stu-id="306e4-109">[out] The name of the type.</span></span>  
  
 `cbName`  
 <span data-ttu-id="306e4-110">[out] Число символов в буфере строки.</span><span class="sxs-lookup"><span data-stu-id="306e4-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="306e4-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="306e4-111">Remarks</span></span>  
 <span data-ttu-id="306e4-112">Если нет управляемого кода в потоке в данный момент в контексте, функция возвращает значение HRESULT SOS_E_NOMANAGEDCODE со значением устройства 0xa0 и кодом ошибки 0x1000.</span><span class="sxs-lookup"><span data-stu-id="306e4-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="306e4-113">Требования</span><span class="sxs-lookup"><span data-stu-id="306e4-113">Requirements</span></span>  
 <span data-ttu-id="306e4-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="306e4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="306e4-115">**Заголовок:** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="306e4-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="306e4-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="306e4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="306e4-117">См. также</span><span class="sxs-lookup"><span data-stu-id="306e4-117">See Also</span></span>  
 [<span data-ttu-id="306e4-118">Глобальные статические функции отладки</span><span class="sxs-lookup"><span data-stu-id="306e4-118">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)