---
title: Как выполнить  Установка стилей ячейки по умолчанию и форматов данных для элемента управления DataGridView формы Windows с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], setting styles
- data formats
- data [Windows Forms], setting formats
ms.assetid: fc6da49f-8942-41da-b49f-b2afc38cc656
ms.openlocfilehash: 4a4cd1e7582e6e7443ceb1f4188eb3359638d8df
ms.sourcegitcommit: 0069cb3de8eed4e92b2195d29e5769a76111acdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/16/2019
ms.locfileid: "56332212"
---
# <a name="how-to-set-default-cell-styles-and-data-formats-for-the-windows-forms-datagridview-control-using-the-designer"></a>Как выполнить  Установка стилей ячейки по умолчанию и форматов данных для элемента управления DataGridView формы Windows с помощью конструктора
<xref:System.Windows.Forms.DataGridView> Элемент управления позволяет указать стилей ячейки по умолчанию и форматы данных для всего элемента управления, для определенных столбцов, для заголовков строк и столбцов и для чередующихся строк для создания эффекта книги ячейки. По умолчанию, установленным стилей для чередующихся строк и столбцов переопределены стили по умолчанию для всего элемента управления. Кроме того стили, заданные в коде для отдельных строк и ячеек, переопределяют стили по умолчанию.  
  
 Дополнительные сведения о стили ячеек, см. в разделе [стили ячеек элемента управления DataGridView Windows Forms в](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md). Установка стилей для чередующихся строк, см. в разделе [как: Установка стилей чередующихся строк для Windows Forms с помощью конструктора элемента управления DataGridView](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md).  
  
 Можно также задать с помощью стилей <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> свойства влияют на все строки, которые будут добавлены к элементу управления. Дополнительные сведения о шаблоне строк см. в разделе [как: Применение шаблонов строк для настройки отображения строк в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/use-the-row-template-to-customize-rows-in-the-datagrid.md).  
  
 Следующие процедуры требуют **приложения Windows** проекта с формой, содержащей <xref:System.Windows.Forms.DataGridView> элемента управления. Сведения о настройке такого проекта см. в разделе [как: Создайте проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) и [как: Добавление элементов управления в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-set-default-styles-for-all-cells-in-the-control"></a>Установка стилей по умолчанию для всех ячеек в элементе управления  
  
1.  Выберите <xref:System.Windows.Forms.DataGridView> управления в конструкторе.  
  
2.  В **свойства** окно, нажмите кнопку с многоточием (![экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) рядом с полем <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>, или <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> свойство. **Построителя CellStyle** откроется диалоговое окно.  
  
3.  Определите стиль путем установки свойств, используя **предварительной версии** панели, чтобы подтвердить выбранные параметры.  
  
> [!NOTE]
>  Если стили оформления включены, заголовки строк и столбцов (за исключением <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>) автоматически определяются текущей темой, переопределяя <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> и <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> значения свойств.  
>   
>  Можно задать стили ячеек для нескольких выбранных <xref:System.Windows.Forms.DataGridView> элементы управления в конструкторе, но только если они имеют одинаковые значения для свойства стиля ячейки, нужно внести изменения. Если стили ячеек, отличаются для этого свойства, **свойства** windows из **построителя CellStyle** диалоговое окно будет пустым.  
  
### <a name="to-set-default-styles-for-cells-in-individual-columns"></a>Установка стилей по умолчанию для ячеек в отдельных столбцах  
  
1.  Щелкните правой кнопкой мыши <xref:System.Windows.Forms.DataGridView> в конструкторе и выберите **Правка столбцов**.  
  
2.  Выберите столбец из **выбранные столбцы** списка.  
  
3.  В **свойства столбца** сетки, нажмите кнопку с многоточием (![экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) рядом с полем <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> свойство. **Построителя CellStyle** откроется диалоговое окно.  
  
4.  Определите стиль путем установки свойств, используя **предварительной версии** панели, чтобы подтвердить выбранные параметры.  
  
### <a name="to-format-data-in-cells"></a>Для форматирования данных в ячейках  
  
1.  Используйте один из приведенных выше процедур для отображения **построителя CellStyle** диалоговое окно, связанные со свойством стиль ячейки по умолчанию.  
  
2.  В **построителя CellStyle** диалоговом окне нажмите кнопку с многоточием (![экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) рядом с полем <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> свойство. **Строка формата** откроется диалоговое окно.  
  
3.  Выберите тип формата, а затем изменить сведения о типах (например, число десятичных разрядов), с помощью **пример** поле, чтобы подтвердить выбранные параметры.  
  
4.  При связывании <xref:System.Windows.Forms.DataGridView> элемента управления к источнику данных, которая, вероятнее всего содержать значения null, заполните **значение Null** текстовое поле. Это значение отображается в том случае, если значение ячейки равным пустой ссылкой (`Nothing` в Visual Basic) или <xref:System.DBNull.Value?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A?displayProperty=nameWithType>
- [Стили ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)
- [Практическое руководство. Установка стилей чередующихся строк для элемента управления DataGridView формы Windows с помощью конструктора](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md)
- [Практическое руководство. Создание проекта приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project).
- [Практическое руководство. Добавление элементов управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
