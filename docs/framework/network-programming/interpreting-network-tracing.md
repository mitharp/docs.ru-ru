---
title: Интерпретация сетевой трассировки
ms.date: 03/30/2017
helpviewer_keywords:
- TraceMode attribute
- hexidecimal data, network tracing output
- network tracing, analyzing
- protocolonly
- text, network tracing output
- includehex
ms.assetid: ad22b4b8-00af-4778-9cca-cb609ce1f8ff
ms.openlocfilehash: 8813bf68ee2b354ed7fc5e981904b8e4b807c1be
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54576529"
---
# <a name="interpreting-network-tracing"></a>Интерпретация сетевой трассировки
Если включена трассировка сети, ее можно использовать для записи вызовов, осуществляемых приложением к различным членам класса <xref:System.Net>. Выходные данные этих вызовов могут быть аналогичны приведенным далее.  
  
```  
[588]   (4357)   Entering Socket#33574638::Send()  
[588]   (4387)   Exiting Socket#33574638::Send()-> 61#61  
```  
  
 В приведенном выше примере [588] — уникальный идентификатор текущего потока. (4357) и (4387) — метки времени, обозначающие количество миллисекунд, прошедших с момента запуска приложения. Данные, которые идут за меткой времени, указывают на приложение, начинающее и завершающее метод **Socket.Send**. Объект, выполняющий метод **Send**, имеет уникальный идентификатор 33574638. Трассировка завершения метода содержит возвращаемое значение (61 в предыдущем примере).  
  
 Сетевая трассировка может записывать сетевой трафик, отправленный из приложения или полученный им с помощью протоколов уровня приложения, таких как HTTP. Эти данные могут захватываться как текст и шестнадцатеричные данные. Шестнадцатеричные данные доступны при указании **includehex** в качестве значения атрибута **tracemode**. (Подробные сведения об этом атрибуте см. в разделе [Практическое руководство. Настройка трассировки сети](../../../docs/framework/network-programming/how-to-configure-network-tracing.md).) Следующий пример трассировки был создан с помощью **includehex**.  
  
 `[1692]   (1142)   00000000 : 47 45 54 20 2F 77 70 61-64 2E 64 61 74 20 48 54 : GET /wpad.dat HT`  
  
 `[1692]   (1142)   00000010 : 54 50 2F 31 2E 31 0D 0A-48 6F 73 74 3A 20 69 74 : TP/1.1..Host: it`  
  
 `[1692]   (1142)   00000020 : 67 70 72 6F 78 79 0D 0A-43 6F 6E 6E 65 63 74 69 : gproxy..Connecti`  
  
 `[1692]   (1142)   00000030 : 6F 6E 3A 20 43 6C 6F 73-65 0D 0A 0D 0A     : on: Close....`  
  
 Чтобы опустить шестнадцатеричные данные, укажите **protocolonly** в качестве значения атрибута **tracemode**. В следующем примере показана трассировка с указанным значением **protocolonly**.  
  
 `[2444]   (594)   Data from ConnectStream#33574638::WriteHeaders<<GET /wpad.dat HTTP/1.1`  
  
 `Host: itgproxy`  
  
 `Connection: Close`  
  
## <a name="see-also"></a>См. также
- [Включение трассировки сети](../../../docs/framework/network-programming/enabling-network-tracing.md)
- [Практическое руководство. Настройка трассировки сети](../../../docs/framework/network-programming/how-to-configure-network-tracing.md)
- [Трассировка сети в .NET Framework](../../../docs/framework/network-programming/network-tracing.md)
