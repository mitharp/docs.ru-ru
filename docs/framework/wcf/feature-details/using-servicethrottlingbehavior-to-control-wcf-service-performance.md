---
title: Использование ServiceThrottlingBehavior для управления производительностью службы WCF
ms.date: 03/30/2017
helpviewer_keywords:
- behavior [WCF], service performance
ms.assetid: f9dc120c-dc24-49d5-930e-b22f5bc73423
ms.openlocfilehash: 77fe2d3bb7f0e9c9d2e2defd4aa8c0053799406b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54609503"
---
# <a name="using-servicethrottlingbehavior-to-control-wcf-service-performance"></a>Использование ServiceThrottlingBehavior для управления производительностью службы WCF
Класс <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> представляет свойства, которые можно использовать для ограничения количества экземпляров или сеансов, создаваемых на уровне приложения. С помощью этого поведения, можно оптимизировать производительность приложения Windows Communication Foundation (WCF).  
  
## <a name="controlling-service-instances-and-concurrent-calls"></a>Управление экземплярами службы и одновременными вызовами  
 С помощью свойства <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> задайте максимальное количество одновременно обрабатываемых сообщений в классе <xref:System.ServiceModel.ServiceHost>, а с помощью свойства <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A> задайте максимальное количество объектов <xref:System.ServiceModel.InstanceContext> в службе.  
  
 Поскольку определение параметров для этих свойств обычно выполняется после фактического выполнения приложения с нагрузками, параметры для <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> свойства, как правило, задаются в файле конфигурации приложения с помощью [ \<serviceThrottling >](../../../../docs/framework/configure-apps/file-schema/wcf/servicethrottling.md) элемент.  
  
 В следующем примере кода показано использование класса <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> из файла конфигурации приложения, который, в качестве упрощенного примера, задает для свойств <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentSessions%2A>, <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> и <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A> значение 1. Фактические условия определяют оптимальные параметры для каждого конкретного приложения.  
  
 [!code-xml[ServiceThrottlingBehavior#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/servicethrottlingbehavior/cs/hostapplication.exe.config#3)]  
  
 Точное поведение времени выполнения зависит от значений свойств <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> и <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>, которые управляют количеством сообщений, которые могут обрабатываться в операции одновременно, и временем существования службы <xref:System.ServiceModel.InstanceContext> относительно сеансов входящих каналов, соответственно.  
  
 Дополнительные сведения см. в разделах <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> и <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A>.  
  
## <a name="see-also"></a>См. также
- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
- <xref:System.ServiceModel.NetTcpBinding.MaxConnections%2A>
