---
title: Как выполнить Добавление в WPF-приложение экрана-заставки
ms.date: 08/18/2018
helpviewer_keywords:
- WPF [WPF], splash screen
- startup window [WPF]
- SplashScreen class [WPF]
- splash screen [WPF]
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
ms.openlocfilehash: 545fce07d0fab3dca8116f2cacfc068b62cbbde2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54537547"
---
# <a name="how-to-add-a-splash-screen-to-a-wpf-application"></a>Как выполнить Добавление в WPF-приложение экрана-заставки

В этом разделе показано, как добавить окно запуска, или *экран-заставка*, приложение Windows Presentation Foundation (WPF).

## <a name="to-add-an-existing-image-as-a-splash-screen"></a>Чтобы добавить существующий образ в качестве экрана-заставки

1.  Создайте или найдите изображение, которое будет использоваться для экрана-заставки. Можно использовать любой формат изображения, который поддерживается в Windows Imaging Component (WIC). Например можно использовать формат BMP, GIF, JPEG, PNG и TIFF.

2.  Добавьте файл изображения в проект приложения WPF.

3.  В **обозревателе решений**, выберите изображение.

4.  В окне «Свойства» щелкните стрелку раскрывающегося списка для **действие при построении** свойство.

5.  Выберите **экран-заставка** из раскрывающегося списка.

6.  Нажмите клавишу **F5**, чтобы выполнить сборку приложения и запустить его.

     Изображение экрана-заставки отображается в центре экрана, исчезнет, когда появится окно основного приложения.

## <a name="to-exclude-the-splash-screen-from-build"></a>Чтобы исключить из сборки на экране-заставке

1.  В **обозревателе решений**, выберите изображение экрана-заставки.

2.  В **свойства** окне **действие при построении** для **None**.

## <a name="to-remove-the-splash-screen-from-an-application"></a>Для удаления заставки из приложения

В **обозревателе решений**, удалить изображение экрана-заставки.

## <a name="see-also"></a>См. также

- <xref:System.Windows.SplashScreen>
- [Практическое руководство. Добавление существующих элементов в проект](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))
