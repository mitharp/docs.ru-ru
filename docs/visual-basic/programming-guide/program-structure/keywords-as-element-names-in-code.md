---
title: Ключевые слова как имена элементов в коде (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, naming conventions
- keywords [Visual Basic], in code
- name conflicts [Visual Basic]
- element names [Visual Basic], in code
ms.assetid: 2e4e8e02-23f7-49b9-a1c8-2b0402b6b525
ms.openlocfilehash: 0d52df42b00abfa364762d97c162eb143e511f06
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54649496"
---
# <a name="keywords-as-element-names-in-code-visual-basic"></a>Ключевые слова как имена элементов в коде (Visual Basic)
Любым элементам программы, такие как переменная, класс или член — может иметь имя, совпадающее с именем служебное слово. Например, можно создать переменную с именем `Loop`. Тем не менее для ссылки на переменную, который имеет то же имя, что ограниченных `Loop` ключевое слово — необходимо поставили полной строки или заключите его в квадратные скобки (`[ ]`), как показано в следующем примере.  
  
 [!code-vb[VbVbcnConventions#8](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/keywords-as-element-names-in-code_1.vb)]  
  
 Если вы этого не сделать этого, то Visual Basic предполагается, что используется встроенная `Loop` ключевое слово и выводит сообщение об ошибке, как показано в следующем примере:  
  
 `' The following statement causes a compiler error.`  
  
 `Loop.Visible = True`  
  
 Можно использовать квадратные скобки, при ссылке на формах и элементах управления, а также при объявлении переменной или определении процедуры с тем же именем, как только ключевое слово. Его можно легко забыть определить имена или включать квадратные скобки и таким образом привести к ошибкам в код и сделать его труднее читаться. По этой причине рекомендуется не использовать служебные ключевые слова как имена элементов программы. Тем не менее если следующей версии Visual Basic определяет новое ключевое слово конфликтует с существующим именем формы или элемента управления, затем воспользуйтесь этот метод при обновлении кода для работы с новой версией.  
  
> [!NOTE]
>  Программы также могут содержаться имена элементов, предоставляемых в других сборках. Если эти имена конфликтуют с ограниченным доступом ключевые слова, квадратные скобки вокруг них приводит к Visual Basic, чтобы интерпретировать их как определенные вами элементы.  
  
## <a name="see-also"></a>См. также
- [Соглашения об именах Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
- [Соглашения о структуре программы и коде](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
