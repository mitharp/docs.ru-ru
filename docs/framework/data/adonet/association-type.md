---
title: тип ассоциации
ms.date: 03/30/2017
ms.assetid: 26c409f6-06e8-4441-ac78-1b1076a3c005
ms.openlocfilehash: 3b01e053a1d61e2ce413ae6683d350b77c402fb5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54714598"
---
# <a name="association-type"></a>тип ассоциации
*Тип ассоциации* (также называемый ассоциацией) — это фундаментальный блок построения для описания связей в Entity Data Model (EDM). В концептуальной модели ассоциация представляет отношение между двумя [типы сущностей](../../../../docs/framework/data/adonet/entity-type.md) (такие как `Customer` и `Order`). В приложении экземпляр ассоциации представляет собой специфическую ассоциацию (такую как ассоциация между экземпляром `Customer` и экземпляром `Order`). Экземпляры ассоциации логически сгруппированы в [набор ассоциаций](../../../../docs/framework/data/adonet/association-set.md).  
  
 Определение ассоциации содержит следующую информацию.  
  
-   Уникальное имя. (Обязательный атрибут).  
  
-   Два [ассоциации](../../../../docs/framework/data/adonet/association-end.md), один для каждого типа сущности в отношении. (Обязательный атрибут).  
  
    > [!NOTE]
    >  Ассоциация не может представлять связь между более чем двумя типами сущностей. Ассоциация может, тем не менее, определять связь с самим собой посредством указания одного и того же типа сущности для каждой из его конечных точек ассоциаций.  
  
-   Объект [ограничение ссылочной целостности](../../../../docs/framework/data/adonet/referential-integrity-constraint.md). (Необязательный параметр).  
  
 Каждая конечная точка ассоциации необходимо указать [кратность конечной](../../../../docs/framework/data/adonet/association-end-multiplicity.md) , указывающее число экземпляров типа сущности, которые могут быть на одном конце ассоциации. Кратность конечной точки ассоциации может иметь значение «один» (1), «нуль или один» (0..1) или «много» (*). Экземпляры типа сущности на одном конце ассоциации может осуществляться через [свойства навигации](../../../../docs/framework/data/adonet/navigation-property.md) или внешних ключей, если они экспонируются типом сущности. Дополнительные сведения см. в разделе [модели EDM: Внешние ключи](../../../../docs/framework/data/adonet/foreign-key-property.md).  
  
## <a name="example"></a>Пример  
 На приведенной ниже схеме показана концептуальная модель с двумя ассоциациями: `PublishedBy` и `WrittenBy`. Конечные точки ассоциации для ассоциации `PublishedBy` - это типы сущности `Book` и `Publisher`. Кратность конечной точки `Publisher` - «один» (1), а кратность конечной точки `Book` - «много» (*), что означает, что издатель публикует много книг, а одна книга публикуется одним издателем.  
  
 ![Пример модели](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) для определения концептуальных моделей. Далее язык CSDL определяет ассоциацию `PublishedBy`, которая ранее приводилась в схеме.  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a>См. также
- [Основные понятия модели EDM](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Сущностная модель данных](../../../../docs/framework/data/adonet/entity-data-model.md)
