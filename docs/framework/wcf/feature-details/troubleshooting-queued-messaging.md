---
title: Устранение неполадок обмена сообщениями с использованием очередей
ms.date: 03/30/2017
ms.assetid: a5f2836f-018d-42f5-a571-1e97e64ea5b0
ms.openlocfilehash: 2f0763ee2be5d11181ef944426a68d1662abb6aa
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43483766"
---
# <a name="troubleshooting-queued-messaging"></a>Устранение неполадок обмена сообщениями с использованием очередей
Этот раздел содержит общие вопросы и устранении неполадок с помощью очередей в Windows Communication Foundation (WCF).  
  
## <a name="common-questions"></a>Наиболее распространенные вопросы  
 **Вопрос** я использовал WCF бета-версии 1, и я установлено исправление MSMQ. Требуется ли удалять исправление?  
  
 **О.** Да. Это исправление больше не поддерживается. WCF теперь работает на MSMQ, не требуя установки исправления.  
  
 **Вопрос** имеется две привязки для MSMQ: <xref:System.ServiceModel.NetMsmqBinding> и <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>. Какую необходимо использовать и когда?  
  
 **Ответ** использовать <xref:System.ServiceModel.NetMsmqBinding> Если вы хотите использовать MSMQ в качестве транспорта для взаимодействия с использованием очередей между двумя приложениями WCF. Использовать <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> Если вы хотите использовать существующие приложения MSMQ для взаимодействия с новых приложений WCF.  
  
 **Вопрос** нужно ли обновлять MSMQ, чтобы использовать <xref:System.ServiceModel.NetMsmqBinding> и `MsmqIntegration` привязки?  
  
 **Ответ.** Нет. Обе привязки работают с MSMQ 3.0 в [!INCLUDE[wxp](../../../../includes/wxp-md.md)] и [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]. Некоторые возможности привязок будут доступны при обновлении до MSMQ 4.0 в [!INCLUDE[wv](../../../../includes/wv-md.md)].  
  
 **Вопрос** какие функции <xref:System.ServiceModel.NetMsmqBinding> и <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> привязки, доступны в MSMQ 4.0, но отсутствуют в MSMQ 3.0?  
  
 **Ответ** следующие функции доступны в MSMQ 4.0, но отсутствуют в MSMQ 3.0:  
  
-   Пользовательская очередь недоставленных сообщений поддерживается только в MSMQ 4.0.  
  
-   MSMQ 3.0 и 4.0 обрабатывают опасные сообщения по-разному.  
  
-   Удаленные чтения в транзакциях поддерживаются только MSMQ 4.0.  
  
 Дополнительные сведения см. в разделе [различия в возможностях очередей в Windows Vista, Windows Server 2003 и Windows XP](../../../../docs/framework/wcf/feature-details/diff-in-queue-in-vista-server-2003-windows-xp.md).  
  
 **Вопрос** использовать MSMQ 3.0 на одной стороне взаимодействия с использованием очередей, а MSMQ 4.0 на другой стороне?  
  
 **О.** Да.  
  
 **Вопрос** требуется интегрировать существующие приложения MSMQ с новый WCF-клиентов или серверов. Требуются ли обновления для обеих сторон инфраструктуры MSMQ?  
  
 **Ответ.** Нет. Для обеих сторон обновление до MSMQ 4.0 не требуется.  
  
## <a name="troubleshooting"></a>Устранение неполадок  
 Данный раздел содержит ответы на вопросы, связанные с устранением распространенных неполадок. Некоторые вопросы, являющиеся известными ограничениями, описаны также в заметках о выпуске.  
  
 **Вопрос** я пытаюсь использовать частную очередь, и я получаю следующее исключение: `System.InvalidOperationException`: URL-адрес является недопустимым. URL-адрес очереди не может содержать символ "$". Используйте синтаксис net.msmq://machine/private/queueName, чтобы адресовать частную очередь.  
  
 **Ответ** Проверьте универсальный код ресурса (URI) очереди в конфигурации и коде. Не используйте символ "$" в универсальном коде ресурса (URI). Например, чтобы адресовать частную очередь с именем OrdersQueue, задайте следующий универсальный код ресурса (URI): net.msmq://localhost/private/ordersQueue.  
  
 **Вопрос** вызова `ServiceHost.Open()` на мое приложение, в очереди вызывает следующее исключение: `System.ArgumentException`: базовый адрес не может содержать строку запроса URI. Почему?  
  
 **Ответ** проверять очередь URI в файле конфигурации и в коде. Хотя очереди MSMQ поддерживают использование символа "?", универсальные коды ресурсов (URI) интерпретируют этот символ как начало строки запроса. Чтобы избежать этого, не используйте символ "?" в именах очередей.  
  
 **Вопрос** Отправка выполнена успешно, но ни одна из операций службы вызывается на стороне получателя. Почему?  
  
 **Ответ** чтобы определиться с ответом, проработать в приведенном ниже контрольном списке:  
  
-   Проверьте, совместимы ли требования транзакционной очереди с заданными гарантиями. Обратите внимание на следующие принципы.  
  
    -   Можно отправлять устойчивые сообщения (датаграммы и сеансы) с «только один раз» гарантии (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `true`) только в транзакционную очередь.  
  
    -   Сеансы можно отправлять только с гарантиями доставки точно по одному разу.  
  
    -   Необходимо, чтобы в сеансе транзакция получала сообщения из транзакционной очереди.  
  
    -   Можно отправлять или получать неустойчивые и устойчивые сообщения (только датаграммы) без подтверждения (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `false`) только в нетранзакционную очередь.  
  
-   Проверьте очередь недоставленных писем. Если в этой очереди есть сообщения, определите причину, по которой они не были доставлены.  
  
-   Проверьте очереди исходящих сообщений на наличие проблем с подключением и адресацией.  
  
 **Вопрос** задана пользовательская очередь недоставленных. Однако при запуске приложения отправителя получается исключение, которые не были найдены очереди недоставленных или отправляющее приложение не имеет разрешения на очередь недоставленных сообщений. Что происходит?  
  
 **Ответ** пользовательской очереди недоставленных сообщений-URI должен включать значение «localhost» или имя компьютера в первый сегмент, например,: NET.MSMQ://localhost/Private/myappdead-Letter queue.  
  
 **Вопрос** , она всегда необходимо определять пользовательскую очередь недоставленных сообщений или существует очередь недоставленных сообщений-по умолчанию?  
  
 **Ответ** Если используются гарантии с «только один раз» (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `true`), и если вы не укажете пользовательскую очередь недоставленных сообщений-, значение по умолчанию является транзакционной очередью недоставленных всей системы.  
  
 Если гарантии отсутствуют (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `false`), по умолчанию — без функции очереди недоставленных сообщений.  
  
 **Вопрос** служба вызывает исключение Svchost.Open с сообщением «требования к EndpointListener могут быть выполнены с ListenerFactory». Почему?  
  
 О. Проверьте контракт службы. Возможно, вы забыли поместить «IsOneWay =`true`"на все операции службы. Очереди поддерживают только односторонние операции службы.  
  
 **Вопрос** в очереди есть сообщения, но операция службы не вызывается. В чем суть проблемы?  
  
 **Ответ** определить, если происходит сбой узла службы. Убедиться в этом можно, просмотрев трассировку или реализовав `IErrorHandler`. По умолчанию сбой узла службы происходит при обнаружении подозрительного сообщения.  
  
 **Вопрос** в очереди есть сообщения, но моей веб узле службы в очереди не активируется. Почему?  
  
 **Ответ** самая распространенная причина — разрешения.  
  
1.  Убедитесь в том, что выполняется процесс `NetMsmqActivator` и удостоверению процесса `NetMsmqActivator` предоставлено разрешение на чтение и поиск для данной очереди.  
  
2.  Если процесс `NetMsmqActivator` отслеживает очереди на удаленном компьютере, убедитесь в том, что `NetMsmqActivator` не выполняется с маркером ограниченного доступа. Чтобы выполнить процесс `NetMsmqActivator` с маркером неограниченного доступа, используется следующий код.  
  
    ```  
    sc sidtype NetMsmqActivator unrestricted  
    ```  
  
 Связанные веб узла проблем см. в: [веб-размещения приложения, в очередь](../../../../docs/framework/wcf/feature-details/web-hosting-a-queued-application.md).  
  
 **Вопрос** Каков самый простой способ доступа к сеансам?  
  
 **Ответ** задайте AutoComplete =`true` на операцию, которая соответствует последнему сообщению в сеансе и задайте AutoComplete =`false` на всех остальных операций службы.  
  
 **Вопрос** где можно найти ответы на часто задаваемые вопросы по MSMQ?  
  
 **Ответ** Дополнительные сведения о MSMQ, см. в разделе [Microsoft Message Queuing](https://go.microsoft.com/fwlink/?LinkId=87810).  
  
 **Вопрос** почему моя служба создается исключение `ProtocolException` при чтении из очереди, который содержит как сообщения сеанса в очереди и сообщения датаграммы?  
  
 **Ответ** фундаментальных различий в сообщениях как сеанса и сообщения датаграммы из очереди состоят. Вследствие этого, служба, ожидающая чтения сообщения сеанса из очереди не может получить сообщение датаграммы из очереди, а служба, ожидающая чтения сообщения датаграммы из очереди не может получить сообщения сеанса. При попытке чтения сообщений обоих типов из одной очереди будет получено следующее исключение.  
  
```  
System.ServiceModel.MsmqPoisonMessageException: The transport channel detected a poison message. This occurred because the message exceeded the maximum number of delivery attempts or because the channel detected a fundamental problem with the message. The inner exception may contain additional information.   
---> System.ServiceModel.ProtocolException: An incoming MSMQ message contained invalid or unexpected .NET Message Framing information in its body. The message cannot be received. Ensure that the sender is using a compatible service contract with a matching SessionMode.  
```  
  
 Системная очередь недоставленных сообщений, а также любая пользовательская очередь недоставленных сообщений особенно чувствительна к этой проблеме, если приложение отправляет с одного компьютера как сообщения сеанса в очереди, так и сообщения датаграммы. Если сообщение не удается отправить, оно перемещается в очередь недоставленных сообщений. При этих обстоятельствах в очереди недоставленных сообщений могут быть как сообщения сеанса, так и сообщения датаграмм. При чтении из очереди во время выполнения отсутствует возможность разделения двух типов сообщений, поэтому приложения не должны отправлять сообщения сеанса в очереди и сообщения датаграмм в очереди с одного компьютера.  
  
### <a name="msmq-integration-specific-troubleshooting"></a>Интеграция MSMQ: устранение конкретных неполадок  
 **Вопрос** при отправке сообщения или при открытии узла службы, сообщение об ошибке, указывающее, схема неверна. Почему?  
  
 **Ответ** при использовании привязки интеграции MSMQ необходимо применять схему msmq.formatname. Например, msmq.formatname:DIRECT=OS:.\private$\OrdersQueue. Однако если задана пользовательская очередь недоставленных сообщений, необходимо использовать схему net.msmq.  
  
 **Вопрос** при открытом или закрытом формате имя и откройте узел службы на [!INCLUDE[wv](../../../../includes/wv-md.md)], сообщение об ошибке. Почему?  
  
 **Ответ** каналом интеграции WCF на [!INCLUDE[wv](../../../../includes/wv-md.md)] проверяет, если можно открыть вложенную очередь для основной очереди приложения для обработки подозрительных сообщений. Имя вложенной очереди является производным от универсального кода ресурса (URI) msmq.formatname, передаваемого прослушивателю. Имя вложенной очереди в MSMQ может быть только непосредственным именем формата. Из-за этого возникает ошибка. Измените URI очереди на непосредственное имя формата.  
  
 **Вопрос** при получении сообщения из приложения MSMQ, сообщение находится в очереди и не читается принимающим приложением WCF. Почему?  
  
 **Ответ** проверьте, есть ли сообщение текст. Если в сообщении отсутствует тело, канал интеграции MSMQ игнорирует его. Реализуйте интерфейс `IErrorHandler`, чтобы получать уведомления об исключениях, и проверьте трассировки.  
  
### <a name="security-related-troubleshooting"></a>Устранение неполадок, связанных с безопасностью  
 **Вопрос** при выполнении образца, использующего привязку по умолчанию в режиме рабочей группы, сообщения отправляются, но они не доходят до получателя.  
  
 **Ответ** по умолчанию сообщения подписываются с использованием внутреннего сертификата MSMQ, которого требуется служба каталогов Active Directory. В режиме рабочей группы происходит сбой подписи сообщения, так как служба каталогов Active Directory недоступна. Поэтому сообщение попадает в очередь недоставленных и указывает причины сбоя, например «Неверная сигнатура».  
  
 Чтобы обойти эту проблему, можно отключить систему безопасности. Это сделать, задав <xref:System.ServiceModel.NetMsmqSecurity.Mode%2A>  =  <xref:System.ServiceModel.NetMsmqSecurityMode.None> заставить их работать в режиме рабочей группы.  
  
 Как вариант можно получить <xref:System.ServiceModel.MsmqTransportSecurity> из свойства <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A> и присвоить ему значение <xref:System.ServiceModel.MsmqAuthenticationMode.Certificate>, а затем задать сертификат клиента.  
  
 Еще одним обходным путем является установка MSMQ с интеграцией Active Directory.  
  
 **Вопрос** при отправке сообщения с привязкой по умолчанию (Безопасность транспорта включена) в Active Directory в очередь, я получаю сообщение «внутренний сертификат не найден». Как устранить эту проблему?  
  
 **Ответ** это означает, что необходимо обновить сертификат в Active Directory для отправителя. Чтобы сделать это, откройте **панели управления**, **Администрирование**, **Управление компьютером**, щелкните правой кнопкой мыши **MSMQ**и выберите **Свойства**. Выберите **сертификат пользователя** вкладку и нажмите кнопку **Renew** кнопки.  
  
 **Вопрос** при отправке сообщения с помощью <xref:System.ServiceModel.MsmqAuthenticationMode.Certificate> и укажите сертификат, используемый, я получаю сообщение «Недопустимый сертификат». Как устранить эту проблему?  
  
 **Ответ** хранилище сертификатов локального компьютера нельзя использовать в режиме сертификатов. Необходимо скопировать сертификат из хранилища сертификатов компьютера в хранилище текущего пользователя с помощью оснастки сертификатов. Чтобы получить оснастку сертификатов, выполните следующие действия.  
  
1.  Нажмите кнопку **запустить**выберите **запуска**, тип `mmc`и нажмите кнопку **ОК**.  
  
2.  В **консоли управления**откройте **файл** меню и выберите **Add/Remove Snap-in**.  
  
3.  В **Add/Remove Snap-in** диалоговом окне щелкните **добавить** кнопки.  
  
4.  В **Добавить изолированную оснастку** диалоговое окно, выберите сертификаты и нажмите кнопку **добавить**.  
  
5.  В **сертификаты** привязки в диалоговом окне выберите **моей учетной записи пользователя,** и нажмите кнопку **Готово**.  
  
6.  Добавьте второй оснастку сертификатов, выполнив предыдущие действия, но на этот раз выберите **учетная запись компьютера** и нажмите кнопку **Далее**.  
  
7.  Выберите **локального компьютера** и нажмите кнопку **Готово**. Теперь сертификаты можно перетаскивать из хранилища сертификатов компьютера в хранилище текущего пользователя.  
  
 **Вопрос** когда служба считывает из очереди на другом компьютере в режиме рабочей группы, получается исключение «доступ запрещен».  
  
 **Ответ** в режиме рабочей группы, удаленное приложение для получения доступа к очереди, приложение должно иметь разрешение на доступ к очереди. Добавьте «Анонимный вход» в очереди список управления доступом (ACL) и предоставьте ей разрешение на чтение.  
  
 **Вопрос** когда клиент сетевой службы (или любого клиента, который не имеет учетной записи домена) отправляет сообщения в очереди, происходит сбой отправки с недействительным сертификатом. Как устранить эту проблему?  
  
 **Ответ** Проверьте конфигурацию привязки. В привязке по умолчанию включена безопасность транспорта MSMQ для подписи сообщения. Отключите ее.  
  
### <a name="remote-transacted-receives"></a>Удаленное получение транзакций  
 **Вопрос** при наличии очереди на компьютере A, и службы WCF, которая считывает сообщения из очереди на компьютере B (сценарий удаленного получения транзакций), сообщения не считываются из очереди. Сведения трассировки указывают на сбой получения с сообщением «не удается импортировать транзакцию.» Как решить эту проблему?  
  
 **Ответ** существуют три возможные причины этого:  
  
-   В режиме домена для удаленного получения транзакций требуется доступ к сети координатора распределенных транзакций (Майкрософт) (MSDTC). Вы можете включить ее с помощью **Установка и удаление компонентов**.  
  
     ![Включение сетевого доступа DTC](../../../../docs/framework/wcf/feature-details/media/applicationserveraddcomps.jpg "ApplicationServerAddComps")  
  
-   Проверьте режим проверки подлинности для взаимодействия с диспетчером транзакций. Если вы находитесь в режиме рабочей группы, необходимо выбрать «Проверка подлинности не требуется». Если вы находитесь в режиме домена, необходимо выбрать «Требуется взаимная проверка подлинности».  
  
     ![Включение транзакций XA](../../../../docs/framework/wcf/feature-details/media/4f3695e0-fb0b-4c5b-afac-75f8860d2bb0.jpg "4f3695e0-fb0b-4c5b-afac-75f8860d2bb0")  
  
-   Убедитесь, что MSDTC находится в списке исключений в **брандмауэр подключения к Интернету** параметры.  
  
-   Убедитесь, что используется [!INCLUDE[wv](../../../../includes/wv-md.md)]. MSMQ в [!INCLUDE[wv](../../../../includes/wv-md.md)] поддерживает удаленное чтение в транзакциях. MSMQ в более ранних версиях Windows не поддерживает удаленное чтение в транзакциях.  
  
 **Вопрос** чтения службой сообщений из очереди сетевой службы, например, в веб-узла, почему я получаю исключение отказе в доступе вызывается при чтении из очереди?  
  
 **Ответ** доступ на чтение службы сети должны добавляться в очередь ACL, чтобы убедиться, что сетевая служба могла читать из очереди.  
  
 **Вопрос** используется служба активации MSMQ для активации приложения на основе сообщений в очереди на удаленном компьютере?  
  
 **О.** Да. Для этого необходимо настроить службу активации MSMQ для выполнения в качестве сетевой службы, а также добавить доступ сетевой службы к очереди на удаленном компьютере.  
  
## <a name="using-custom-msmq-bindings-with-receivecontext-enabled"></a>Использование пользовательских привязок MSMQ с включенным ReceiveContext  
 При использовании пользовательских привязок MSMQ с включенным <xref:System.ServiceModel.Channels.ReceiveContext> для обработки входящего сообщения будет использоваться поток из пула потоков, поскольку собственная MSMQ не поддерживает завершение ввода-вывода для асинхронного получения <xref:System.ServiceModel.Channels.ReceiveContext>. Причина этого в том, что при обработке такого сообщения для <xref:System.ServiceModel.Channels.ReceiveContext> используются внутренние транзакции, а MSMQ не поддерживает асинхронной обработки. Эту проблему можно обойти, добавив <xref:System.ServiceModel.Description.SynchronousReceiveBehavior> к конечной точке для принудительной асинхронной обработки или установив для параметра <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior.MaxPendingReceives%2A> значение 1.
