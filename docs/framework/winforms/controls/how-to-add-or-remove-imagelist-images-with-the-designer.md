---
title: Как выполнить Добавление или удаление изображений из компонента ImageList с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
ms.openlocfilehash: f03ad1735d7da450d6ebc10c227e3f2bbb41a3d8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54688148"
---
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a>Как выполнить Добавление или удаление изображений из компонента ImageList с помощью конструктора
Можно добавить изображения для <xref:System.Windows.Forms.ImageList> компонент несколькими различными способами. Можно добавлять изображения очень быстро с помощью смарт-тег, связанный с <xref:System.Windows.Forms.ImageList>, или при установке на несколько других свойств <xref:System.Windows.Forms.ImageList>, может оказаться более удобным для добавления изображений в окне "Свойства". Также можно добавлять изображения с помощью кода. Дополнительные сведения о способах добавления изображений в коде см. в разделе [как: Добавление и удаление изображений с помощью Windows Forms компонента ImageList](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md). Обычно заполняется <xref:System.Windows.Forms.ImageList> компонент с изображениями, прежде чем он связан с элементом управления, но это не является обязательным.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-add-or-remove-images-by-using-the-properties-window"></a>Добавление или удаление изображений с помощью окна свойств  
  
1.  Выберите <xref:System.Windows.Forms.ImageList> компонента, или добавить его в форму.  
  
2.  В окне «Свойства» нажмите кнопку с многоточием (![экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) рядом с полем <xref:System.Windows.Forms.ImageList.Images%2A> свойство.  
  
3.  В **редактор коллекции изображений**, нажмите кнопку **добавить** или **удалить** на добавление и удаление изображений из списка.  
  
### <a name="to-add-or-remove-images-using-the-smart-tag"></a>Добавление и удаление изображений с помощью смарт-тег  
  
1.  Выберите <xref:System.Windows.Forms.ImageList> компонента, или добавить его в форму.  
  
2.  Щелкните глиф смарт-тега (![глиф смарт-тега](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))  
  
3.  В **задачи ImageList** выберите **выбрать рисунки**.  
  
4.  В **Editor Kolekce Images** щелкните **добавить** или **удалить** на добавление и удаление изображений из списка.  
  
## <a name="see-also"></a>См. также
- [Изображения, точечные рисунки и метафайлы](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
- [Пошаговое руководство: Выполнение типичных задач с помощью смарт-тегов в Windows Forms элементы управления](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md)
- [Компонент ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)
