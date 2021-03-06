---
title: Как выполнить Определение прямоугольника с помощью RectangleGeometry
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rectangles
- rectangles [WPF], creating with RectangleGeometry class
ms.assetid: e40b8a8e-54b8-416b-a9f2-be6dca9fdf0b
ms.openlocfilehash: 9c57f1536065af0bca1f3752179547daa502c066
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54511650"
---
# <a name="how-to-define-a-rectangle-using-a-rectanglegeometry"></a>Как выполнить Определение прямоугольника с помощью RectangleGeometry
В этом примере описывается использование <xref:System.Windows.Media.RectangleGeometry> класс, который описывает прямоугольник.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как создать и отобразить <xref:System.Windows.Media.RectangleGeometry>.  Относительное положение и размеры прямоугольника определяются <xref:System.Windows.Rect> структуры. Относительное положение — `50,50` и высота и ширина — `25` создает квадрат. Прямоугольник закрашивается кистью <xref:System.Windows.Media.Brushes.LemonChiffon%2A> кисть и его контура отрисовывается с <xref:System.Windows.Media.Brushes.Black%2A> штриха с толщиной, равной `1`.  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 ![Практическое руководство](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rectangle.gif "graphicsmm_rectangle")  
RectangleGeometry  
  
 Несмотря на то, что в этом примере используется <xref:System.Windows.Shapes.Path> элемента для визуализации <xref:System.Windows.Media.RectangleGeometry>, существует много способов использовать <xref:System.Windows.Media.RectangleGeometry> объектов. Например <xref:System.Windows.Media.RectangleGeometry> может использоваться для указания <xref:System.Windows.UIElement.Clip%2A> из <xref:System.Windows.UIElement> или <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> из <xref:System.Windows.Media.GeometryDrawing>.  
  
 Другие простые геометрические классы включают <xref:System.Windows.Media.LineGeometry> и <xref:System.Windows.Media.EllipseGeometry>. Эти геометрические объекты, а также более сложные, могут также создаваться с использованием <xref:System.Windows.Media.PathGeometry> или <xref:System.Windows.Media.StreamGeometry>.  
  
## <a name="see-also"></a>См. также
- [Общие сведения о классе Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
- [Создание составной фигуры](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)
- [Создание фигуры с помощью объекта PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
