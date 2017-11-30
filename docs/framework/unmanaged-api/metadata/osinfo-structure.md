---
title: "Структура OSINFO"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: OSINFO
api_location: mscoree.dll
api_type: COM
f1_keywords: OSINFO
helpviewer_keywords: OSINFO structure [.NET Framework metadata]
ms.assetid: fac7b480-7adb-4450-a5e9-690fed81ffae
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 700e9bcfe33e5be3725bd24b212b3a77ad139b2c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="osinfo-structure"></a><span data-ttu-id="4b816-102">Структура OSINFO</span><span class="sxs-lookup"><span data-stu-id="4b816-102">OSINFO Structure</span></span>
<span data-ttu-id="4b816-103">Содержит сведения об операционной системе для сборки или модуля.</span><span class="sxs-lookup"><span data-stu-id="4b816-103">Contains details about the operating system for an assembly or module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b816-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4b816-104">Syntax</span></span>  
  
```  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;   
    DWORD   dwOSMinorVersion;   
} OSINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="4b816-105">Члены</span><span class="sxs-lookup"><span data-stu-id="4b816-105">Members</span></span>  
  
|<span data-ttu-id="4b816-106">Член</span><span class="sxs-lookup"><span data-stu-id="4b816-106">Member</span></span>|<span data-ttu-id="4b816-107">Описание</span><span class="sxs-lookup"><span data-stu-id="4b816-107">Description</span></span>|  
|------------|-----------------|  
|`dwOSPlatformId`|<span data-ttu-id="4b816-108">Одно из значений идентификаторов, определенные функцией платформы Microsoft Windows `GetVersionEx`.</span><span class="sxs-lookup"><span data-stu-id="4b816-108">One of the identifier values defined by the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="4b816-109">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="4b816-109">The following values are supported:</span></span><br /><br /> <span data-ttu-id="4b816-110">-VER_PLATFORM_WIN32s, или 0x0000, чтобы указать Microsoft Windows версии 3.1.</span><span class="sxs-lookup"><span data-stu-id="4b816-110">-   VER_PLATFORM_WIN32s, or 0x0000, to specify Microsoft Windows 3.1.</span></span><br /><span data-ttu-id="4b816-111">-VER_PLATFORM_WIN32_WINDOWS, или 0x0001, чтобы указать Windows 95, Windows 98 или потомками их операционных систем.</span><span class="sxs-lookup"><span data-stu-id="4b816-111">-   VER_PLATFORM_WIN32_WINDOWS, or 0x0001, to specify Windows 95, Windows 98, or operating systems descended from them.</span></span><br /><span data-ttu-id="4b816-112">-VER_PLATFORM_WIN32_NT, или 0x0010, чтобы указать Windows NT или операционными системами, его потомками.</span><span class="sxs-lookup"><span data-stu-id="4b816-112">-   VER_PLATFORM_WIN32_NT, or 0x0010, to specify Windows NT or operating systems descended from it.</span></span>|  
|`dwOSMajorVersion`|<span data-ttu-id="4b816-113">Основной номер версии операционной системы, или значение NULL для указания любой версии.</span><span class="sxs-lookup"><span data-stu-id="4b816-113">The operating system major version, or a NULL value to indicate any version.</span></span>|  
|`dwOSMinorVersion`|<span data-ttu-id="4b816-114">Дополнительный номер версии операционной системы, или значение NULL для указания любой версии.</span><span class="sxs-lookup"><span data-stu-id="4b816-114">The operating system minor version, or a NULL value to indicate any version.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b816-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="4b816-115">Remarks</span></span>  
 <span data-ttu-id="4b816-116">`OSINFO`на основе `OSVERSIONINFOEX` структуру и используется в вызовах функции платформы Microsoft Windows `GetVersionEx`.</span><span class="sxs-lookup"><span data-stu-id="4b816-116">`OSINFO` is based on the `OSVERSIONINFOEX` structure that is used in calls to the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="4b816-117">Эта структура используется структура ASSEMBLYMETADATA для указания поддержки операционной системы.</span><span class="sxs-lookup"><span data-stu-id="4b816-117">This structure is used by the ASSEMBLYMETADATA structure to indicate its operating system support.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b816-118">Требования</span><span class="sxs-lookup"><span data-stu-id="4b816-118">Requirements</span></span>  
 <span data-ttu-id="4b816-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b816-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b816-120">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4b816-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4b816-121">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4b816-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4b816-122">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b816-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b816-123">См. также</span><span class="sxs-lookup"><span data-stu-id="4b816-123">See Also</span></span>  
 [<span data-ttu-id="4b816-124">Структуры метаданных</span><span class="sxs-lookup"><span data-stu-id="4b816-124">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [<span data-ttu-id="4b816-125">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="4b816-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)