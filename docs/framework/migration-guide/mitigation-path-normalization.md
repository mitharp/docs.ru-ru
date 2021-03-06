---
title: Устранение рисков. Нормализация путей
ms.date: 03/30/2017
ms.assetid: 158d47b1-ba6d-4fa6-8963-a012666bdc31
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: addbeeab6f5b3544a7ed1b86b7da0f7d09be7ffb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54701109"
---
# <a name="mitigation-path-normalization"></a>Устранение рисков. Нормализация путей
Начиная с приложений, ориентированных на [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], нормализация путей в .NET Framework изменилась.  
  
## <a name="what-is-path-normalization"></a>Что такое нормализация путей?  
 Нормализация пути подразумевает изменение строки, которая идентифицирует путь или файл, чтобы он соответствовал допустимому пути в целевой операционной системе. Нормализация обычно включает в себя:  
  
-   канонизацию разделителей компонентов и каталогов;  
  
-   применение текущего каталога к относительному пути;  
  
-   оценку относительного каталога (`.`) или родительского каталога (`..`) в пути;  
  
-   обрезку указанных символов.  
  
## <a name="the-changes"></a>Изменения  
 Начиная с приложений, ориентированных на [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], нормализация путей изменилась в следующих направлениях.  
  
-   Среда выполнения перекладывает нормализацию путей на функцию [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) операционной системы.  
  
-   Нормализация больше не предусматривает обрезки окончания сегментов каталогов (например, пробела в конце имени каталога).  
  
-   Поддержка синтаксиса пути устройства в режиме полного доверия, включая `\\.\` и (для API-интерфейсов файлового ввода-вывода в mscorlib.dll) `\\?\`.  
  
-   Среда выполнения не проверяет пути с синтаксисом устройства.  
  
-   Поддерживается использование синтаксиса устройства для доступа к альтернативным потокам данных.  
  
## <a name="impact"></a>Последствия  
 Для приложений, предназначенных для [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] или более поздней версии, эти изменения включены по умолчанию. Они должны улучшить производительность, позволяя методам получать доступ к ранее недоступным путям.  
  
 Это изменение не влияет на приложения, предназначенные для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] и более ранних версий, но работающие на платформе [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] или более новой версии.  
  
## <a name="mitigation"></a>Устранение рисков  
 В приложениях, предназначенных для [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] или более поздней версии, данное изменение можно отключить и использовать устаревшую нормализацию, добавив следующее в раздел [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения:  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
</runtime>  
```  
  
 В приложениях, предназначенных для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] или более ранней версии, но работающих на платформе [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] или более поздней версии, можно включить изменения в нормализацию пути, добавив следующее в раздел [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения:  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />    
</runtime>  
```  
  
## <a name="see-also"></a>См. также
- [Изменение целевой платформы](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)
