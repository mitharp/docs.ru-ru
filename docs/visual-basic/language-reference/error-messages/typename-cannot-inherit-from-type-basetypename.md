---
title: <typename> не может наследоваться от <type><basetypename>, поскольку он расширяет доступ базового типа <type> за пределы сборки
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: 226c85f887ecc706a5cb554c2163742f10896141
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269826"
---
# <a name="typename-cannot-inherit-from-type-basetypename-because-it-expands-the-access-of-the-base-type-outside-the-assembly"></a>"\<typename >" не может наследовать от \<тип > "\<имя_базового_типа >", поскольку он расширяет доступ базового \<тип > за пределы данной сборки
Класс или интерфейс наследует от базового класса или интерфейса, но имеет менее строгий уровень доступа.  
  
 Например `Public` интерфейс наследует от `Friend` интерфейс, или `Protected` класс наследует от `Private` класса. Этот класс представляет базовый класс или интерфейс для доступа к выше установленного уровня.  
  
 **Идентификатор ошибки:** BC30910  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Измените уровень доступа производный класс или интерфейс был менее строгий, как и для базового класса или интерфейса.  
  
     - или -  
  
-   Если требуется менее строгий уровень доступа, удалите `Inherits` инструкции. Не может наследовать от более ограниченных базового класса или интерфейса.  
  
## <a name="see-also"></a>См. также
- [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)
- [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Оператор Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
