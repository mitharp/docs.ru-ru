---
title: Как выполнить Отправка строк в последовательный порт в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- ports, sending strings to
- strings [Visual Basic], sending to serial ports
- My.Computer.Ports object
- serial ports, sending strings to
ms.assetid: 6ebf46cd-b2d0-4b2c-9a1f-be177b22ad52
ms.openlocfilehash: b2ba25f4ca3f63e1e7831d26745fa35cd337dc48
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54503031"
---
# <a name="how-to-send-strings-to-serial-ports-in-visual-basic"></a>Как выполнить Отправка строк в последовательный порт в Visual Basic
В этом разделе описывается, как использовать `My.Computer.Ports` для отправки строк в последовательные порты компьютера в Visual Basic.  
  
## <a name="example"></a>Пример  
 Этот пример кода отправляет строку в последовательный порт COM1. Возможно, на вашем компьютере потребуется использовать другой последовательный порт.  
  
 Воспользуйтесь методом `My.Computer.Ports.OpenSerialPort`, чтобы получить ссылку на порт. Для получения дополнительной информации см. <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.  
  
 Блок `Using` позволяет приложению закрыть последовательный порт даже в том случае, если он создает исключение. В блоке `Try...Catch...Finally` должен отображаться весь код, управляющий последовательным портом.  
  
 Метод <xref:System.IO.Ports.SerialPort.WriteLine%2A> отправляет данные в последовательный порт.  
  
 [!code-vb[VbVbalrMyComputer#33](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-send-strings-to-serial-ports_1.vb)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
-   В этом примере предполагается, что компьютер использует `COM1`.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 В этом примере предполагается, что компьютер использует `COM1`. Для большей гибкости код должен позволять пользователю выбирать нужный последовательный порт из списка доступных портов. Дополнительные сведения см. в разделе [Как Отображение доступных последовательных портов](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).  
  
 В этом примере блок `Using` позволяет сделать так, чтобы приложение закрыло порт, даже если он создает исключение. Дополнительные сведения см. в разделе [Оператор using](../../../../visual-basic/language-reference/statements/using-statement.md).  
  
## <a name="see-also"></a>См. также
- <xref:Microsoft.VisualBasic.Devices.Ports>
- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
- [Практическое руководство. Дозвон при помощи модема, подключенного к последовательному порту компьютера](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)
- [Практическое руководство. Отображение доступных последовательных портов](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)
