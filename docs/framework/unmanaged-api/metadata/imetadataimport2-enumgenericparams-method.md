---
title: Метод IMetaDataImport2::EnumGenericParams
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumGenericParams
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumGenericParams
helpviewer_keywords:
- EnumGenericParams method [.NET Framework metadata]
- IMetaDataImport2::EnumGenericParams method [.NET Framework metadata]
ms.assetid: b50488a5-3cf0-483c-82dc-2892a3ec61ac
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 51eeaf79e470e38461450c6f4afbef982cca7a34
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54727967"
---
# <a name="imetadataimport2enumgenericparams-method"></a>Метод IMetaDataImport2::EnumGenericParams
Получает перечислитель для массива маркеров параметра универсального типа, связанный с указанным TypeDef или MethodDef маркер.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnumGenericParams (  
   [in, out] HCORENUM     *phEnum,   
   [in]  mdToken          tk,  
   [out] mdGenericParam   rGenericParams[],   
   [in]  ULONG            cMax,   
   [out] ULONG            *pcGenericParams  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `phEnum`  
 [in, out] Указатель на перечислитель.  
  
 `tk`  
 [in] Токен TypeDef или MethodDef, которого универсальных параметров, необходимо перечислить.  
  
 `rGenericParams`  
 [out] Массив универсальных параметров для перечисления.  
  
 `cMax`  
 [in] Максимальное число маркеров для размещения в `rGenericParams`.  
  
 `pcGenericParams`  
 [out] Возвращенное число маркеров помещаются в `rGenericParams`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|`S_OK`|`EnumGenericParams` успешно возвращен.|  
|`S_FALSE`|`phEnum` не имеет члена элементов. В этом случае `pcGenericParams` имеет значение 0 (ноль).|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
