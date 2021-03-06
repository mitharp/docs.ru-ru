---
title: Сценарии одноранговых каналов
ms.date: 03/30/2017
ms.assetid: dae6e0f7-900c-45ee-8be9-3647698382fb
ms.openlocfilehash: 05fe7f632b286876dfee36b7d5d22a77c0ae11e4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54566218"
---
# <a name="peer-channel-scenarios"></a>Сценарии одноранговых каналов
Поддержка интерфейсов API одноранговых каналов для следующих сценариев разработки.  
  
## <a name="publicationsubscription-messaging"></a>Обмен сообщениями с публикацией и подпиской  
 Компании, создающие приложения с публикацией и подпиской (например, программы для публикации биржевых котировок, заголовков новостей, спортивных результатов и прогноза погоды), могут использовать одноранговые каналы в бессерверных приложениях. Например, пользователи могут получать самые свежие результаты спортивных соревнований, присоединясь к общей сетке (или группе клиентов), и распространять большие объемы самых свежих данных об игре, не увеличивая нагрузку на сервер. Это позволяет поставщику данных повысить качество обслуживания практически без увеличения расходов на серверные технологии.  
  
## <a name="collaboration"></a>Совместная работа  
 Независимые поставщики программного обеспечения могут создавать приложения, которые позволяют пользователям объединяться в тесные группы для выполнения одноранговых операций. Например, это может быть совместная работа над проектами, обмен фотографиями с друзьями, планирование развлекательных мероприятий и т. д. Обычно в таких случаях используется сервер; однако одноранговые каналы предлагают более экономичное решение этой задачи за счет сценариев автономного доступа, которые достаточно сложно реализовать в традиционной модели "клиент-сервер".  
  
## <a name="distributed-processing-and-compute-clusters"></a>Распределенная обработка и вычислительные кластеры  
 Вычислительные кластеры и распределенная обработка обычно используются для масштабных расчетов, например для моделирования финансовых рынков, прогнозирования погоды или расшифровки ДНК человека. В большинстве случаев для решения подобных проблем серверы назначают отдельные задачи всем клиентам, входящим в вычислительный кластер. Такие серверы обычно устанавливают дополнительные требования; например, все задачи должны быть завершены в течение определенного интервала времени, для чего требуется выделять более одного компьютера под каждую задачу. Кроме того, если один из клиентов, выполняющих задачу, выйдет из строя, другой клиент должен подхватить эту задачу и завершить ее. Возможно также, что одна и та же задача должна выполняться на нескольких клиентах, чтобы можно было сравнить результаты. Хотя подобная координация работы клиентов может выполняться сервером, можно создать одноранговое решение, где клиенты, получающие задачи независимо, определяют требования сервера к этой задаче и с помощью вычислительной сетки определяют, как именно следует выполнять эту задачу.  
  
## <a name="gaming"></a>Игры  
 С помощью приложений на базе одноранговых каналов разработчики могут реализовывать бессерверные версии игр, где игровые действия синхронизируются между игроками при помощи однорангового механизма, а не через центральный сервер. Для небольших разработчиков такой подход позволяет избавиться от операционных издержек, связанных с развертыванием, поддержкой и обслуживанием центральных серверов. В игры, написанные с использованием одноранговой архитектуры, можно играть через Интернет, а также через проводные и беспроводные сети. Кроме того, на базе одноранговых сетей можно реализовывать вспомогательные игровые процессы, например общение между участниками игры.  
  
## <a name="see-also"></a>См. также
- [Основные понятия одноранговых каналов](../../../../docs/framework/wcf/feature-details/peer-channel-concepts.md)
