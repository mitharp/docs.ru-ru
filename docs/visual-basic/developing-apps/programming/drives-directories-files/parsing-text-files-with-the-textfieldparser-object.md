---
title: Анализ текстовых файлов с помощью объекта TextFieldParser (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- TextFieldParser object, using
- I/O [Visual Basic], parsing files
- files [Visual Basic], parsing
ms.assetid: fc31d6e6-af0c-403f-8a00-d556b2c57567
ms.openlocfilehash: 09821e9b1985913b7433b070ae19c4818265926e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54585406"
---
# <a name="parsing-text-files-with-the-textfieldparser-object-visual-basic"></a>Анализ текстовых файлов с помощью объекта TextFieldParser (Visual Basic)
Объект `TextFieldParser` позволяет анализировать и обрабатывать файлы очень большого размера, по своей структуре имеющие вид столбцов текста с разделителями, например файлы журнала или старые базы данных. Анализ текстового файла с помощью объекта `TextFieldParser` похож на итерацию содержимого текстового файла, а метод анализа, связанный с извлечением полей текста, напоминает методы работы со строками, используемые для маркировки разделенных строк.  
  
## <a name="parsing-different-types-of-text-files"></a>Анализ различных типов текстовых файлов  
 Текстовые файлы могут иметь поля различной ширины, разделенные тем или иными символом, например запятой или знаком табуляции. Определите `TextFieldType` и разделитель, как в следующем примере, в котором с помощью метода `SetDelimiters` определяется текстовый файл со знаком табуляции в качестве разделителя:  
  
 [!code-vb[VbVbalrTextFieldParser#21](../../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/parsing-text-files-with-the-textfieldparser-object_1.vb)]  
  
 Другие текстовые файлы могут иметь поля фиксированной ширины. В этом случае необходимо определить `TextFieldType` как `FixedWidth` и задать ширину каждого поля, как в примере ниже. В этом примере столбцы текста определяются с помощью метода `SetFieldWidths`: первый столбец имеет ширину 5 символов, второй — 10, третий — 11, а четвертый столбец имеет переменную ширину.  
  
 [!code-vb[VbVbalrTextFieldParser#22](../../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/parsing-text-files-with-the-textfieldparser-object_2.vb)]  
  
 После определения формата можно обработать весь файл в цикле, используя для обработки каждой строки метод `ReadFields`.  
  
 Если поле не соответствует указанному формату, создается исключение <xref:Microsoft.VisualBasic.FileIO.MalformedLineException>. При возникновении таких исключений в свойства `ErrorLine` и `ErrorLineNumber` записывается текст, вызвавший исключение, и номер строки, в которой находится этот текст.  
  
## <a name="parsing-files-with-multiple-formats"></a>Анализ файлов с содержимым в нескольких форматах  
 Метод `PeekChars` объекта `TextFieldParser` можно использовать для проверки каждого поля до его чтения, что позволяет определить несколько форматов для полей и отреагировать соответствующим образом. Дополнительные сведения см. в разделе [Как Чтение из текстовых файлов различных форматов](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md).  
  
## <a name="see-also"></a>См. также
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFieldParser%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.PeekChars%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ReadFields%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.CommentTokens%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLineNumber%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.FieldWidths%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.HasFieldsEnclosedInQuotes%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.LineNumber%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TextFieldType%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TrimWhiteSpace%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetFieldWidths%2A>
