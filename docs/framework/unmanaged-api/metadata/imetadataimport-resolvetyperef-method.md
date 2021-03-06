---
title: Метод IMetaDataImport::ResolveTypeRef
ms.date: 03/30/2017
api_name:
- IMetaDataImport.ResolveTypeRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::ResolveTypeRef
helpviewer_keywords:
- ResolveTypeRef method [.NET Framework metadata]
- IMetaDataImport::ResolveTypeRef method [.NET Framework metadata]
ms.assetid: 556bccfb-61bc-4761-b1d5-de4b1c18a38f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3c69c67c5c9d996bd746d82ea86caf4a396c0b10
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54625241"
---
# <a name="imetadataimportresolvetyperef-method"></a>Метод IMetaDataImport::ResolveTypeRef
Разрешает <xref:System.Type> ссылку, представленный указанный токен TypeRef.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `tr`  
 [in] Токен метаданных TypeRef для возврата сведений о типе, на которую указывает ссылка.  
  
 `riid`  
 [in] Идентификатор IID интерфейса, возвращаемый в `ppIScope`. Как правило это будет IID_IMetaDataImport.  
  
 `ppIScope`  
 [out] Интерфейс для области модуля, в котором определен тип, на который указывает ссылка.  
  
 `ptd`  
 [out] Указатель на токен TypeDef, представляющий ссылочного типа.  
  
## <a name="remarks"></a>Примечания  
  
> [!IMPORTANT]
>  Не используйте этот метод, если загружено несколько доменов приложений. Метод не учитывает границы домена приложения. Если несколько версий сборки загружаются, и они содержат один и тот же тип того же пространства имен, метод возвращает области модуля, найденную первого типа.  
  
 `ResolveTypeRef` Поиска методов для определения типа в других модулях. Если определение типа обнаруживается, `ResolveTypeRef` возвращает интерфейс для области модуля, а также маркер TypeDef для типа.  
  
 Если необходимо разрешить ссылку на тип получит разрешение область AssemblyRef, `ResolveTypeRef` метод осуществляет поиск совпадения только в области метаданных, которые уже было открыто с вызовами либо [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)метод или [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) метод. Это обусловлено `ResolveTypeRef` не может определить только в области AssemblyRef, где на диске или в глобальном кэше сборок сборки хранятся.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
