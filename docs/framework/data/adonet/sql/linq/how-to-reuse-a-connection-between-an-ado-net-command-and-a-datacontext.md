---
title: Как выполнить повторно использовать соединение между командой ADO.NET и DataContext
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
ms.openlocfilehash: 079b4b28a613ce6a9ae525514b89ea9e316a7c66
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54613679"
---
# <a name="how-to-reuse-a-connection-between-an-adonet-command-and-a-datacontext"></a>Как выполнить повторно использовать соединение между командой ADO.NET и DataContext
Так как [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] является частью [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] семейства технологий и основан на службах, предоставленных [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)], вы можете повторно использовать соединение между [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] команды и <xref:System.Data.Linq.DataContext>.  
  
## <a name="example"></a>Пример  
 В следующем примере показано повторное использование подключения между командой [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] и <xref:System.Data.Linq.DataContext>.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## <a name="see-also"></a>См. также
- [Основные сведения](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [ADO.NET и LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/ado-net-and-linq-to-sql.md)
- [Установка связи с базой данных](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
