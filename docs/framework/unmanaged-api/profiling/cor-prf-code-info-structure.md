---
title: "Структура COR_PRF_CODE_INFO"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_CODE_INFO
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_CODE_INFO
helpviewer_keywords: COR_PRF_CODE_INFO structure [.NET Framework profiling]
ms.assetid: cf30e27c-1f7e-43a2-ba1e-01e4137301db
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 007bb5990ec750dccc678a208d755136ea67a05c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="corprfcodeinfo-structure"></a><span data-ttu-id="14c85-102">Структура COR_PRF_CODE_INFO</span><span class="sxs-lookup"><span data-stu-id="14c85-102">COR_PRF_CODE_INFO Structure</span></span>
<span data-ttu-id="14c85-103">Представляет один непрерывный блок машинного кода, хранящийся в памяти.</span><span class="sxs-lookup"><span data-stu-id="14c85-103">Represents one contiguous block of native code stored in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14c85-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="14c85-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_CODE_INFO {  
    UINT_PTR startAddress;  
    SIZE_T size;  
} COR_PRF_CODE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="14c85-105">Члены</span><span class="sxs-lookup"><span data-stu-id="14c85-105">Members</span></span>  
  
|<span data-ttu-id="14c85-106">Член</span><span class="sxs-lookup"><span data-stu-id="14c85-106">Member</span></span>|<span data-ttu-id="14c85-107">Описание</span><span class="sxs-lookup"><span data-stu-id="14c85-107">Description</span></span>|  
|------------|-----------------|  
|`startAddress`|<span data-ttu-id="14c85-108">Начальный адрес непрерывного блока кода.</span><span class="sxs-lookup"><span data-stu-id="14c85-108">The starting address of the contiguous block of code.</span></span>|  
|`size`|<span data-ttu-id="14c85-109">Размер блока.</span><span class="sxs-lookup"><span data-stu-id="14c85-109">The size of the block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="14c85-110">Требования</span><span class="sxs-lookup"><span data-stu-id="14c85-110">Requirements</span></span>  
 <span data-ttu-id="14c85-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14c85-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14c85-112">**Заголовок:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="14c85-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="14c85-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14c85-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14c85-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14c85-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14c85-115">См. также</span><span class="sxs-lookup"><span data-stu-id="14c85-115">See Also</span></span>  
 [<span data-ttu-id="14c85-116">Структуры профилирования</span><span class="sxs-lookup"><span data-stu-id="14c85-116">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)