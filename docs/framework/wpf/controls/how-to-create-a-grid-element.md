---
title: Как выполнить Создание элемента сетки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], creating [WPF], grid instance
ms.assetid: b2f07626-9df8-43b8-8d36-492f3cb42837
ms.openlocfilehash: b5bb9572b6a34b21208a8d8c0583068873772aae
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54726602"
---
# <a name="how-to-create-a-grid-element"></a>Как выполнить Создание элемента сетки
## <a name="example"></a>Пример  
 В следующем примере показано, как создать и использовать экземпляр <xref:System.Windows.Controls.Grid> либо при помощи [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] или кода. В этом примере используются три <xref:System.Windows.Controls.ColumnDefinition> объектов и три <xref:System.Windows.Controls.RowDefinition> объектов для создания сетки, который принимает девять ячеек, как в рабочем листе. Каждая ячейка содержит <xref:System.Windows.Controls.TextBlock> содержит элемент, который представляет данные, а верхняя строка <xref:System.Windows.Controls.TextBlock> с <xref:System.Windows.Controls.Grid.ColumnSpan%2A> свойства применен. Показать границы каждой ячейки, <xref:System.Windows.Controls.Grid.ShowGridLines%2A> включено свойство.  
  
 [!code-csharp[Grid#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Grid/CSharp/Grid_Code.cs#3)]
 [!code-vb[Grid#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Grid/VisualBasic/grid_vb.vb#3)]
 [!code-xaml[Grid#3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Grid/XAML/default.xaml#3)]  
  
  Любой из этих подходов создаст пользовательский интерфейс, который всегда выглядит практически так же, как показано ниже.

  ![Снимок экрана показан пользовательский интерфейс WPF, который содержит сетку разбить на три столбца.  Есть заголовок "2018 г. продукты поставляются» охват всех столбцов в верхней строке и содержит три столбца с показателями продаж для определенного квартала.  В нижней строке имеется текст, охватывающая два столбца с сообщением "Общее количество единиц: 300,000'](./media/how-to-create-a-grid-element/how-to-create-a-grid-element.png)
## <a name="see-also"></a>См. также
- <xref:System.Windows.Controls.Grid>
- [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)
