---
title: Метод IMetaDataEmit2::DefineGenericParam
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.DefineGenericParam
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::DefineGenericParam
helpviewer_keywords:
- IMetaDataEmit2::DefineGenericParam method [.NET Framework metadata]
- DefineGenericParam method [.NET Framework metadata]
ms.assetid: 47b2a3b6-907d-43dc-858d-1ae7dca1316a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b54f5bb47135bcf56c91cd07b916c959e75b9fb5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745331"
---
# <a name="imetadataemit2definegenericparam-method"></a>Метод IMetaDataEmit2::DefineGenericParam
Создает определение для параметра универсального типа и возвращает маркер для этого параметра универсального типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT DefineGenericParam (   
    [in]  mdToken         tk,   
    [in]  ULONG           ulParamSeq,   
    [in]  DWORD           dwParamFlags,   
    [in]  LPCWSTR         szname,   
    [in]  DWORD           reserved,   
    [in]  mdToken         rtkConstraints[],   
    [out] mdGenericParam  *pgp  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `tk`  
 [in] `mdTypeDef` Или `mdMethodDef` токен, представляющий метод или конструктор, для которого необходимо определить универсальный параметр.  
  
 `ulParamSeq`  
 [in] Индекс универсального параметра.  
  
 `dwParamFlags`  
 [in] Значение [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) перечисление, описывающее тип универсального параметра.  
  
 `szname`  
 [in] Имя параметра.  
  
 `reserved`  
 [in] Этот параметр зарезервирован для будущего расширения.  
  
 `rtkConstraints`  
 [in] Массив типа ограничения, оканчивающаяся нулем. Элементы массива должны быть `mdTypeDef`, `mdTypeRef`, или `mdTypeSpec` токеном метаданных.  
  
 `pgp`  
 [out] Токен, который представляет универсальный параметр.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
