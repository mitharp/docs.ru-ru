---
title: "Метод EmitAssemblyCustomAttribute"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.EmitAssemblyCustomAttribute
- EmitAssemblyCustomAttribute
api_location: alink.dll
api_type: COM
f1_keywords: EmitAssemblyCustomAttribute
helpviewer_keywords: EmitAssemblyCustomAttribute method
ms.assetid: b72f5409-79af-4fa7-90a7-7630eec170f1
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bb21ee1396a9dd0426b9b91711c2345ef66c09f9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="emitassemblycustomattribute-method"></a><span data-ttu-id="50479-102">Метод EmitAssemblyCustomAttribute</span><span class="sxs-lookup"><span data-stu-id="50479-102">EmitAssemblyCustomAttribute Method</span></span>
<span data-ttu-id="50479-103">Вызов для установки настраиваемые атрибуты уровня сборки.</span><span class="sxs-lookup"><span data-stu-id="50479-103">Call to set assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50479-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="50479-104">Syntax</span></span>  
  
```  
HRESULT EmitAssemblyCustomAttribute(  
    mdAssembly   AssemblyID,  
    mdToken      FileToken,  
    mdToken      tkType,  
    void const*  pCustomValue,  
    DWORD        cbCustomValue,  
    BOOL         bSecurity,  
    BOOL         bAllowMulti  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="50479-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="50479-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="50479-106">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="50479-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="50479-107">Файл, понижающий уровень атрибута.</span><span class="sxs-lookup"><span data-stu-id="50479-107">File that defiles the attribute.</span></span> <span data-ttu-id="50479-108">Может иметь значение NULL, если `AssemblyID` не указывает на несвязанный NETMODULE-файл.</span><span class="sxs-lookup"><span data-stu-id="50479-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `tkType`  
 <span data-ttu-id="50479-109">Тип настраиваемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="50479-109">Type of the custom attribute.</span></span>  
  
 `pCustomValue`  
 <span data-ttu-id="50479-110">Пользовательские данные значения.</span><span class="sxs-lookup"><span data-stu-id="50479-110">Custom value data.</span></span>  
  
 `cbCustomValue`  
 <span data-ttu-id="50479-111">Длина пользовательских данных значения.</span><span class="sxs-lookup"><span data-stu-id="50479-111">Length of custom value data.</span></span>  
  
 `bSecurity`  
 <span data-ttu-id="50479-112">Значение TRUE, если пользовательский атрибут имеет отношение к подписи сборки.</span><span class="sxs-lookup"><span data-stu-id="50479-112">TRUE if the custom attribute is related to assembly signing.</span></span>  
  
 `bAllowMulti`  
 <span data-ttu-id="50479-113">Значение TRUE, если несколько атрибутов, которые должны быть созданы.</span><span class="sxs-lookup"><span data-stu-id="50479-113">TRUE if multiple attributes are to be emitted.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="50479-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="50479-114">Return Value</span></span>  
 <span data-ttu-id="50479-115">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="50479-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50479-116">Требования</span><span class="sxs-lookup"><span data-stu-id="50479-116">Requirements</span></span>  
 <span data-ttu-id="50479-117">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="50479-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50479-118">См. также</span><span class="sxs-lookup"><span data-stu-id="50479-118">See Also</span></span>  
 [<span data-ttu-id="50479-119">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="50479-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="50479-120">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="50479-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="50479-121">ALink-интерфейс API</span><span class="sxs-lookup"><span data-stu-id="50479-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)