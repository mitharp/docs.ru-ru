---
title: Метод ICorDebugController::Terminate
ms.date: 03/30/2017
api_name:
- ICorDebugController.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Terminate
helpviewer_keywords:
- Terminate method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Terminate method [.NET Framework debugging]
ms.assetid: 4275af0c-b5a7-4e4c-97c9-7e41f36b2dd8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 362ae813846ab31f170ae49288735996eb1e9555
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54531763"
---
# <a name="icordebugcontrollerterminate-method"></a>Метод ICorDebugController::Terminate
Завершает процесс с помощью указанного кода выхода.  
  
> [!NOTE]
>  Этот метод является оболочкой для Win32 `TerminateProcess` функции. Таким образом `Terminate` использует код выхода в том же образом, как Win32 `TerminateProcess` функция использует его.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `exitCode`  
 [in] Числовое значение, — это код выхода. Допустимые числовые значения определяются в Winbase.h.  
  
## <a name="remarks"></a>Примечания  
 Если процесс останавливается, когда `Terminate` является именем, процесс должен быть продолжено с помощью [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) метод таким образом, чтобы отладчик получает подтверждение о завершении через [ ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) или [ICorDebugManagedCallback::ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) обратного вызова.  
  
> [!NOTE]
>  Этот метод не реализован доменом приложения. То есть оно не реализовано на <xref:System.AppDomain> уровень.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

