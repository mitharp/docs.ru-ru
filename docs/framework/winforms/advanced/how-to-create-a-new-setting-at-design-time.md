---
title: 'Как выполнить: Создание новых параметров во время разработки'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], design time
- application settings [Windows Forms], creating
ms.assetid: c5d60a66-6507-462f-a81f-e3bc0a804e16
ms.openlocfilehash: 160d4a9f560479b3a66b2cf4d7712b24551fabee
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54558708"
---
# <a name="how-to-create-a-new-setting-at-design-time"></a>Как выполнить: Создание новых параметров во время разработки
Можно создать новый параметр во время разработки с помощью конструктора параметров. Этот конструктор имеет табличный интерфейс, который позволяет создавать новые параметры и указать свойства для этих параметров. Необходимо указать имя, значение, тип и область для новых параметров. Создав параметр, он доступен в коде.  
  
### <a name="to-create-a-new-setting-at-design-time-in-c"></a>Чтобы создать новый параметр во время разработки вC#  
  
1.  В **обозревателе решений**, разверните **свойства** узле проекта.  
  
2.  Дважды щелкните файл с расширением Settings, в котором вы хотите добавить новый параметр. Имя по умолчанию для этого файла — Settings.settings.  
  
3.  В конструкторе параметров задайте имя, значение, тип и область действия параметра. Каждая строка представляет один параметр.  
  
### <a name="to-create-a-new-setting-at-design-time-in-visual-basic"></a>Чтобы создать новый параметр во время разработки в Visual Basic  
  
1.  В **обозревателе решений**, щелкните правой кнопкой мыши узел проекта и выберите **свойства**.  
  
2.  В **свойства** выберите **параметры** вкладки.  
  
3.  В конструкторе параметров задайте имя, значение, тип и область действия параметра. Каждая строка представляет один параметр.  
  
## <a name="see-also"></a>См. также
- [Использование параметров приложения и параметров пользователя](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)
- [Общие сведения о параметрах приложений](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
- [Практическое руководство. Изменить значение существующего параметра во время разработки](../../../../docs/framework/winforms/advanced/how-to-change-the-value-of-an-existing-setting-at-design-time.md)
