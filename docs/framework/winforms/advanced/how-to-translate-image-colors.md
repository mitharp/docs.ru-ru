---
title: Как выполнить Преобразование цветов изображения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], changing colors
- images [Windows Forms], changing colors
- image colors [Windows Forms]
ms.assetid: 2106fb9a-4d60-4dcf-9220-9f189a6c4d19
ms.openlocfilehash: 7a3ed1f3f6b3e89c8df160b7e753839e20acd877
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549763"
---
# <a name="how-to-translate-image-colors"></a>Как выполнить Преобразование цветов изображения
Перевод добавляет значение к одному или нескольким из четырех компонентов цвета. В следующей таблице приведены элементы матрицы цветов, представляющих переводы.  
  
|Преобразуемый компонент|Элемент матрицы|  
|--------------------------------|------------------|  
|Красный|[4][0]|  
|Зеленый|[4][1]|  
|Синий|[4][2]|  
|Коэффициент альфа|[4][3]|  
  
## <a name="example"></a>Пример  
 В следующем примере создается <xref:System.Drawing.Image> объекта из файла ColorBars.bmp. Затем код добавляет 0,75 красного компонента каждого пикселя в изображении. Исходное изображение отображается вместе с преобразованные изображения.  
  
 Ниже показан исходное изображение в левой части и преобразованные изображения справа.  
  
 ![Преобразование цветов](../../../../docs/framework/winforms/advanced/media/colortrans2.png "colortrans2")  
  
 Ниже перечислены эти векторы четырех полос до и после преобразования. Обратите внимание на то, что так как максимальное значение для компонента цвета равно 1, красный компонент во второй строке остается неизменным. (Аналогичным образом, минимальное значение для компонента цвета — 0).  
  
|До преобразования|Перевод|  
|--------------|----------------|  
|Черный (0, 0, 0, 1)|(0.75, 0, 0, 1)|  
|Красный (1, 0, 0, 1)|(1, 0, 0, 1)|  
|Зеленый (0, 1, 0, 1)|(0.75, 1, 0, 1)|  
|Синий (0, 0, 1, 1)|(0.75, 0, 1, 1)|  
  
 [!code-csharp[System.Drawing.RecoloringImages#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.RecoloringImages#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчик событий. Замените `ColorBars.bmp` в вашей системе путь и имя файла изображения.  
  
## <a name="see-also"></a>См. также
- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
- [перекрашивание изображений](../../../../docs/framework/winforms/advanced/recoloring-images.md)
