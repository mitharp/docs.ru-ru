---
title: "Метод GetWin32ResBlob"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.GetWin32ResBlob
api_location: alink.dll
api_type: COM
f1_keywords: GetWin32ResBlob
helpviewer_keywords: GetWin32ResBlob method
ms.assetid: 36997e04-f9f6-4254-a041-6767ac6c51d9
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9c4456757c56440463010d4adc3d3eed90dbc07a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="getwin32resblob-method"></a><span data-ttu-id="b3579-102">Метод GetWin32ResBlob</span><span class="sxs-lookup"><span data-stu-id="b3579-102">GetWin32ResBlob Method</span></span>
<span data-ttu-id="b3579-103">Извлекает большой двоичный объект ресурсов Win32.</span><span class="sxs-lookup"><span data-stu-id="b3579-103">Retrieves Win32 resource blob.</span></span> <span data-ttu-id="b3579-104">Этот метод вызывается после задания параметров сборки.</span><span class="sxs-lookup"><span data-stu-id="b3579-104">Call this method after setting assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3579-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b3579-105">Syntax</span></span>  
  
```  
HRESULT GetWin32ResBlob(  
    mdAssembly    AssemblyID,  
    mdToken       FileToken,  
    BOOL          fDll,  
    LPCWSTR       pszIconFile,  
    const void**  ppResBlob,  
    DWORD*        pcbResBlob  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b3579-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b3579-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="b3579-107">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="b3579-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="b3579-108">Маркер файла, используемый для извлечения имени файла для использования при создании ресурса версии Win32.</span><span class="sxs-lookup"><span data-stu-id="b3579-108">File token used to retrieve the filename to be used when constructing the Win32 Version resource</span></span>  
  
 `fDll`  
 <span data-ttu-id="b3579-109">Значение TRUE, если файл является библиотекой DLL, false для EXE-файла.</span><span class="sxs-lookup"><span data-stu-id="b3579-109">TRUE if file is a DLL, false for an EXE.</span></span>  
  
 `pszIconFile`  
 <span data-ttu-id="b3579-110">Необязательный значок, вставляемый в большой двоичный объект ресурсов.</span><span class="sxs-lookup"><span data-stu-id="b3579-110">Optional icon to insert into the resource blob.</span></span>  
  
 `ppResBlob`  
 <span data-ttu-id="b3579-111">Получает ресурс большого двоичного объекта.</span><span class="sxs-lookup"><span data-stu-id="b3579-111">Receives the resource blob.</span></span>  
  
 `pcbResBlob`  
 <span data-ttu-id="b3579-112">Получает размер большого двоичного объекта.</span><span class="sxs-lookup"><span data-stu-id="b3579-112">Receives the size of the blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b3579-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b3579-113">Return Value</span></span>  
 <span data-ttu-id="b3579-114">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="b3579-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3579-115">Требования</span><span class="sxs-lookup"><span data-stu-id="b3579-115">Requirements</span></span>  
 <span data-ttu-id="b3579-116">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="b3579-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3579-117">См. также</span><span class="sxs-lookup"><span data-stu-id="b3579-117">See Also</span></span>  
 [<span data-ttu-id="b3579-118">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="b3579-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="b3579-119">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="b3579-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="b3579-120">ALink-интерфейс API</span><span class="sxs-lookup"><span data-stu-id="b3579-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)