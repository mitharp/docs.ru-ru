---
title: Как выполнить Получение уведомления об изменении с помощью компонента BindingSource и интерфейса INotifyPropertyChanged
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- change notifications [Windows Forms], raising
- BindingSource component [Windows Forms], and IPropertyChange
- data sources [Windows Forms], detecting changes
- examples [Windows Forms], BindingSource component
- change notifications
- INotifyPropertyChanged interface [Windows Forms], using with BindingSource
- BindingSource component [Windows Forms], examples
ms.assetid: 7fa2cf51-c09f-4375-adf0-e36c5617f099
ms.openlocfilehash: cf6f39154b7b896a835bda7f946134fbff8dbe17
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54543962"
---
# <a name="how-to-raise-change-notifications-using-a-bindingsource-and-the-inotifypropertychanged-interface"></a>Как выполнить Получение уведомления об изменении с помощью компонента BindingSource и интерфейса INotifyPropertyChanged
Компонент <xref:System.Windows.Forms.BindingSource> автоматически обнаруживает изменения в источнике данных, когда тип, содержащийся в этом источнике, реализует интерфейс <xref:System.ComponentModel.INotifyPropertyChanged> и вызывает события <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> при изменении значения свойства. Это очень удобно, так как элементы управления, привязанные к <xref:System.Windows.Forms.BindingSource>, будут автоматически обновляться при изменении значений источника данных.  
  
> [!NOTE]
>  Если источник данных реализует <xref:System.ComponentModel.INotifyPropertyChanged> и выполняются асинхронные операции, не следует вносить изменения в источник данных в фоновом потоке. Вместо этого рекомендуется считывать данные в фоновом потоке и объединять их в список в потоке пользовательского интерфейса.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показан пример простой реализации интерфейса <xref:System.ComponentModel.INotifyPropertyChanged>. Также показано, как компонент <xref:System.Windows.Forms.BindingSource> автоматически передает изменения источника данных в связанный элемент управления, когда <xref:System.Windows.Forms.BindingSource> привязан к списку типа <xref:System.ComponentModel.INotifyPropertyChanged>.  
  
 При использовании атрибута `CallerMemberName` в вызовах метода `NotifyPropertyChanged` нет необходимости указывать имя свойства в качестве строкового аргумента. Дополнительные сведения см. в разделе [сведения о вызывающем объекте](https://msdn.microsoft.com/library/9cb2b8c0-c4f6-44b8-9c90-38948455b373).  
  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System, System.Data, System.Drawing и System.Windows.Forms.  
  
 Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект. Также см. раздел [Как Компиляция и выполнение примера кода завершения Windows Forms с помощью Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb129228(v=vs.100)).  
  
## <a name="see-also"></a>См. также
- <xref:System.ComponentModel.INotifyPropertyChanged>
- [Компонент BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component.md)
- [Практическое руководство. Получение уведомления об изменении, с использованием метода ResetItem компонента BindingSource](../../../../docs/framework/winforms/controls/how-to-raise-change-notifications-using-the-bindingsource-resetitem-method.md)
