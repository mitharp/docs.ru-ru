---
title: Устаревшие классы библиотеки классов .NET Framework
ms.custom: updateeachrelease
ms.date: 04/10/2018
helpviewer_keywords:
- obsolete [.NET Framework]
- what's obsolete [.NET Framework]
- deprecated [.NET Framework]
ms.assetid: d356a43a-73df-4ae2-a457-b9628074c7cd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 86928c734583cfc8cae0be53458a0d5c1769f292
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55287824"
---
# <a name="whats-obsolete-in-the-net-framework-class-library"></a>Устаревшие классы библиотеки классов .NET Framework
Со временем в платформу .NET Framework вносятся изменения. В каждой новой версии добавляются новые типы и члены типов, предоставляющие новые функциональные возможности. Существующие типы и их члены постепенно изменяются. Например, некоторые типы становятся менее важными из-за того, что поддерживаемая ими технология заменяется на другую технологию, а некоторые методы вытесняются новыми методами, которые более удобны в использовании или обладают большей функциональностью.  
  
 Платформа .NET Framework и среда CLR ориентированы на поддержку обратной совместимости (которая позволяет запускать приложения, разработанные в одной версии платформы .NET Framework, в более новой версии .NET Framework). Это затрудняет простое удаление типа или его члена. Вместо этого платформа .NET Framework указывает, что отдельный тип или член типа больше не следует использовать, помечая его как устаревший или нерекомендуемый. Для перевода типа или члена типа в разряд нерекомендуемых он помечается, чтобы разработчики знали об отказе от него и у них было время к этому подготовиться. Однако существующий код, в котором используется этот тип или член, продолжает выполняться в новой версии .NET Framework.  
  
> [!NOTE]
>  Применительно к типам и членам платформы .NET Framework термины *устаревший* и *нерекомендуемый* имеют одинаковое значение.  
  
## <a name="the-obsoleteattribute-attribute"></a>Атрибут ObsoleteAttribute  
 Платформа .NET Framework указывает, что тип или член типа является устаревшим, помечая его с помощью атрибута <xref:System.ObsoleteAttribute>. Применение этого атрибута к типу или члену указывает на то, что этот тип или член будет удален в одной из последующих версий платформы .NET Framework без нарушения работы скомпилированного кода, в котором он используется.  
  
 Кроме обозначения устаревшего типа или члена типа, атрибут <xref:System.ObsoleteAttribute> определяет, как компилятор обрабатывает исходный код, содержащий такой тип или член. Компилятор может компилировать код, выдавая предупреждение, или считать использование такого типа или члена ошибкой. В первом случае код успешно компилируется, но выдается предупреждение о том, что тип или член является устаревшим. Во втором случае происходит сбой компиляции.  
  
 Даже если во время компиляции вместо предупреждения происходит ошибка, атрибут <xref:System.ObsoleteAttribute> не влияет на поведение во время выполнения. Таким образом, приложения, использующие тип или член, который был успешно скомпилирован, всегда выполняются успешно. Сбой вызывает только повторная компиляция такого приложения.  
  
## <a name="how-to-handle-obsolete-types-and-members"></a>Обработка устаревших типов и членов  
 При обновлении и повторной компиляции существующего кода использование типа или члена, вызывающего предупреждение компилятора, полностью приемлемо. Однако следует просматривать предупреждение компилятора для того, чтобы определить, следует ли изменить код приложения. Если в предупреждении не указан допустимый альтернативный вариант, следует выполнить одно из следующих действий:  
  
-   Измените код, удалив такой тип или член, если это возможно.  
  
     - или -  
  
-   Просмотрите документацию по данной технологии, чтобы определить, что делать с таким нерекомендуемым типом или членом.  
  
 Можно не выполнять повторную компиляцию существующего кода в более новой версии .NET Framework. Вместо этого можно указать версию .NET Framework, в которой запускается имеющийся скомпилированный код. Предположим, что имеется приложение app1.exe, скомпилированное в платформе [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)], но требуется его запуск в платформе [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]. Для этого необходимо выполнить следующие действия:  
  
1.  Создайте файл конфигурации для основного исполняемого файла и назовите его *appName*.exe.config, где *appName* — это имя исполняемого файла приложения. Для используемого в данном примере приложения app1.exe необходимо создать файл конфигурации app1.exe.config.  
  
2.  Добавьте в этот файл конфигурации следующее.  
  
    ```xml  
    <configuration>  
       <startup>   
          <supportedRuntime version="v4.0" />  
       </startup>  
    </configuration>  
    ```  
  
 В следующей таблице приведены строковые значения, которые можно назначить атрибуту `version` для ориентации на определенную версию платформы .NET Framework.  
  
|Версия платформы .NET Framework|`version` строковое значение|
|-|-|  
|4.7 (включая 4.7.1 и 4.7.2)|v4.0|  
|4.6 (включая 4.6.1 и 4.6.2)|v4.0|  
|4.5 (включая 4.5.1 и 4.5.2)|v4.0|  
|4|v4.0|  
|3.5|v2.0.50727|  
|2.0|v2.0.50727|  
|1.1|v1.1.4322|  
|1.0|v1.0.3705|  
  
## <a name="obsolete-lists-for-the-net-framework-45-and-later-versions"></a>Списки устаревших типов и членов для .NET Framework 4.5 и более поздних версий  
 [Устаревшие типы](../../../docs/framework/whats-new/obsolete-types.md)  
  
 [Устаревшие члены](../../../docs/framework/whats-new/obsolete-members.md)  
  
## <a name="obsolete-lists-for-previous-versions"></a>Списки устаревших типов и членов для предыдущих версий  
 [Устаревшие типы в платформе .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=224224)  
  
 [Устаревшие члены в платформе .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=224227)  
  
 [Список устаревших элементов в платформе .NET Framework 3.5](https://go.microsoft.com/fwlink/?LinkId=163710)  
  
 [Список устаревших элементов в платформе .NET Framework 2.0](https://go.microsoft.com/fwlink/?LinkID=125264)  
  
## <a name="see-also"></a>См. также
- [\<Поддерживаемый элемент среды выполнения](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)
