---
title: Метод ISymUnmanagedReader2::GetMethodsInDocument
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetMethodsInDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetMethodsInDocument
helpviewer_keywords:
- ISymUnmanagedReader2::GetMethodsInDocument method [.NET Framework debugging]
- GetMethodsInDocument method [.NET Framework debugging]
ms.assetid: c7ae84d6-81e8-4cb7-a1f9-d48b6cde5d79
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 38cbea25c485ff517e3448c4de5245ff36fb5b21
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54594555"
---
# <a name="isymunmanagedreader2getmethodsindocument-method"></a>Метод ISymUnmanagedReader2::GetMethodsInDocument
Возвращает каждый метод, который содержит сведения о строке в указанный документ.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetMethodsInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is(cMethod),  
        length_is(*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
#### <a name="parameters"></a>Параметры  
 `document`  
 [in] Указатель на документ.  
  
 `cMethod`  
 [in] Объект `ULONG32` указывает размер `pRetVal` массива.  
  
 `pcMethod`  
 [out] Указатель на `ULONG32` , получающий размер буфера, необходимый для методов.  
  
 `pRetVal`  
 [out] Указатель на буфер, получающий методы.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** CorSym.idl CorSym.h  
  
## <a name="see-also"></a>См. также
- [Интерфейс ISymUnmanagedReader2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
