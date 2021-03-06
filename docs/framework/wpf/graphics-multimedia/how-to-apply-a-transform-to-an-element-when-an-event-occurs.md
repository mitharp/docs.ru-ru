---
title: Как выполнить Применение преобразования к элементу при возникновении события
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], transformations as event responses
- properties [WPF], LayoutTransform
- transformations as event responses [WPF]
- properties [WPF], RenderTransform
- LayoutTransform property [WPF]
ms.assetid: 71e4327e-ca57-444c-a3cf-09fb381491a0
ms.openlocfilehash: 3862ffcb8e0dcabd2de67c495204470ac9fa6c14
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54726394"
---
# <a name="how-to-apply-a-transform-to-an-element-when-an-event-occurs"></a>Как выполнить Применение преобразования к элементу при возникновении события
В этом примере показано, как применить <xref:System.Windows.Media.ScaleTransform> при наступлении определенного события. Показанный подход аналогичен тому, который используется при применении других типов преобразований. Дополнительные сведения о доступных типах преобразований см. в разделе <xref:System.Windows.Media.Transform> класса или [Общие сведения о преобразованиях](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).  
  
 Преобразование можно применить к элементу любым из двух следующих способов:  
  
-   В этом случае *не* преобразование влияло на макет, используйте <xref:System.Windows.UIElement.RenderTransform%2A> свойство элемента.  
  
-   Если вы хотите, чтобы преобразование влияло на макет, используйте <xref:System.Windows.FrameworkElement.LayoutTransform%2A> свойство элемента.  
  
 В следующем примере применяется <xref:System.Windows.Media.ScaleTransform> для <xref:System.Windows.UIElement.RenderTransform%2A> свойства кнопки. При перемещении указателя мыши над кнопкой, <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> и <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> свойства <xref:System.Windows.Media.ScaleTransform> присваивается `2`, что приводит к увеличению кнопки. Когда указатель мыши покидает кнопку, <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> и <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> присваивается `1`, которое вызывает кнопки для возврата к исходному размеру.  
  
## <a name="example"></a>Пример  
 [!code-xaml[ButtonTransform#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml#1)]  
  
 [!code-csharp[ButtonTransform#1cb](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml.cs#1cb)]
 [!code-vb[ButtonTransform#1cb](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ButtonTransform/VisualBasic/ButtonTransformExample.xaml.vb#1cb)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.ScaleTransform>
- [Общие сведения о классах Transform](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
- [Разделы практического руководства](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
- [Общие сведения о перенаправленных событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
