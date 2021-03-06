---
title: Как выполнить Присоединение существующей сущности к контексту DataServiceContext (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, changing data
ms.assetid: e3f2d71d-434c-4e98-91c3-95adae4702b6
ms.openlocfilehash: 2a515609feff343b6e917bf420a06cfb9dc468df
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54614228"
---
# <a name="how-to-attach-an-existing-entity-to-the-dataservicecontext-wcf-data-services"></a>Как выполнить Присоединение существующей сущности к контексту DataServiceContext (службы данных WCF)
Если сущность уже имеется в службе данных, [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] клиентская библиотека позволяет присоединить объект, представляющий сущность непосредственно к <xref:System.Data.Services.Client.DataServiceContext> без предварительного выполнения запроса. Дополнительные сведения см. в разделе [обновление службы данных](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md).  
  
 Пример в этом разделе использует образец службы данных Northwind и автоматически сформированные клиентские классы службы данных. Эта служба и клиентские классы данных создаются при завершении [краткое руководство по службам данных WCF](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Пример  
 Следующий пример иллюстрирует создание существующего объекта `Customer`, содержащего изменения, которые должны быть сохранены в службе данных. Объект присоединяется к контексту, и вызывается метод <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A>, помечающий присоединенный объект как <xref:System.Data.Services.Client.EntityStates.Modified> перед вызовом метода <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>.  
  
 [!code-csharp[Astoria Northwind Client#AttachObject](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#attachobject)]
 [!code-vb[Astoria Northwind Client#AttachObject](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#attachobject)]  
  
## <a name="see-also"></a>См. также
- [Библиотека клиентов служб данных WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
