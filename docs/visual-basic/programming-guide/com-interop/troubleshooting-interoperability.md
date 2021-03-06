---
title: Устранение неполадок взаимодействия (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interop, deploying assemblies
- assemblies [Visual Basic]
- interop, installing assemblies that share components
- COM objects, troubleshooting
- interop, sharing components
- troubleshooting interoperability [Visual Basic]
- interoperability, troubleshooting
- COM interop [Visual Basic], troubleshooting
- assemblies [Visual Basic], deploying
- troubleshooting Visual Basic, interoperability
- interop assemblies
- interoperability, sharing components
- shared components, using with assemblies
ms.assetid: b324cc1e-b03c-4f39-aea6-6a6d5bfd0e37
ms.openlocfilehash: 413c9331611d3406c13df58f25db1ef0255339b6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517673"
---
# <a name="troubleshooting-interoperability-visual-basic"></a>Устранение неполадок взаимодействия (Visual Basic)
При взаимодействии между COM и управляемым кодом [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], может появиться один или несколько из следующих распространенных проблем.  
  
##  <a name="vbconinteroperabilitymarshalinganchor1"></a> Маршалинг взаимодействия  
 В некоторых случаях может потребоваться использовать типы данных, которые не являются частью [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Сборки взаимодействия обрабатывать большую часть работы с объектами COM, но может потребоваться управлять типами данных, которые используются, когда управляемые объекты доступны через COM. Например, структуры в библиотеках класса необходимо указать `BStr` неуправляемый тип для строк, отправляемых на COM-объекты, созданные в Visual Basic 6.0 и более ранних версий. В таких случаях можно использовать <xref:System.Runtime.InteropServices.MarshalAsAttribute> атрибут, чтобы управляемые типы в качестве неуправляемых типов.  
  
##  <a name="vbconinteroperabilitymarshalinganchor2"></a> Экспорт строк фиксированной длины в неуправляемом коде  
 В Visual Basic 6.0 и более ранних версий строки экспортируются COM-объектов как последовательности байтов без знака завершающимся нулевым значением. Для обеспечения совместимости с другими языками Visual Basic .NET включает завершающий знак при экспорте строк. Лучший способ решить проблему несовместимости — экспортировать строки без завершающего знака как массивы `Byte` или `Char`.  
  
##  <a name="vbconinteroperabilitymarshalinganchor3"></a> Экспорт иерархий наследования  
 Управляемого класса выравниваются иерархий при представлении в виде COM-объектов. К примеру Если определить базовый класс с членом и, наследуют базовый класс в производном классе, который предоставляется как объект COM, клиенты, использующие производный класс в COM-объект не будет возможность использовать наследуемые члены. Члены базового класса из COM-объектов может осуществляться только как экземпляры базового класса, а затем только в том случае, если базовый класс также создается как COM-объекта.  
  
## <a name="overloaded-methods"></a>Перегруженные методы  
 Несмотря на то, что перегруженные методы можно создать с помощью Visual Basic, они не поддерживаются в COM. Когда класс, содержащий перегруженные методы предоставляется как объект COM, новые имена методов создаются для перегруженных методов.  
  
 Например, рассмотрим класс, имеющий две перегрузки `Synch` метод. Когда класс предоставляется как объект COM, новые имена созданных методов может быть `Synch` и `Synch_2`.  
  
 Переименование может вызвать две проблемы для потребителей COM-объекта.  
  
1.  Клиенты могут не ожидать имена созданных методов.  
  
2.  Имена созданных методов в классе, в виде COM-объекта можно изменить при добавлении новых перегрузок для класса или его базовый класс. Это может вызвать проблемы управления версиями.  
  
 Чтобы устранить обе проблемы, присвойте каждому методу уникальное имя, вместо того чтобы использовать перегрузку, при разработке объектов, которым будет предоставляться в виде COM-объектов.  
  
##  <a name="vbconinteroperabilitymarshalinganchor4"></a> Использование COM-объектам через сборки взаимодействия  
 Сборки взаимодействия используются почти так же, как если бы они замены управляемого кода для COM-объектов, которые они представляют. Тем не менее поскольку они являются оболочки и не фактических объектов COM, существуют некоторые различия между использованием сборок взаимодействия и стандартные сборки. Эти различия касаются уязвимость классы и типы данных для параметров и возвращаемых значений.  
  
##  <a name="vbconinteroperabilitymarshalinganchor5"></a> Классы, предоставляемые и как интерфейсы и классы  
 В отличие от классов в стандартные сборки COM-классов, представлены в сборки взаимодействия в качестве интерфейс и класс, представляющий COM-класса. Имя интерфейс идентична COM-класса. Имя класса взаимодействия такой же, как для исходного класса COM, но со словом «Class» добавлено. Например предположим, что у вас есть проект со ссылкой на сборку взаимодействия для COM-объекта. Если COM-класса называется `MyComClass`, IntelliSense и обозреватель объектов Показать интерфейс с именем `MyComClass` и класс с именем `MyComClassClass`.  
  
##  <a name="vbconinteroperabilitymarshalinganchor6"></a> Создание экземпляров класса .NET Framework  
 Как правило, создается экземпляр [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] используя `New` инструкцию с именем класса. Наличие класса COM, представленный сборку взаимодействия — это тот случай, в котором можно использовать `New` инструкции с интерфейсом. Если вы не используете COM-класса с `Inherits` инструкции, можно использовать интерфейс, так же, как и класс. Следующий код демонстрирует создание `Command` объекта в проекте, который содержит ссылку на Microsoft ActiveX данных объектов 2.8 библиотеки COM-объекта:  
  
 [!code-vb[VbVbalrInterop#20](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_1.vb)]  
  
 Тем не менее если вы используете класс COM как основу для производного класса, необходимо использовать класс взаимодействия, представляющий класс COM, как показано в следующем коде:  
  
 [!code-vb[VbVbalrInterop#21](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_2.vb)]  
  
> [!NOTE]
>  Сборки взаимодействия неявно реализуют интерфейсы, которые представляют COM-классов. Не следует пытаться использовать `Implements` приведет к инструкции для реализации этих интерфейсов или ошибку.  
  
##  <a name="vbconinteroperabilitymarshalinganchor7"></a> Типы данных для параметров и возвращаемых значений  
 В отличие от элементов обычных сборок элементы сборки взаимодействия могут иметь типы данных, которые отличаются от тех, которые используются в исходном объявлении объекта. Несмотря на то, что сборки взаимодействия неявное преобразование типов COM в совместимые типы среды выполнения, следует обратить внимание на типы данных, которые используются с обеих сторон для предотвращения ошибки времени выполнения. Например, в COM-объекты, созданные в Visual Basic 6.0 и более ранних версий, значения типа `Integer` предполагается [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] эквивалентный тип `Short`. Рекомендуется использовать обозреватель объектов для проверки характеристик импортированных элементов, прежде чем их использовать.  
  
##  <a name="vbconinteroperabilitymarshalinganchor8"></a> Методы COM уровня модуля  
 Большинство объектов COM используются путем создания экземпляра класса COM с помощью `New` ключевое слово и затем вызывает методы этого объекта. Единственным исключением из этого правила включает в себя COM-объекты, содержащие `AppObj` или `GlobalMultiUse` COM-классов. Такие классы напоминают методы уровня модуля в классы Visual Basic .NET. Visual Basic 6.0 и более ранних версиях неявно создает экземпляры таких объектов при первом вызове одного из их методов. Например, в Visual Basic 6.0 можно добавить ссылку на библиотеку Microsoft DAO 3.6 Object Library и вызов `DBEngine` без предварительного создания экземпляра:  
  
```vb  
Dim db As DAO.Database  
' Open the database.  
Set db = DBEngine.OpenDatabase("C:\nwind.mdb")  
' Use the database object.  
```  
  
 Visual Basic .NET требуется всегда создавать экземпляры COM-объектов перед использованием их методов. Чтобы использовать эти методы в Visual Basic, объявите переменную нужного класса и используйте ключевое слово new для назначения объекта переменной объекта. `Shared` Слово может использоваться для убедитесь, что создается только один экземпляр класса.  
  
 [!code-vb[VbVbalrInterop#23](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_3.vb)]  
  
##  <a name="vbconinteroperabilitymarshalinganchor9"></a> Необработанные ошибки в обработчиках событий  
 Одна из распространенных проблем взаимодействия касается ошибок в обработчиках событий, которые обрабатывают события COM-объектов. Такие ошибки игнорируются, если только специально проверки на наличие ошибок с помощью `On Error` или `Try...Catch...Finally` инструкций. Например ниже приведен из проекта Visual Basic .NET, который содержит ссылку на Microsoft ActiveX данных объектов 2.8 библиотеки COM-объекта.  
  
 [!code-vb[VbVbalrInterop#24](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_4.vb)]  
  
 В этом примере происходит ошибка, должным образом. Тем не менее если один и тот же пример без `Try...Catch...Finally` блока, ошибка обрабатывается, как если бы вы использовали `OnError Resume Next` инструкции. Без обработки ошибок деления на ноль вызовет неявную ошибку. Поскольку такие ошибки никогда не вызывают необработанное исключение, важно использовать определенные виды обработки исключений в обработчики событий, которые обрабатывают события из COM-объектов.  
  
### <a name="understanding-com-interop-errors"></a>Основные сведения об ошибках взаимодействия COM  
 Без обработки ошибок вызовы взаимодействия часто создают ошибки, которые предоставляют немного информации. По возможности используйте структурированную обработку для предоставления дополнительных сведений о проблемах, возникающих ошибок. Это может быть особенно полезно при отладке приложений. Пример:  
  
 [!code-vb[VbVbalrInterop#25](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_5.vb)]  
  
 Вы найдете сведения, такие как описание ошибки, HRESULT и источника ошибок COM, проверив содержимое объекта исключения.  
  
##  <a name="vbconinteroperabilitymarshalinganchor10"></a> Проблемы управления ActiveX  
 Большинство элементов управления ActiveX, которые работают с Visual Basic 6.0 работать с Visual Basic .NET без проблем. Большинство исключений — это контейнерные элементы управления или элементы управления, которые визуально содержат другие элементы управления. Ниже приведены некоторые примеры старых элементов управления, которые не работают с помощью Visual Studio:  
  
-   Элемент управления Microsoft Forms 2.0 кадра  
  
-   Элемент управления вверх-вниз, также известный как элемент управления "Счетчик"  
  
-   Шеридан набор вкладок  
  
 Имеется только несколько временных решений проблемы с неподдерживаемыми элементами управления ActiveX. Если вы являетесь владельцем исходного кода, можно перенести существующие элементы управления в Visual Studio. В противном случае можно проверить с поставщиками программного обеспечения для обновления. NET-совместимой версии элементов управления для замены неподдерживаемые элементы управления ActiveX.  
  
##  <a name="vbconinteroperabilitymarshalinganchor11"></a> Передача свойств только для чтения из элементов управления ByRef  
 Visual Basic .NET иногда вызывает ошибки COM, такие как «Ошибка 0x800A017F CTL_E_SETNOTSUPPORTED», при передаче `ReadOnly` свойства некоторых старых элементов управления ActiveX, как `ByRef` параметров для других процедур. Как и вызовов процедур с Visual Basic 6.0, не вызывает ошибку, и параметры обрабатываются так, как если бы они передавались по значению. Visual Basic .NET сообщение об ошибке указывает, что вы пытаетесь изменить свойство, которое не поддерживает свойство `Set` процедуры.  
  
 Если у вас есть доступ к вызываемой процедуры, можно предотвратить эту ошибку, используя `ByVal` ключевого слова для объявления параметров, принимающих `ReadOnly` свойства. Пример:  
  
 [!code-vb[VbVbalrInterop#26](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_6.vb)]  
  
 Если у вас нет доступа к исходному коду для вызываемой процедуры, можно принудительно свойство передаваться по значению, добавив дополнительный набор заключается в квадратные скобки вызывающей процедуре. Например в проекте, который содержит ссылку на Microsoft ActiveX данных объектов 2.8 библиотеки COM-объекта, можно использовать:  
  
 [!code-vb[VbVbalrInterop#27](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_7.vb)]  
  
##  <a name="vbconinteroperabilitymarshalinganchor12"></a> Развертывание сборок, предоставляющих взаимодействие  
 Развертывание сборок, которые предоставляют интерфейсы COM представляет некоторые уникальные трудности. Например потенциальные проблема возникает, когда отдельные приложения ссылаются на одну и ту же сборку COM. Эта ситуация типична при установке новой версии сборки, а другое приложение по-прежнему использует старую версию сборки. При удалении сборки, общих папок библиотеки DLL, вы можете непреднамеренно сделать ее недоступной для других сборок.  
  
 Чтобы избежать этой проблемы, необходимо установить общие сборки в глобальный кэш сборок (GAC) и использовать MergeModule для компонента. Если приложение невозможно установить в глобальном кэше СБОРОК, его следует установить, чтобы CommonFilesFolder в подкаталоге конкретной версии.  
  
 Сборки, которые не являются общими должен находиться рядом друг с другом в каталоге с вызывающим приложением.  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [COM-взаимодействие](../../../visual-basic/programming-guide/com-interop/index.md)
- [Tlbimp.exe (программа экспорта библиотек типов)](../../../framework/tools/tlbimp-exe-type-library-importer.md)
- [Tlbexp.exe (программа экспорта библиотек типов)](../../../framework/tools/tlbexp-exe-type-library-exporter.md)
- [Пошаговое руководство: Реализация наследования с использованием COM-объектов](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)
- [Оператор Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [Глобальный кэш сборок](../../../framework/app-domains/gac.md)
