---
title: Как выполнить Удаление хранилищ из области изолированного хранения
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- stores, deleting
- data stores, deleting
- deleting stores
- removing stores
- isolated storage, deleting stores
- storing data using isolated storage, deleting stores
- data storage using isolated storage, deleting stores
ms.assetid: 3947e333-5af6-4601-b2f1-24d4d6129cf3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 19a671cac609e79088956ecb4324ebb0a25fb941
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54547405"
---
# <a name="how-to-delete-stores-in-isolated-storage"></a>Как выполнить Удаление хранилищ из области изолированного хранения
Класс <xref:System.IO.IsolatedStorage.IsolatedStorageFile> предоставляет два метода для удаления файлов изолированного хранилища.  
  
-   Метод экземпляра <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove> не требует аргументов и удаляет хранилище, которое его вызывает. Для данной операции не требуется никаких разрешений. Код, имеющий доступ к хранилищу, может удалить данные внутри него полностью или выборочно.  
  
-   Статический метод <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%28System.IO.IsolatedStorage.IsolatedStorageScope%29> принимает значение перечисления <xref:System.IO.IsolatedStorage.IsolatedStorageScope.User> и удаляет все хранилища пользователя, выполняющего этот код. Для выполнения операции требуется разрешение <xref:System.Security.Permissions.IsolatedStorageFilePermission> для значения <xref:System.Security.Permissions.IsolatedStorageContainment.AdministerIsolatedStorageByUser> .  
  
## <a name="example"></a>Пример  
 В следующем примере кода демонстрируется использование статических методов и методов экземпляра <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%2A> . Класс получает два хранилища: одно — изолированное по пользователю и сборке, другое — изолированное по пользователю, домену и сборке. Затем изолированное по пользователю, домену и сборке хранилище удаляется вызовом метода <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove> файла изолированного хранилища  `isoStore1`. Далее вызовом статического метода <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%28System.IO.IsolatedStorage.IsolatedStorageScope%29>удаляются все оставшиеся хранилища пользователя.  
  
 [!code-cpp[Conceptual.IsolatedStorage#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source3.cpp#3)]
 [!code-csharp[Conceptual.IsolatedStorage#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source3.cs#3)]
 [!code-vb[Conceptual.IsolatedStorage#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source3.vb#3)]  
  
## <a name="see-also"></a>См. также

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>
- [Изолированное хранилище](../../../docs/standard/io/isolated-storage.md)
