---
title: Метод ICorDebugObjectValue::GetFieldValue
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.GetFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetFieldValue
helpviewer_keywords:
- ICorDebugObjectValue::GetFieldValue method [.NET Framework debugging]
- GetFieldValue method [.NET Framework debugging]
ms.assetid: c96770b0-3e09-47bb-bd29-20353b043459
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 72a504d23b7b15ad3de72995a632843874cc7c5f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54631775"
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a>Метод ICorDebugObjectValue::GetFieldValue
Получает значение указанного поля заданного класса для этого значения объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pClass`  
 [in] Указатель на объект, представляющий класс, для которого необходимо получить значение поля «ICorDebugClass».  
  
 `fieldDef`  
 [in] `mdFieldDef` Маркер, который ссылается на метаданные, описывающие поле.  
  
 `ppValue`  
 [out] Указатель на объект «ICorDebugValue», который представляет значение указанного поля.  
  
## <a name="remarks"></a>Примечания  
 Класс, заданный в `pClass` параметр, должен быть в иерархии значение объекта класса, а поле должно быть полем этого класса.  
  
 `GetFieldValue` Метод все равно заканчивается успешно для универсальных объектов и классов. Например если MyDictionary\<V > наследует из словаря\<string, V >, и значение объекта, которое имеет тип MyDictionary\<int32 >, передав `ICorDebugClass` объект словаря\<K, V > будет получить поля словаря\<string, int32 >.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также


