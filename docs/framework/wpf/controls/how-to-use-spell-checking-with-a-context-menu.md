---
title: Как выполнить Использование проверки орфографии при помощи контекстного меню
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- enabling spell checking in a text box [WPF]
- reenabling spell checking in a text box [WPF]
- spell checking with a context menu [WPF]
ms.assetid: 61f69a20-2ff3-4056-9060-e32f4483ec5e
ms.openlocfilehash: 2b6790fd4d5d2e322a46bd98ed19e7b88c4923c4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54713120"
---
# <a name="how-to-use-spell-checking-with-a-context-menu"></a>Как выполнить Использование проверки орфографии при помощи контекстного меню
По умолчанию при включении орфографии в элементе управления редактирования, такие как <xref:System.Windows.Controls.TextBox> или <xref:System.Windows.Controls.RichTextBox>, можно выбрать варианты правописания в контекстном меню. Например, если пользователи неправильно написанное слово, щелкните правой кнопкой мыши, они получают набор вариантов правописания или возможность **пропустить все**. Тем не менее при переопределении отобразится контекстное меню по умолчанию с собственного пользовательского контекстного меню, эта функция теряется, и вам нужно написать код, чтобы включить средство проверки орфографии в контекстном меню. В следующем примере показано, как включить эту функцию для <xref:System.Windows.Controls.TextBox>.  
  
## <a name="example"></a>Пример  
 В следующем примере показан [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , создающий <xref:System.Windows.Controls.TextBox> с некоторые события, которые используются для реализации контекстного меню.  
  
 [!code-xaml[TextBoxMiscSnippets_snip#SpellerCustomContextMenuExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml#spellercustomcontextmenuexamplewholepage)]  
  
## <a name="example"></a>Пример  
 Следующий пример показывает код, который реализует в контекстном меню.  
  
 [!code-csharp[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml.cs#spellercustomcontextmenucodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/speller_custom_context_menu.xaml.vb#spellercustomcontextmenucodeexamplewholepage)]  
  
 Код, используемый для этого с помощью <xref:System.Windows.Controls.RichTextBox> похож. Основное различие состоит в параметр, передаваемый `GetSpellingError` метод. Для <xref:System.Windows.Controls.TextBox>, передайте целочисленный индекс положения курсора:  
  
 `spellingError = myTextBox.GetSpellingError(caretIndex);`  
  
 Для <xref:System.Windows.Controls.RichTextBox>, передайте <xref:System.Windows.Documents.TextPointer> , указывающий положение курсора:  
  
 `spellingError = myRichTextBox.GetSpellingError(myRichTextBox.CaretPosition);`  
  
## <a name="see-also"></a>См. также
- [Общие сведения о TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)
- [Общие сведения о RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
- [Включение проверки орфографии в элементе управления редактирования текста](../../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md)
- [Использование пользовательского контекстного меню с элементом TextBox](../../../../docs/framework/wpf/controls/how-to-use-a-custom-context-menu-with-a-textbox.md)
