---
title: Стили и шаблоны элемента Slider
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Slider
- states [WPF], Slider
- Slider [WPF], styles and templates
- styles [WPF], Slider
- templates [WPF], Slider
- ControlTemplate [WPF], Slider
ms.assetid: d89aa97b-075a-4752-9c41-9679df65c491
ms.openlocfilehash: 3b56b26716eb2ffc0a776085579c4d5df09e3ace
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54596258"
---
# <a name="slider-styles-and-templates"></a>Стили и шаблоны элемента Slider
В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.Slider> элемента управления. Вы можете изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> предоставить уникальный внешний вид элемента управления. Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="slider-parts"></a>Ползунок частей  
 В следующей таблице перечислены именованные части <xref:System.Windows.Controls.Slider> элемента управления.  
  
|Отделение|Тип|Описание|  
|-|-|-|  
|PART_Track|<xref:System.Windows.Controls.Primitives.Track>|Контейнер для элемента, который указывает положение <xref:System.Windows.Controls.Slider>.|  
|PART_SelectionRange|<xref:System.Windows.FrameworkElement>|Элемент, отображаемый диапазон выбора вдоль <xref:System.Windows.Controls.Slider>.  Диапазон выбора отображается только если <xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A> свойство `true`.|  
  
## <a name="slider-states"></a>Состояния "ползунок"  
 В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Slider> элемента управления.  
  
|Имя VisualState|Имя VisualStateGroup|Описание:|  
|----------------------|---------------------------|-----------------|  
|Норм.|CommonStates|Состояние по умолчанию.|  
|MouseOver|CommonStates|Указатель мыши расположен над элементом управления.|  
|Отключено|CommonStates|Элемент управления отключен.|  
|Focused|FocusStates|Элемент управления имеет фокус.|  
|Без фокуса ввода|FocusStates|Элемент управления не имеет фокуса.|  
|Valid|ValidationStates|Элемент управления использует <xref:System.Windows.Controls.Validation> класс и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенное свойство `false`.|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления не имеет фокуса.|  
  
## <a name="slider-controltemplate-example"></a>Пример шаблона элемента управления "ползунок"  
 В следующем примере показано определение <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Slider> элемента управления.  
  
 [!code-xaml[ControlTemplateExamples#Slider](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#slider)]  
  
 В предыдущем примере используется один или несколько из следующих ресурсов.  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Стили и шаблоны элемента управления](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)
- [Настройка элементов управления](../../../../docs/framework/wpf/controls/control-customization.md)
- [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)
- [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
