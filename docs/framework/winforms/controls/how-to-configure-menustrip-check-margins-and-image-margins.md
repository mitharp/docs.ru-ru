---
title: Как выполнить  Настройка объекта MenuStrip полей флажков и значков
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- margins [Windows Forms], setting in MenuStrip controls
- menus [Windows Forms], setting margins
- MenuStrip control [Windows Forms], configuring check and image margins
ms.assetid: 45a9075d-4bea-4ce2-9b2c-7619aa39f8ce
ms.openlocfilehash: ab606e126d346332f3da1ca1281372f3cce8f7ab
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219066"
---
# <a name="how-to-configure-menustrip-check-margins-and-image-margins"></a>Как выполнить  Настройка объекта MenuStrip полей флажков и значков
Элемент управления <xref:System.Windows.Forms.MenuStrip> можно настраивать, устанавливая свойства <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A> и <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A> в различных сочетаниях.   
  
## <a name="example"></a>Пример  
 В примере кода ниже показано, как установить и настроить поля флажков и значков для элемента управления <xref:System.Windows.Forms.ContextMenuStrip>. Для элементов управления <xref:System.Windows.Forms.ContextMenuStrip> и <xref:System.Windows.Forms.MenuStrip> процедура одинакова.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#60](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#60)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#60](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#60)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System, System.Drawing и System.Windows.Forms.  
  
 Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.ToolStripDropDown>
- [Элемент управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
- [Практическое руководство. Включение полей флажков и значков для элементов управления ContextMenuStrip](../../../../docs/framework/winforms/controls/how-to-enable-check-margins-and-image-margins-in-contextmenustrip-controls.md)
