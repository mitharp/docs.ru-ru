---
title: Как выполнить Применение преобразования к тексту
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], rotated text
- typography [WPF], scaled text
- skewed text [WPF]
- typography [WPF], translated text
- typography [WPF], shadowed text
- rotated text [WPF]
- translated text [WPF]
- shadowed text [WPF]
- transforms in text [WPF]
- typography [WPF], transforms
- scaled text [WPF]
- typography [WPF], skewed text
ms.assetid: 0d61678a-4185-4f2a-85c6-c1d020f96fa0
ms.openlocfilehash: 7737a2e01ddfe2a639426bbced643d8f78961207
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54740554"
---
# <a name="how-to-apply-transforms-to-text"></a>Как выполнить Применение преобразования к тексту
Преобразования могут менять отображение текста в приложении. В следующих примерах используются различные типы преобразований отрисовки влияющие на отображение текста в <xref:System.Windows.Controls.TextBlock> элемента управления.  
  
## <a name="example"></a>Пример  
 В следующем примере показан текст, повернутый относительно заданной точки в двухмерной плоскости x-y.  
  
 ![Текст, повернутый с использованием RotateTransform](../../../../docs/framework/wpf/advanced/media/transformedtext01.jpg "TransformedText01")  
Пример текста, повернутого на 90 градусов  
  
 В следующем примере кода используется <xref:System.Windows.Media.RotateTransform> вращение текста. <xref:System.Windows.Media.RotateTransform.Angle%2A> Значение 90, поворачивает элемент на 90 градусов по часовой стрелке.  
  
 [!code-xaml[TextTransformSample#TextTransformSample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample1)]  
  
 В следующем примере показаны вторая строка текста, масштабированная на 150 % вдоль оси X, и третья строка текста, масштабированная на 150 % вдоль оси Y.  
  
 ![Текст, масштабируемый с использованием ScaleTransform](../../../../docs/framework/wpf/advanced/media/transformedtext02.jpg "TransformedText02")  
Пример масштабированного текста  
  
 В следующем примере кода используется <xref:System.Windows.Media.ScaleTransform> для масштабирования текста из исходного размера.  
  
 [!code-xaml[TextTransformSample#TextTransformSample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample2)]  
  
> [!NOTE]
>  Масштабирование текста не равнозначно увеличению шрифта текста. Размеры шрифта рассчитываются независимо друг от друга, чтобы обеспечить оптимальное разрешение для разных размеров. В масштабированном тексте, с другой стороны, сохранены пропорции текста исходного размера.  
  
 В следующем примере показан текст, наклоненный вдоль оси X.  
  
 ![Текст, наклоненный с использованием SkewTransform](../../../../docs/framework/wpf/advanced/media/transformedtext03.jpg "TransformedText03")  
Пример наклоненного текста  
  
 В следующем примере кода используется <xref:System.Windows.Media.SkewTransform> для наклона текста. Отклонение (или срез) — это преобразование, которое неравномерно растягивает пространство координат. В этом примере две текстовые строки, наклоненные на –30° и 30° вдоль оси X.  
  
 [!code-xaml[TextTransformSample#TextTransformSample3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample3)]  
  
 В следующем примере показан текст, преобразованный (или перемещенный) вдоль осей X и Y.  
  
 ![Смещение текста с использованием TranslateTransform](../../../../docs/framework/wpf/advanced/media/transformedtext04.jpg "TransformedText04")  
Пример преобразованного текста  
  
 В следующем примере кода используется <xref:System.Windows.Media.TranslateTransform> для смещения текста. В этом примере слегка смещенная копия текста под основным текстом создает эффект тени.  
  
 [!code-xaml[TextTransformSample#TextTransformSample4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample4)]  
  
> [!NOTE]
>  <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> Предоставляет широкий набор функций для создания эффектов тени. Дополнительные сведения см. в разделе [Создание текста с тенью](../../../../docs/framework/wpf/advanced/how-to-create-text-with-a-shadow.md).  
  
## <a name="see-also"></a>См. также
- [Применение анимаций к тексту](../../../../docs/framework/wpf/advanced/how-to-apply-animations-to-text.md)
