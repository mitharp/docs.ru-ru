---
title: События общих переменных WithEvents не могут обрабатываться не используемыми совместно методами
ms.date: 07/20/2015
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
ms.openlocfilehash: 09f56d340322ee88afc54e7e8a53716777782d47
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505774"
---
# <a name="events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a>События общих переменных WithEvents не могут обрабатываться не используемыми совместно методами
Переменная, объявленная с `Shared` модификатор является общей переменной. Общей переменной определяет строго одно место хранения. Переменная, объявленная с `WithEvents` модификатором обработки набора событий, вызываемых переменной типа, к которому относится переменная. Когда значение присваивается переменной, свойства, созданные `WithEvents` объявление отсоединяется от любого существующего обработчика событий и подключает обработчик событий с помощью `Add` метод.  
  
 **Идентификатор ошибки:** BC30594  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Объявите обработчик событий `Shared`.  
  
## <a name="see-also"></a>См. также
- [Общие](../../../visual-basic/language-reference/modifiers/shared.md)
- [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)
