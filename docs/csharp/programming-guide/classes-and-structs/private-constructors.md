---
title: Руководство по программированию на C#. Закрытые конструкторы
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, private constructors
- private constructors [C#]
ms.assetid: 29eeaa7d-8d81-453c-94b9-0e2800172621
ms.openlocfilehash: e406b72e5d2932464c407dce014dd8eceee59fb0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54577299"
---
# <a name="private-constructors-c-programming-guide"></a>Закрытые конструкторы (Руководство по программированию на C#)
Закрытый конструктор — это особый конструктор экземпляров. Обычно он используется в классах, содержащих только статические элементы. Если в классе один или несколько закрытых конструкторов и ни одного открытого конструктора, то прочие классы (за исключением вложенных классов) не смогут создавать экземпляры этого класса. Например:  
  
 [!code-csharp[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_1.cs)]  
  
 Объявление пустого конструктора запрещает автоматическое создание конструктора по умолчанию. Обратите внимание, что если не использовать с конструктором модификатор доступа, то по умолчанию он все равно будет закрытым. Однако обычно используется модификатор [private](../../../csharp/language-reference/keywords/private.md), чтобы явно обозначить невозможность создания экземпляров этого класса.  
  
 Закрытые конструкторы используются, чтобы не допустить создания экземпляров класса при отсутствии полей или методов экземпляра, например для класса <xref:System.Math>, или когда осуществляется вызов метода для получения экземпляра класса. Если все методы в классе являются статическими, имеет смысл сделать статическим весь класс. Дополнительные сведения см. в разделе [Статические классы и члены статических классов](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
## <a name="example"></a>Пример  
 Ниже приведен пример класса с закрытым конструктором.  
  
 [!code-csharp[csProgGuideObjects#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_2.cs)]  
  
 Обратите внимание, что если в примере раскомментировать следующий оператор, возникнет ошибка, так как конструктор недоступен из-за уровня защиты:  
  
 [!code-csharp[csProgGuideObjects#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_3.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  

Дополнительные сведения см. в разделе [Закрытые конструкторы](~/_csharplang/spec/classes.md#private-constructors) в [Спецификации языка C#](../../language-reference/language-specification/index.md). Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)
- [Конструкторы](../../../csharp/programming-guide/classes-and-structs/constructors.md)
- [Методы завершения](../../../csharp/programming-guide/classes-and-structs/destructors.md)
- [private](../../../csharp/language-reference/keywords/private.md)
- [public](../../../csharp/language-reference/keywords/public.md)
