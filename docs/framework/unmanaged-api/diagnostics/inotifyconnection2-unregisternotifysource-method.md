---
title: Метод INotifyConnection2::UnregisterNotifySource
ms.date: 03/30/2017
api_name:
- INotifyConnection2.UnregisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::UnregisterNotifySource
helpviewer_keywords:
- INotifyConnection2::UnregisterNotifySource method [.NET Framework debugging]
- UnregisterNotifySource method [.NET Framework debugging]
ms.assetid: 2fc6c715-646f-41fd-9c12-c59b40575269
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3e5380ed63a362b73b0684ef07b638117751ca80
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54712016"
---
# <a name="inotifyconnection2unregisternotifysource-method"></a>Метод INotifyConnection2::UnregisterNotifySource
Удаляет заданный исходный объект уведомлений из соединения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT UnregisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `in_pNotifySource`  
 [in] Объект уведомления для отмены регистрации.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно.  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** ProtocolNotify2.idl  
  
## <a name="see-also"></a>См. также
- [Интерфейс INotifyConnection2](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
- [Интерфейс INotifySource2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [Интерфейс INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [Метод RegisterNotifySource](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-registernotifysource-method.md)
