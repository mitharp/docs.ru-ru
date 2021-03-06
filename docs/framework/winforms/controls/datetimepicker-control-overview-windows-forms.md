---
title: Общие сведения об элементе управления DateTimePicker (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- DateTimePicker
helpviewer_keywords:
- DateTimePicker control [Windows Forms], about
- date and time picker controls
ms.assetid: 501af106-e9fc-4efc-b9b3-c9d8dcaf8c5c
ms.openlocfilehash: 956a14b13148b21fc83e372eeb4e7552c42db8d7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54694949"
---
# <a name="datetimepicker-control-overview-windows-forms"></a>Общие сведения об элементе управления DateTimePicker (Windows Forms)
Windows Forms <xref:System.Windows.Forms.DateTimePicker> управления позволяет пользователю выбрать один элемент из списка дат или времени. При использовании для представления даты, он отображается в виде двух частей: раскрывающегося списка с датой, представленных в текст и сетки, которая появляется, если щелкнуть стрелку вниз рядом со списком. Сетка выглядит аналогично <xref:System.Windows.Forms.MonthCalendar> элемент управления, который может использоваться для выбора нескольких дат. Дополнительные сведения о <xref:System.Windows.Forms.MonthCalendar> управления, см. в разделе [Обзор элемента управления MonthCalendar](../../../../docs/framework/winforms/controls/monthcalendar-control-overview-windows-forms.md).  
  
## <a name="key-properties"></a>Ключевые свойства  
 При желании <xref:System.Windows.Forms.DateTimePicker> для отображаются как элемент управления для выбора или изменение значений времени вместо даты, задайте <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> свойства `true` и <xref:System.Windows.Forms.DateTimePicker.Format%2A> свойства <xref:System.Windows.Forms.DateTimePickerFormat.Time>. Дополнительные сведения см. в практическом руководстве по [ Отображение времени с помощью элемента управления DateTimePicker](../../../../docs/framework/winforms/controls/how-to-display-time-with-the-datetimepicker-control.md).  
  
 Когда <xref:System.Windows.Forms.DateTimePicker.ShowCheckBox%2A> свойству `true`, отображаемого рядом с выбранной даты в элементе управления типа "флажок". Если флажок установлен, можно обновить выбранное значение даты и времени. Если этот флажок пуст, отображаемое значение недоступно.  
  
 Элемент управления <xref:System.Windows.Forms.DateTimePicker.MaxDate%2A> и <xref:System.Windows.Forms.DateTimePicker.MinDate%2A> определяют диапазон дат и времени. <xref:System.Windows.Forms.DateTimePicker.Value%2A> Свойство содержит текущую дату и время, элемент управления имеет значение. Дополнительные сведения см. в разделе [как: Отображение и ввод дат с помощью Windows Forms элемента управления DateTimePicker](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md). Значения могут отображаться в четырех форматов, которые задаются <xref:System.Windows.Forms.DateTimePicker.Format%2A> свойство: <xref:System.Windows.Forms.DateTimePickerFormat.Long>, <xref:System.Windows.Forms.DateTimePickerFormat.Short>, <xref:System.Windows.Forms.DateTimePickerFormat.Time>, или <xref:System.Windows.Forms.DateTimePickerFormat.Custom>. Если выбран пользовательский формат, необходимо задать <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> свойство соответствующую строку. Дополнительные сведения см. в разделе [как: Отображение даты в пользовательском формате с элемента управления DateTimePicker в Windows Forms](../../../../docs/framework/winforms/controls/display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md).  
  
## <a name="see-also"></a>См. также
- [Практическое руководство. Отображение даты в пользовательском формате с элемента управления DateTimePicker в Windows Forms](../../../../docs/framework/winforms/controls/display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)
- [Практическое руководство. Задайте и возвращаемого значения дат с помощью элемента управления DateTimePicker в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
