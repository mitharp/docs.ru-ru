---
title: Расширение разметки TemplateBinding
ms.date: 03/30/2017
f1_keywords:
- TemplateBinding
- TemplateBindingExtension
helpviewer_keywords:
- XAML [WPF], TemplateBinding markup extension
- TemplateBinding markup extensions [WPF]
ms.assetid: 1d25bbfc-dbc2-499d-9f12-419d23d4ac6a
ms.openlocfilehash: 3ae17dc98137bd417d2468fb0415fb2078acf20f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54686027"
---
# <a name="templatebinding-markup-extension"></a>Расширение разметки TemplateBinding
Связывает значение свойства в шаблоне элемента управления со значением другого свойства элемента управления-шаблона.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```xml  
<object property="{TemplateBinding sourceProperty}" .../>  
```  
  
## <a name="xaml-attribute-usage-for-setter-property-in-template-or-style"></a>Использование атрибута XAML (для свойства Setter в шаблоне или стиле)  
  
```xml  
<Setter Property="propertyName" Value="{TemplateBinding sourceProperty}" .../>  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|`propertyName`|<xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType> для свойства задается в синтаксисе метода задания значения.|  
|`sourceProperty`|Другое свойство зависимостей для типа, который используется в качестве шаблона, задается с помощью <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType>.<br /><br /> -или-<br /><br /> "Краткое" имя свойства, которое определяется типом, отличным от целевого шаблонного типа. Фактически это <xref:System.Windows.PropertyPath>. См. в разделе [синтаксис PropertyPath XAML](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md).|  
  
## <a name="remarks"></a>Примечания  
 Объект `TemplateBinding` является оптимизированной формой [привязки](../../../../docs/framework/wpf/advanced/binding-markup-extension.md) для сценариев шаблонов, аналогично `Binding` создан с параметром `{Binding RelativeSource={RelativeSource TemplatedParent}}`. `TemplateBinding` всегда является односторонней привязкой, даже если используемые свойства по умолчанию используют двустороннюю привязку. Оба используемых свойства должны быть свойствами зависимостей. Чтобы добиться двухстороннюю привязку для шаблонного родительского элемента следующая инструкция привязки вместо этого используйте `{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=TwoWay, Path=MyDependencyProperty}`. 
  
 [RelativeSource](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md) является еще одним расширением разметки, которое иногда используется в сочетании с или instead of `TemplateBinding` для выполнения относительной привязки свойства в шаблоне.  
  
 Шаблоны элементов управления в качестве концепции здесь нет; Дополнительные сведения см. в разделе [управления стили и шаблоны](../../../../docs/framework/wpf/controls/control-styles-and-templates.md).  
  
 Синтаксис атрибутов является наиболее распространенным синтаксисом, используемым с этим расширением разметки. Строковая лексема, указываемая после строки идентификатора `TemplateBinding`, присваивается в качестве значения <xref:System.Windows.TemplateBindingExtension.Property%2A> соответствующего класса расширения <xref:System.Windows.TemplateBindingExtension>.  
  
 Синтаксис элемента объекта возможен, но он не рассматривается из-за отсутствия практического применения. `TemplateBinding` используется для заполнения значений в методах установки значений с помощью вычисленных выражений. Использование синтаксиса элемента объекта для `TemplateBinding` для заполнения синтаксиса элемента свойства `<Setter.Property>` является излишним.  
  
 Излишним может оказаться и использование `TemplateBinding` в атрибуте, в котором свойство <xref:System.Windows.TemplateBindingExtension.Property%2A> определено как пара "свойство=значение".  
  
```xml  
<object property="{TemplateBinding Property=sourceProperty}" .../>  
```  
  
 Подробное определение зачастую удобно использовать для расширений, которые имеют несколько устанавливаемых свойств, а также в том случае, если некоторые свойства являются необязательными. Так как `TemplateBinding` имеет только одно устанавливаемое свойство, которое является обязательным, это использование не является типичным.  
  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] реализации обработчика XAML обработка данного расширения разметки определяется <xref:System.Windows.TemplateBindingExtension> класса.  
  
 `TemplateBinding` является расширением разметки. Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами. Все расширения разметки в XAML используют `{` и `}` символов в синтаксисе их атрибутов, который является соглашением, по которому обработчик XAML узнает, что расширение разметки должно обработать атрибут. Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Style>
- <xref:System.Windows.Controls.ControlTemplate>
- [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)
- [Общие сведения о языке XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
- [Расширения разметки и XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
- [Расширение разметки RelativeSource](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md)
- [Привязка расширения разметки](../../../../docs/framework/wpf/advanced/binding-markup-extension.md)
