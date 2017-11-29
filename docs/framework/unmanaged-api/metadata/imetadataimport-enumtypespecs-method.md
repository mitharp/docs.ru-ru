---
title: "Метод IMetaDataImport::EnumTypeSpecs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumTypeSpecs
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumTypeSpecs
helpviewer_keywords:
- EnumTypeSpecs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeSpecs method [.NET Framework metadata]
ms.assetid: 75331c7b-988b-436c-9eb9-a270d37b4f06
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a872af384a8df624178d8d37d5ad98a0b5c561d1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumtypespecs-method"></a><span data-ttu-id="49fee-102">Метод IMetaDataImport::EnumTypeSpecs</span><span class="sxs-lookup"><span data-stu-id="49fee-102">IMetaDataImport::EnumTypeSpecs Method</span></span>
<span data-ttu-id="49fee-103">Перечисляет токены TypeSpec, определенные в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="49fee-103">Enumerates TypeSpec tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49fee-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="49fee-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeSpecs (  
   [in, out] HCORENUM    *phEnum,  
   [out] mdTypeSpec      rTypeSpecs[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTypeSpecs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="49fee-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="49fee-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="49fee-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="49fee-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="49fee-107">Это значение должно быть NULL при первом вызове этого метода.</span><span class="sxs-lookup"><span data-stu-id="49fee-107">This value must be NULL for the first call of this method.</span></span>  
  
 `rTypeSpecs`  
 <span data-ttu-id="49fee-108">[out] Массив, используемый для хранения токены TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="49fee-108">[out] The array used to store the TypeSpec tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="49fee-109">[in] Максимальный размер массива `rTypeSpecs`.</span><span class="sxs-lookup"><span data-stu-id="49fee-109">[in] The maximum size of the `rTypeSpecs` array.</span></span>  
  
 `pcTypeSpecs`  
 <span data-ttu-id="49fee-110">[out] Число токены TypeSpec, возвращаемых в `rTypeSpecs`.</span><span class="sxs-lookup"><span data-stu-id="49fee-110">[out] The number of TypeSpec tokens returned in `rTypeSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="49fee-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="49fee-111">Return Value</span></span>  
  
|<span data-ttu-id="49fee-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="49fee-112">HRESULT</span></span>|<span data-ttu-id="49fee-113">Описание</span><span class="sxs-lookup"><span data-stu-id="49fee-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="49fee-114">`EnumTypeSpecs`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="49fee-114">`EnumTypeSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="49fee-115">Существуют маркеры для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="49fee-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="49fee-116">В этом случае `pcTypeSpecs` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="49fee-116">In that case, `pcTypeSpecs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49fee-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="49fee-117">Remarks</span></span>  
 <span data-ttu-id="49fee-118">Токены TypeSpec, создаются [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="49fee-118">The TypeSpec tokens are created by the [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49fee-119">Требования</span><span class="sxs-lookup"><span data-stu-id="49fee-119">Requirements</span></span>  
 <span data-ttu-id="49fee-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49fee-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49fee-121">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="49fee-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="49fee-122">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="49fee-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="49fee-123">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49fee-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49fee-124">См. также</span><span class="sxs-lookup"><span data-stu-id="49fee-124">See Also</span></span>  
 [<span data-ttu-id="49fee-125">IMetaDataImport-интерфейс</span><span class="sxs-lookup"><span data-stu-id="49fee-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="49fee-126">IMetaDataImport2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="49fee-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)