---
title: Метод ImportFileEx
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx
helpviewer_keywords:
- ImportFileEx method
ms.assetid: ad276f3f-b303-46ac-97e0-66a377adaa4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a0381ee61a0128a8ae303d44198f8d391b4531a9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660623"
---
# <a name="importfileex-method"></a>Метод ImportFileEx
Импортирует указанную сборку или Непривязанный модуль.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT ImportFileEx(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
#### <a name="parameters"></a>Параметры  
 `pszFilename`  
 Полное имя файла для импорта.  
  
 `pszTargetName`  
 Необязательное имя целевого файла.  
  
 `fSmartImport`  
 Если значение равно TRUE, используется ImportTypes, в противном случае импорт должен выполняться вручную.  
  
 `dwOpenFlags`  
 Флаги, передаваемые по [метод OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).  
  
 `pImportToken`  
 Получает идентификатор импортируемого файла.  
  
 `ppAssemblyScope`  
 Получает области импорта сборки [интерфейс IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) интерфейс. Имеет значение NULL, если файл не является сборкой.  
  
 `pdwCountOfScopes`  
 Получает число импортированных файлов и/или областей.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK, если метод выполнен успешно.  
  
## <a name="requirements"></a>Требования  
 Требуется alink.h.  
  
## <a name="see-also"></a>См. также
- [Интерфейс IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [Интерфейс IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [API ALink](../../../../docs/framework/unmanaged-api/alink/index.md)
