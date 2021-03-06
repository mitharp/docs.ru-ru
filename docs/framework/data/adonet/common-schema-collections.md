---
title: Общие коллекции схемы
ms.date: 03/30/2017
ms.assetid: 50127ced-2ac8-4d7a-9cd1-5c98c655ff03
ms.openlocfilehash: dfd1e28a117ca71cac6c792058c1aeb17a0c4f69
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700966"
---
# <a name="common-schema-collections"></a>Общие коллекции схемы
Стандартные коллекции схем - это коллекции схем, реализуемые каждым из управляемых поставщиков .NET Framework. Можно запросить управляемый поставщик .NET Framework для определения списка поддерживаемых коллекций схем, вызвав **GetSchema** метода без аргументов или с именем коллекции схем «MetaDataCollections». При этом будет возвращена <xref:System.Data.DataTable> со списком поддерживаемых коллекций схем, число ограничений, которые каждая из них поддерживает, и число идентификационных частей, которые в них используются. Данные коллекции описывают все требуемые столбцы. По желанию в поставщиках может быть предусмотрено добавление дополнительных столбцов. Например, поставщики `SqlClient` и `OracleClient` добавляют к коллекции ограничений столбец ParameterName.  
  
 Если поставщик не может определить значение требуемого столбца, то он возвращает значение NULL.  
  
 Дополнительные сведения об использовании **GetSchema** методы, см. в разделе [коллекции GetSchema и Schema](../../../../docs/framework/data/adonet/getschema-and-schema-collections.md).  
  
## <a name="metadatacollections"></a>Коллекция схем MetaDataCollections  
 Данная коллекция схем предоставляет сведения обо всех коллекциях схем, поддерживаемых управляемым поставщиком .NET Framework, который используется в настоящее время для подключения к базе данных.  
  
|ColumnName|DataType|Описание|  
|----------------|--------------|-----------------|  
|CollectionName|string|Имя коллекции, передаваемое **GetSchema** метода для возврата коллекции.|  
|NumberOfRestrictions|int|Число ограничений, которые могут быть указаны для коллекции.|  
|NumberOfIdentifierParts|int|Число частей в составном имени идентификатора и (или) объекта базы данных. Например, в SQL Server такое число частей может быть равным 3 для таблиц и 4 - для столбцов. В Oracle оно может быть равным 2 для таблиц и 3 - для столбцов.|  
  
## <a name="datasourceinformation"></a>Коллекция схем DataSourceInformation  
 Данная коллекция схем предоставляет сведения об источнике данных, к которому в данный момент подключен управляемый поставщик .NET Framework.  
  
|ColumnName|DataType|Описание|  
|----------------|--------------|-----------------|  
|CompositeIdentifierSeparatorPattern|string|Регулярное выражение служит для согласования составных разделителей в составном идентификаторе. Например "\\.» (для SQL Server) или "\@&#124;\\.» (для Oracle).<br /><br /> Составные идентификаторы — как правило, для чего используется имя объекта базы данных, например: pubs.dbo.authors или pubs\@dbo.authors.<br /><br /> Для SQL Server, использовать регулярное выражение "\\.». Для OracleClient следует использовать "\@&#124;\\.».<br /><br /> Для ODBC следует использовать Catalog_name_seperator.<br /><br /> Для OLE DB следует использовать DBLITERAL_CATALOG_SEPARATOR или DBLITERAL_SCHEMA_SEPARATOR.|  
|DataSourceProductName|string|Имя продукта, доступ к которому обеспечивается поставщиком, например «Oracle» или «SQLServer».|  
|DataSourceProductVersion|string|Версия продукта, доступ к которому обеспечивается поставщиком, в собственном формате источников данных, а не в формате Microsoft.<br /><br /> В некоторых случаях DataSourceProductVersion и DataSourceProductVersionNormalized будут иметь одно значение. В случае OLE DB и ODBC эти значения всегда одинаковы, поскольку они сопоставляются с одним и тем же вызовом функции в собственном API-интерфейсе.|  
|DataSourceProductVersionNormalized|string|Нормализованная версия для источника данных, позволяющая провести ее сравнение с помощью функции `String.Compare()`. Данный формат является согласованным для всех версий поставщика, что позволяет исключить появление обозначения версии 10 между обозначениями версий 1 и 2 после сортировки.<br /><br /> Например поставщик Oracle использует формат «nn.nn.nn.nn.nn» для нормализованной версии, что приводит к источнику данных Oracle 8i возвращает значение «08.01.07.04.01»». SQL Server используется обычный формат Майкрософт имеющий вид «nn.nn.nnnn»».<br /><br /> В некоторых случаях DataSourceProductVersion и DataSourceProductVersionNormalized будут иметь одно значение. В случае OLE DB и ODBC эти значения всегда одинаковы, поскольку они сопоставляются с одним и тем же вызовом функции в собственном API-интерфейсе.|  
|GroupByBehavior|<xref:System.Data.Common.GroupByBehavior>|Задает связь между столбцами в предложении GROUP BY и неагрегатными столбцами в списке выбора.|  
|IdentifierPattern|string|Регулярное выражение, которое согласуется с идентификатором или имеет совпадающее с ним значение. Например, «[A-Za-z0-9_#$]».|  
|IdentifierCase|<xref:System.Data.Common.IdentifierCase>|Определяет, обрабатываются ли идентификаторы, не заключенные в кавычки, с учетом регистра.|  
|OrderByColumnsInSelect|bool|Указывает, должны ли столбцы в предложении ORDER BY быть в списке выбора. Значение true определяет, что они должны находиться в списке выбора, значение false указывает обратное.|  
|ParameterMarkerFormat|string|Строка форматирования, представляющая способ форматирования параметра.<br /><br /> Если именованные параметры поддерживаются источником данных, первый местозаполнитель в этой строке должен находиться в позиции форматирования имени параметра.<br /><br /> Например, если источник данных рассчитан на применение параметров с именем и с префиксом ":" это было бы «:{0}«. При форматировании с именем параметра «p1» итоговая строка будет иметь вид «:p1».<br /><br /> Если источник данных рассчитан параметров с префиксом "\@", но имена уже содержат их, это будет "{0}" и результатом форматирования параметра с именем "\@p1» просто"\@p1».<br /><br /> Для источников данных, не именованных параметров ожидается использование "?" символ, строка формата может быть указана как просто "?", что приводит к пропуску имени параметра. Для OLE DB возвращается символ «?».|  
|ParameterMarkerPattern|string|Регулярное выражение, соответствующее маркеру параметра. Оно будет иметь значение, совпадающее с именем параметра (если таковое имеется).<br /><br /> Например, если именованные параметры поддерживаются начальным "\@" начальным символом, которое будет включено в имя параметра, это будет: «(\@[A-Za-z0-9_$ #] *)».<br /><br /> Тем не менее если именованные параметры поддерживаются начальным ":", являющимся и он не является частью имени параметра, это было бы: «: ([A-Za-z0-9_$ #]\*)».<br /><br /> Разумеется, если источник данных не поддерживает именованные параметры, выражением будет просто «?».|  
|ParameterNameMaxLength|int|Максимальная длина имени параметра в символах. В среде Visual Studio принято предположение, что в случае поддержки имен параметров минимальным значением максимальной длины будет 30 символов.<br /><br /> Если источник данных не поддерживает именованные параметры, это свойство возвращает ноль.|  
|ParameterNamePattern|string|Регулярное выражение, соответствующее действительным именам параметров. Для различных источников данных применяются разные правила использования символов в именах параметров.<br /><br /> В среде Visual Studio принято предположение, что в случае поддержки имен параметров символы «\p{Lu}\p{Ll}\p{Lt}\p{Lm}\p{Lo}\p{Nl}\p{Nd}» являются минимальным поддерживаемым набором символов, действительных для имен параметров.|  
|QuotedIdentifierPattern|string|Регулярное выражение, соответствующее идентификатору, заключенному в кавычки, и имеющее значение идентификатора без кавычек. Например, если в источнике данных используются двойные кавычки для определения идентификаторов, заключенных в кавычки, это будет: «(([^\\"]&#124;\\"\\") *)».|  
|QuotedIdentifierCase|<xref:System.Data.Common.IdentifierCase>|Определяет, обрабатываются ли заключенные в кавычки идентификаторы с учетом регистра.|  
|StatementSeparatorPattern|string|Регулярное выражение, соответствующее разделителю инструкций.|  
|StringLiteralPattern|string|Регулярное выражение, соответствующее строковому литералу, и имеющее одинаковое с ним значение. Например, если в источнике данных используются одинарные кавычки для определения строк, это будет: «('([^']&#124;'') * ")»"|  
|SupportedJoinOperators|<xref:System.Data.Common.SupportedJoinOperators>|Указывает, какие типы инструкций соединения SQL поддерживаются источником данных.|  
  
## <a name="datatypes"></a>DataTypes  
 Данная коллекция схем предоставляет сведения о типах данных, поддерживаемых базой данных, к которой в данный момент подключен управляемый поставщик .NET Framework.  
  
|ColumnName|DataType|Описание|  
|----------------|--------------|-----------------|  
|TypeName|string|Имя типа данных, зависящего от поставщика.|  
|ProviderDbType|int|Значение типа, зависящего от поставщика, которое можно использовать при задании типа параметра. Например, SqlDbType.Money или OracleType.Blob.|  
|ColumnSize|long|Значение длины нечислового столбца или параметра, которое относится либо к максимуму, либо к длине, определенной поставщиком для этого типа.<br /><br /> Для символьных данных это максимальная или определенная длина в единицах, заданных источником данных. В Oracle для символьных данных некоторых типов применяется такой принцип, что вначале указывается длина, а затем - действительный размер хранения. Указывается длина в единицах только для Oracle.<br /><br /> Для типов данных даты-времени это длина строки представления (при условии использования максимально допустимой точности компонента с определением долей секунды).<br /><br /> Если типа данных является числовым, это верхняя граница максимальной точности типа данных.|  
|CreateFormat|string|Строка форматирования, представляющая способ добавления данного столбца в инструкцию описания данных, например CREATE TABLE. Каждый элемент массива CreateParameter должен быть представлен в строке форматирования так называемым «маркером параметра».<br /><br /> Например, тип данных DECIMAL в SQL требует указания точности и масштаба. В этом случае строка формата будет «DECIMAL ({0},{1})».|  
|CreateParameters|string|Параметры создания, которые необходимо указать при создании столбца данных этого типа. Каждый параметр создания перечисляется в строке с разделением запятыми в порядке указания параметров.<br /><br /> Например, тип данных DECIMAL в SQL требует указания точности и масштаба. В этом случае параметры создания должны содержать строку «точность, масштаб».<br /><br /> В тексте команды для создания столбца DECIMAL с точностью 10 и масштабом 2, значение столбца CreateFormat может быть ДЕСЯТИЧНЫМ ({0},{1}) «а полной спецификацией типа будет DECIMAL(10,2).|  
|DataType|string|Имя типа данных платформы .NET Framework.|  
|IsAutoincrementable|bool|true. Значения данных этого типа могут быть заданы с автоматическим приращением.<br /><br /> false. Значения данных этого типа не могут быть заданы с автоматическим приращением.<br /><br /> Обратите внимание, что определяется лишь возможность, что столбцы этого типа данных могут быть заданы с автоматическим приращением, а не то, что все столбцы этого типа имеют автоматическое приращение.|  
|IsBestMatch|bool|true. Данные этого типа выбираются с учетом наилучшего соответствия между типами данных хранилища данных и типом данных .NET Framework, определяемым значением в столбце DataType.<br /><br /> false. Данные этого типа не выбираются с учетом наилучшего соответствия.<br /><br /> Для каждого набора строк, в которых значение столбца DataType одинаково, столбцу IsBestMatch присваивается значение true только в одной строке.|  
|IsCaseSensitive|bool|true. Данные этого типа являются символьными и задаются с учетом регистра.<br /><br /> false. Данные этого типа не являются символьными, или в них не учитывается регистр.|  
|IsFixedLength|bool|true. Столбцы данных этого типа, созданные с помощью языка DDL, будут иметь фиксированную длину.<br /><br /> false. Столбцы данных этого типа, созданные с помощью языка DDL, будут иметь переменную длину.<br /><br /> DBNull.Value. Неизвестно, с каким столбцом поставщик сопоставит это поле - со столбцом фиксированной длины или переменной длины.|  
|IsFixedPrecisionScale|bool|true. Данные этого типа имеют фиксированные точность и масштаб.<br /><br /> false. Данные этого типа не имеют фиксированной точности и масштаба.|  
|IsLong|bool|true. Данные этого типа содержат данные очень большой длины. Определение данных очень большой длины зависит от поставщика.<br /><br /> false. Данные этого типа не содержат данные очень большой длины.|  
|IsNullable|bool|true. Данные этого типа допускают значения NULL.<br /><br /> false. Данные этого типа не допускают значения NULL.<br /><br /> DBNull.Value. Неизвестно, допускают ли данные этого типа значения NULL.|  
|IsSearchable|bool|true. Данные этого типа могут использоваться в предложении WHERE с любым оператором, за исключением предиката LIKE.<br /><br /> false. Данные этого типа не могут использоваться в предложении WHERE ни с одним оператором, за исключением предиката LIKE.|  
|IsSearchableWithLike|bool|true. Данные этого типа могут использоваться с предикатом LIKE.<br /><br /> false. Данные этого типа не могут использоваться с предикатом LIKE.|  
|IsUnsigned|bool|true. Данные этого типа являются беззнаковыми.<br /><br /> false. Данные этого типа представляют собой данные со знаком.<br /><br /> DBNull.Value. Значение неприменимо для типа данных.|  
|MaximumScale|short|Если индикатор типа является числовым типом, то он обозначает максимально допустимое число десятичных знаков после запятой. В противном случае это DBNull.Value.|  
|MinimumScale|short|Если индикатор типа является числовым типом, то он обозначает минимально допустимое число десятичных знаков после запятой. В противном случае это DBNull.Value.|  
|IsConcurrencyType|bool|true. Данные этого типа обновляются базой данных при каждом изменении строки, а текущее значение столбца отличается от всех предыдущих значений.<br /><br /> false. Данные этого типа не обновляются базой данных при каждом изменении строки.<br /><br /> DBNull.Value. База данных не поддерживает данные этого типа.|  
|IsLiteralSupported|bool|true. Данные этого типа могут быть выражены в виде литерала.<br /><br /> false. Данные этого типа не могут быть выражены в виде литерала.|  
|LiteralPrefix|string|К заданному литералу применяется префикс.|  
|LiteralSuffix|string|К заданному литералу применяется суффикс.|  
|NativeDataType|Строковое|NativeDataType представляет собой столбец OLE DB, который служит для обеспечения доступа к данным типа OLE DB.|  
  
## <a name="restrictions"></a>Ограничения  
 Данная коллекция схем предоставляет сведения об ограничениях, поддерживаемых управляемым поставщиком .NET Framework, который в данный момент подключен к базе данных.  
  
|ColumnName|DataType|Описание|  
|----------------|--------------|-----------------|  
|CollectionName|string|Имя коллекции, к которой применяются эти ограничения.|  
|RestrictionName|string|Имя ограничения в коллекции.|  
|RestrictionDefault|string|Не обрабатывается.|  
|RestrictionNumber|int|Фактическое расположение в коллекциях тех ограничений, к которым относится данное конкретное ограничение.|  
  
## <a name="reservedwords"></a>ReservedWords  
 Данная коллекция схем предоставляет сведения о словах, резервируемых базой данных, с которой в данный момент соединен управляемый поставщик .NET Framework.  
  
|ColumnName|DataType|Описание:|  
|----------------|--------------|-----------------|  
|ReservedWord|string|Поставщика зарезервированное слово.|  
  
## <a name="see-also"></a>См. также
- [Извлечение сведений о схеме базы данных](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)
- [Коллекции GetSchema и Schema](../../../../docs/framework/data/adonet/getschema-and-schema-collections.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
