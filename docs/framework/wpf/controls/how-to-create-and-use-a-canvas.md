---
title: Как выполнить Создание и использование элемента Canvas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Canvas
- Canvas control [WPF], creating
- Canvas control [WPF], using
ms.assetid: 420b9487-9a15-477c-9489-a22a4dec7779
ms.openlocfilehash: d2d56851de2444ce246750688df67ed5ba9adb9a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54687483"
---
# <a name="how-to-create-and-use-a-canvas"></a>Как выполнить Создание и использование элемента Canvas
В этом примере показано, как создать и использовать экземпляр <xref:System.Windows.Controls.Canvas>.  
  
## <a name="example"></a>Пример  
 Следующий пример явным образом располагает два <xref:System.Windows.Controls.TextBlock> элементов с помощью <xref:System.Windows.Controls.Canvas.SetTop%2A> и <xref:System.Windows.Controls.Canvas.SetLeft%2A> методы <xref:System.Windows.Controls.Canvas>. В примере также назначается <xref:System.Windows.Controls.Control.Background%2A> цвет `LightSteelBlue` для <xref:System.Windows.Controls.Canvas>.  
  
> [!NOTE]
>  При использовании [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] позицию <xref:System.Windows.Controls.TextBlock> элементы, используют <xref:System.Windows.Controls.Canvas.Top%2A> и <xref:System.Windows.Controls.Canvas.Left%2A> свойства.  
  
 [!code-csharp[CanvasCode#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasCode/CSharp/Canvas_Code.cs#1)]
 [!code-vb[CanvasCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasCode/VisualBasic/canvas_vb.vb#1)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.TextBlock>
- <xref:System.Windows.Controls.Canvas.SetTop%2A>
- <xref:System.Windows.Controls.Canvas.SetLeft%2A>
- <xref:System.Windows.Controls.Canvas.Top%2A>
- <xref:System.Windows.Controls.Canvas.Left%2A>
- [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)
- [Разделы практического руководства](../../../../docs/framework/wpf/controls/canvas-how-to-topics.md)
