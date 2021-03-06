---
title: Общие сведения об элементе управления RadioButton (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- RadioButton
helpviewer_keywords:
- RadioButton control [Windows Forms], about RadioButton control
- RadioButton control [Windows Forms], determining state
- radio buttons [Windows Forms], determining state
- radio buttons [Windows Forms], about radio buttons
ms.assetid: cd11f0c2-d098-4022-adf9-1455bc166a13
ms.openlocfilehash: d07fd4028385dac25ae7413a54f72b331ab91eb6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54558401"
---
# <a name="radiobutton-control-overview-windows-forms"></a>Общие сведения об элементе управления RadioButton (Windows Forms)
Windows Forms <xref:System.Windows.Forms.RadioButton> элементов управления пользователь получает набор из двух или более взаимоисключающих вариантов. Переключатели и флажки могут показаться работают так же, является важным отличием: при выборе типа "переключатель", другие переключатели в той же группе, не могут быть выбраны также. Напротив можно выбрать любое количество флажки. Сообщает пользователю, определив группу переключателей, «Вот набор вариантов, которые можно выбрать один и только один».  
  
## <a name="using-the-control"></a>Использование элемента управления  
 Когда <xref:System.Windows.Forms.RadioButton> нажатии элемента управления, его <xref:System.Windows.Forms.RadioButton.Checked%2A> свойству `true` и <xref:System.Windows.Forms.Control.Click> вызывается обработчик события. <xref:System.Windows.Forms.RadioButton.CheckedChanged> События при значение <xref:System.Windows.Forms.RadioButton.Checked%2A> изменения свойств. Если <xref:System.Windows.Forms.RadioButton.AutoCheck%2A> свойству `true` (по умолчанию), если выбран переключатель всем другим элементам в группе очищаются автоматически. Это свойство обычно имеет значение только в `false` при использовании кода проверки для убедитесь, что этот переключатель — это допустимый параметр. Текст, отображаемый в элементе управления задается с помощью <xref:System.Windows.Forms.Control.Text%2A> свойство, которое может содержать клавиши быстрого доступа. Ключ доступа позволяет пользователю «click» элемента управления с помощью клавиши ALT ключом доступа. Дополнительные сведения см. в разделе [Как Определение клавиш доступа для Windows Forms, элементы управления](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md) и [как: Задать текст, отображаемый элементом управления форм Windows](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md).  
  
 <xref:System.Windows.Forms.RadioButton> Может отображаться как кнопка команд, который отображается при выбранном, если элемент управления <xref:System.Windows.Forms.RadioButton.Appearance%2A> свойству <xref:System.Windows.Forms.Appearance.Button>. Переключатели также можно выводить изображения с использованием <xref:System.Windows.Forms.ButtonBase.Image%2A> и <xref:System.Windows.Forms.ButtonBase.ImageList%2A> свойства. Дополнительные сведения см. в разделе [Как Задайте изображения, отображаемого элементом управления форм Windows](../../../../docs/framework/winforms/controls/how-to-set-the-image-displayed-by-a-windows-forms-control.md).  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.RadioButton>
- [Общие сведения об элементе управления Panel](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)
- [Общие сведения об элементе управления GroupBox](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md)
- [Общие сведения об элементе управления CheckBox](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)
- [Практическое руководство. Определение клавиш доступа для элементов управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)
- [Практическое руководство. Задать текст, отображаемый элементом управления форм Windows](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Практическое руководство. Группа элементов управления RadioButton Windows Forms выступать в качестве набора](../../../../docs/framework/winforms/controls/how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md)
- [Элемент управления RadioButton](../../../../docs/framework/winforms/controls/radiobutton-control-windows-forms.md)
