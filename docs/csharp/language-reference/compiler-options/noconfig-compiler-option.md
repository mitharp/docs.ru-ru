---
title: -noconfig (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /noconfig
helpviewer_keywords:
- /noconfig compiler option [C#]
- csc.rsp
- -noconfig compiler option [C#]
- noconfig compiler option [C#]
ms.assetid: cd26967e-e494-4c8c-b5c9-af13b2f78b2e
ms.openlocfilehash: 8d28ef1334df847865721783fa98aaa9d8c576be
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54528580"
---
# <a name="-noconfig-c-compiler-options"></a>-noconfig (параметры компилятора C#)
Параметр **-noconfig** указывает компилятору не выполнять компиляцию с использованием файла csc.rsp, который располагается в том же каталоге, что и файл csc.exe, и загружается оттуда.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-noconfig  
```  
  
## <a name="remarks"></a>Примечания  
 Файл csc.rsp содержит ссылки на все сборки, поставляемые вместе с платформой .NET Framework. Фактические ссылки, которые включает среда разработки Visual Studio .NET, зависят от типа проекта.  
  
 Вы можете изменить файл csc.rsp и указать дополнительные параметры компилятора, которые нужно включать при каждой компиляции, из командной строки с помощью программы csc.exe (кроме параметра **-noconfig**).  
  
 Компилятор обрабатывает параметры, передаваемые в команду **csc**, последними. Таким образом, любой параметр командной строки переопределяет значение аналогичного параметра в файле csc.rsp.  
  
 Если не требуется, чтобы компилятор искал и использовал параметры в файле csc.rsp, укажите параметр **-noconfig**.  
  
 Этот параметр компилятора недоступен в Visual Studio и не может быть изменен программным способом.  
  
## <a name="see-also"></a>См. также

- [Параметры компилятора C# ](../../../csharp/language-reference/compiler-options/index.md)
- [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)
