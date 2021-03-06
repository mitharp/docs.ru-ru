---
title: Атрибут Extension может быть применен только к объявлениям Module, Sub или Function
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: e2e2c41d713b0b04b8bc7208a83d059f0d16bf06
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278724"
---
# <a name="extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations"></a>Атрибут Extension может быть применен только к объявлениям Module, Sub или Function
Единственный способ расширения типа данных в Visual Basic является определение метода расширения внутри стандартного модуля. Метод расширения может быть `Sub` процедуры или `Function` процедуры. Все методы расширения должны быть помечены атрибутом расширения, `<Extension()>`, из <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> пространства имен. Кроме того модуль, содержащий метод расширения может быть помечен таким же образом. Не используется атрибут расширения является допустимым.  
  
 **Идентификатор ошибки:** BC36550  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Удалите атрибут расширения.  
  
-   Измените расширение в качестве метода, определенного в заключающего модуля.  
  
## <a name="example"></a>Пример  
 В следующем примере определяется `Print` метод `String` тип данных.  
  
```  
Imports StringUtility  
Imports System.Runtime.CompilerServices  
Namespace StringUtility  
    <Extension()>   
    Module StringExtensions  
        <Extension()>   
        Public Sub Print (ByVal str As String)  
            Console.WriteLine(str)  
        End Sub  
    End Module  
End Namespace  
```  
  
## <a name="see-also"></a>См. также
- [Обзор атрибутов](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [Методы расширения](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
- [Оператор Module](../../../visual-basic/language-reference/statements/module-statement.md)
