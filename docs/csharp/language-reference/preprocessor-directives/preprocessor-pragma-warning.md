---
title: '#Справочник по C#. #pragma warning'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#pragma warning'
helpviewer_keywords:
- '#pragma warning [C#]'
ms.assetid: 723493d5-9753-4cec-babb-54e2b8eb36b6
ms.openlocfilehash: 7c664ee7d6e0e083eba958e6ee36a63009e13956
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54606612"
---
# <a name="pragma-warning-c-reference"></a>#pragma warning (Справочник по C#)
`#pragma warning` может включать или отключать определенные предупреждения.  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
#pragma warning disable warning-list  
#pragma warning restore warning-list  
```  
  
#### <a name="parameters"></a>Параметры  
 `warning-list`  
 Список номеров предупреждений с разделителем-запятой. Префикс CS является необязательным.  
  
 Если номера предупреждений не указаны, `disable` отключает все предупреждения, а `restore` включает все предупреждения.  
  
> [!NOTE]
>  Чтобы найти номера предупреждений в Visual Studio, выполните сборку проекта, а затем поиск номеров предупреждений в окне **Вывод**.  
  
## <a name="example"></a>Пример  
  
```csharp
// pragma_warning.cs  
using System;  
  
#pragma warning disable 414, CS3021  
[CLSCompliant(false)]  
public class C  
{  
    int i = 1;  
    static void Main()  
    {  
    }  
}  
#pragma warning restore CS3021  
[CLSCompliant(false)]  // CS3021  
public class D  
{  
    int i = 1;  
    public static void F()  
    {  
    }  
}  
```  
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../../../csharp/language-reference/index.md)
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Директивы препроцессора C#](../../../csharp/language-reference/preprocessor-directives/index.md)
- [Ошибки компилятора C#](../../../csharp/language-reference/compiler-messages/index.md)
