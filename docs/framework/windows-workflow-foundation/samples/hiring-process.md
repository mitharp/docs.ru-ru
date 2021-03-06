---
title: Процесс найма
ms.date: 03/30/2017
ms.assetid: d5fcacbb-c884-4b37-a5d6-02b1b8eec7b4
ms.openlocfilehash: 0420a174705c12384509bf1d8022d664d7cb354e
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2019
ms.locfileid: "54223225"
---
# <a name="hiring-process"></a>Процесс найма
Этот образец демонстрирует, как реализовать бизнес-процесс, используя действия обмена сообщениями и два рабочих процесса, размещенные как службы рабочих процессов. Эти рабочие процессы входят в ИT-инфраструктуру вымышленной компании Contoso, Inc.  
  
 Рабочий процесс `HiringRequest` (реализованный как <xref:System.Activities.Statements.Flowchart>) запрашивает авторизацию у нескольких менеджеров организации. Для достижения этой цели, в рабочем процессе используется другими существующими службами в организации (в нашем случае это служба почтового ящика и служба данных организации реализованы в виде простых служб Windows Communication Foundation (WCF)).  
  
 Рабочий процесс `ResumeRequest` (реализованный как <xref:System.Activities.Statements.Sequence>) публикует объявления о вакансиях на соответствующей странице внешнего веб-узла компании Contoso, а также управляет получением резюме. Размещенное объявление о вакансии находится на внешнем веб-узле в течение определенного времени (до истечения времени ожидания) либо до тех пор, пока сотрудник компании Contoso не решит удалить его.  
  
 Этот образец демонстрирует следующие функции [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].  
  
-   Рабочие процессы <xref:System.Activities.Statements.Flowchart> и <xref:System.Activities.Statements.Sequence> для моделирования бизнес-процессов.  
  
-   Службы рабочего процесса.  
  
-   Действия обмена сообщениями.  
  
-   Корреляция по содержимому.  
  
-   Настраиваемые действия (декларативные и основанные на коде).  
  
-   Предоставляемая системой сохраняемость сервера SQL.  
  
-   Настраиваемый <xref:System.Activities.Persistence.PersistenceParticipant>.  
  
-   Настраиваемое отслеживание.  
  
-   Отслеживание Event Tracking for Windows (ETW).  
  
-   Сочетание действий.  
  
-   Действия <xref:System.Activities.Statements.Parallel>.  
  
-   Действие <xref:System.Activities.Statements.CancellationScope>.  
  
-   Устойчивые таймеры (действие <xref:System.Activities.Statements.Delay>).  
  
-   Транзакции.  
  
-   Несколько рабочих процессов в одном решении.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Application\HiringProcess`  
  
## <a name="description-of-the-process"></a>Описание процесса  
 Компании Contoso, Inc. требуется постоянно контролировать количество сотрудников во всех своих отделах. Поэтому каждый раз, когда какой-нибудь сотрудник хочет нанять нового сотрудника, он должен выполнить процесс одобрения запроса о найме до того, как объявление о вакансии будет опубликовано. Этот процесс называется запросом о найме (он определен в проекте HiringRequestService), он состоит из двух этапов.  
  
1.  Сотрудник (инициатор) создает запрос о найме.  
  
2.  Менеджер инициатора должен одобрить запрос.  
  
    1.  Менеджер может отклонить запрос.  
  
    2.  Менеджер может вернуть запрос инициатору для получения дополнительных сведений.  
  
        1.  Инициатор анализирует ответ менеджера и возвращает ему запрос.  
  
    3.  Менеджер может его утвердить.  
  
3.  После получения одобрения менеджера инициатора запрос должен одобрить глава отдела.  
  
    1.  Глава отдела может отклонить запрос.  
  
    2.  Глава отдела может одобрить запрос.  
  
4.  После получения одобрения главы отдела запрос должен быть одобрен двумя менеджерами по персоналу или главой компании.  
  
    1.  Процесс может перейти в состояние «одобрено» или «отклонено».  
  
    2.  Если запрос одобрен, создается новый экземпляр рабочего процесса `ResumeRequest` (`ResumeRequest` связывается с HiringRequest.csproj с помощью ссылки на службу).  
  
 После одобрения менеджерами найма нового сотрудника отдел кадров должен найти подходящего кандидата. Этот процесс выполняется вторым рабочим процессом (`ResumeRequest`, определенным в ResumeRequestService.csproj). Этот рабочий процесс определяет процесс публикации объявления о вакансии на соответствующей странице внешнего веб-узла компании Contoso, получает резюме от претендентов и отслеживает состояние объявления о вакансии. Объявление отображается в течение определенного времени (до истечения времени ожидания) либо до тех пор, пока сотрудник не решит удалить его. Рабочий процесс `ResumeRequest` состоит из следующих шагов.  
  
1.  Сотрудник компании Contoso вводит сведений о вакансии и время, в течение которого она будет доступна. После ввода сотрудником этих сведений вакансия размещается на соответствующей странице веб-узла.  
  
2.  После публикации сведений заинтересованные кандидаты могут подавать свои резюме. После подачи резюме оно сохраняется в записи, связанной с вакансией.  
  
3.  Претенденты могут подавать свои резюме до истечения времени ожидания или до тех пор, пока кто-то из сотрудников отдела кадров компании Contoso не решит удалить вакансию, остановив процесс.  
  
## <a name="projects-in-the-sample"></a>Проекты в этом образце  
 В следующей таблице приведены проекты из этого образца решения.  
  
|Project|Описание|  
|-------------|-----------------|  
|ContosoHR|Содержит контракты данных, бизнес-объекты и классы репозитория.|  
|HiringRequestService|Содержит определение рабочего процесса запроса на найм.<br /><br /> Этот проект реализован в виде консольного приложения, в котором рабочий процесс (файл xaml) является резидентной службой.|  
|ResumeRequestService|Служба рабочего процесса, которая собирает резюме от кандидатов до истечения времени ожидания или до того момента, когда кто-то решит остановить процесс.<br /><br /> Этот проект реализован в виде декларативной службы рабочего процесса (xamlx).|  
|OrgService|Служба, которая предоставляет данные организации (Employees, Positions, PositionTypes и Departments). Эту службу можно представить в виде модуля организации компании плана ресурсов предприятия.<br /><br /> Этот проект реализован как консольное приложение, которое предоставляет службы Windows Communication Foundation (WCF).|  
|InboxService|Папка «Входящие», содержащая императивные задачи для сотрудников.<br /><br /> Этот проект реализован в виде консольного приложения, предоставляющего службу WCF.|  
|InternalClient|Веб-приложение для взаимодействия с процессом. Пользователи могут запускать свои рабочие процессы HiringProcess, участвовать в них, просматривать их. С помощью этого приложения они также могут запускать и отслеживать процессы ResumeRequest.<br /><br /> Этот узел реализован как внутренний в интрасети компании Contoso. Этот проект реализован в виде веб-узла ASP.NET.|  
|CareersWebSite|Внешний веб-узел, на котором отображаются открытые вакансии в компании Contoso. Любой потенциальный кандидат может перейти на этот узел и отправить резюме.|  
  
## <a name="feature-summary"></a>Сводка функций  
 В следующей таблице приведено описание того, как в этом образце используется каждая функция.  
  
|Функция|Описание|Project|  
|-------------|-----------------|-------------|  
|Блок-схема|Бизнес-процесс представлен в виде блок-схемы. Это описание с помощью блок-схемы представляет процесс так же, как в реальной жизни он был бы нарисован на доске.|HiringRequestService|  
|Службы рабочего процесса|Flowchart с определением процесса размещается в службе (в данном примере служба размещается в консольном приложении).|HiringRequestService|  
|Действия обмена сообщениями|На блок-схеме действия обмена сообщениями используются двумя способами.<br /><br /> — Чтобы получать информацию от пользователя (получение решений и связанные сведения на каждом этапе одобрения).<br />-Для взаимодействия с другими существующими службами (InboxService и OrgDataService, используемыми с помощью ссылок на службы).|HiringRequestService|  
|Корреляция по содержимому|Сообщения об одобрении связываются со свойством ID запроса о найме.<br /><br /> — При запуске процесса дескриптор взаимосвязи инициализируется с Идентификатором запроса.<br />-Входящие сообщения об одобрении связываются со своими Идентификаторами, (первый параметр каждого сообщения об одобрении является идентификатор запроса).|HiringRequestService / ResumeRequestService|  
|Настраиваемые действия (декларативные и основанные на коде)|В этом образце присутствует несколько пользовательских действий.<br /><br /> -   `SaveActionTracking`: Это действие выдает настраиваемую <xref:System.Activities.Tracking.TrackingRecord> (с помощью <xref:System.Activities.NativeActivityContext.Track%2A>). Это действие создано с помощью императивного кода, расширяющего <xref:System.Activities.NativeActivity>.<br />-   `GetEmployeesByPositionTypes`: Это действие получает список идентификаторов типов должностей и возвращает список людей, которые занимают эту должность в компании Contoso. Это действие создано декларативно (с помощью конструктора действий).<br />-   `SaveHiringRequestInfo`: Это действие сохраняет сведения о `HiringRequest` (с помощью `HiringRequestRepository.Save`). Это действие создано с помощью императивного кода, расширяющего <xref:System.Activities.CodeActivity>.|HiringRequestService|  
|Предоставляемая системой сохраняемость сервера SQL|Экземпляр <xref:System.ServiceModel.Activities.WorkflowServiceHost>, в котором размещается определение процесса Flowchart, настроен на использование предоставляемой системой сохраняемости SQL Server.|HiringRequestService / ResumeRequestService|  
|Настраиваемое отслеживание|Этот образец содержит настраиваемого участника отслеживания, который сохраняет журнал `HiringRequestProcess` (он записывает, какие действия выполнены, кем и когда). Исходный код находится в папке Tracking службы HiringRequestService.|HiringRequestService|  
|Отслеживание трассировки событий Windows|Предоставляемое системой отслеживание трассировки событий Windows настраивается в файле App.config в службе HiringRequestService.|HiringRequestService|  
|Сочетание действий|В определении процесса используется свободное сочетание действий <xref:System.Activities.Activity>. Flowchart содержит несколько действий Sequence и Parallel, которые одновременно содержат другие действия (и так далее).|HiringRequestService|  
|Параллельные действия|-   <xref:System.Activities.Statements.ParallelForEach%601> используется для регистрации в папке «Входящие» главы компании и менеджеров по Персоналу в параллельном режиме (ожидает утверждаемых двумя менеджерами по Персоналу).<br />-   <xref:System.Activities.Statements.Parallel> используется для выполнения некоторых задач очистки на шагах завершено» и «отклонено|HiringRequestService|  
|Отмена модели|Flowchart использует <xref:System.Activities.Statements.CancellationScope> для создания режима отмены (в данном случае он выполняет очистку).|HiringRequestService|  
|Участник Customer Persistence|`HiringRequestPersistenceParticipant` сохраняет данные из переменной рабочего процесса в таблицу, хранящуюся в базе данных персонала Contoso.|HiringRequestService|  
|Службы рабочего процесса|`ResumeRequestService` реализована с помощью служб рабочего процесса. Определение рабочего процесса и данные службы содержатся в ResumeRequestService.xamlx. Служба настроена на использование сохраняемости и отслеживания.|ResumeRequestService|  
|Устойчивые таймеры|`ResumeRequestService` использует устойчивые таймеры для определения продолжительности публикации вакансии (по истечении времени ожидания вакансия закрывается).|ResumeRequestService|  
|Транзакции|<xref:System.Activities.Statements.TransactionScope> используется для обеспечения согласованности данных в рамках выполнения нескольких действий (при получении нового резюме).|ResumeRequestService|  
|Транзакции|Участник настраиваемой сохраняемости (`HiringRequestPersistenceParticipant`) и участник настраиваемого отслеживания (`HistoryFileTrackingParticipant`) используют одну и ту же транзакцию.|HiringRequestService|  
|Использование [!INCLUDE[wf1](../../../../includes/wf1-md.md)] в приложениях [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].|Доступ к рабочим процессам осуществляется из двух приложений [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].|InternalClient / CareersWebSite|  
  
## <a name="data-storage"></a>Хранилище данных  
 Данные хранятся в базе данных SQL Server `ContosoHR` (скрипт для создания этой базы данных находится в папке `DbSetup`). Экземпляры рабочего процесса хранятся в базе данных SQL Server `InstanceStore` (скрипт для создания хранилища экземпляров является частью распространения [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)]).  
  
 Обе базы данных создаются путем запуска скрипта Setup.cmd из командной строки разработчика для Visual Studio.  
  
## <a name="running-the-sample"></a>Выполнение образца  
  
#### <a name="to-create-the-databases"></a>Создание баз данных  
  
1.  Откройте командную строку разработчика для Visual Studio.  
  
2.  Перейдите в папку образца.  
  
3.  Запустите команду Setup.cmd.  
  
4.  Удостоверьтесь, что две базы данных, `ContosoHR` и `InstanceStore`, были созданы в SQL Express.  
  
#### <a name="to-set-up-the-solution-for-execution"></a>Настройка решения для выполнения  
  
1.  Запустите Visual Studio от имени администратора. Откройте HiringRequest.sln.  
  
2.  Щелкните правой кнопкой мыши решение в **обозревателе решений** и выберите **свойства**.  
  
3.  Выберите параметр **несколько запускаемых проектов** и задайте **CareersWebSite**, **InternalClient**, **HiringRequestService**, и **ResumeRequestService** для **запустить**. Оставьте **ContosoHR**, **InboxService**, и **OrgService** как None.  
  
4.  Выполните сборку решения, нажав клавиши CTRL+SHIFT+B. Удостоверьтесь, что построение выполнено успешно.  
  
#### <a name="to-run-the-solution"></a>Запуск решения  
  
1.  После построения решения нажмите клавиши CTRL+F5, чтобы запустить его без отладки. Удостоверьтесь, что все службы запустились.  
  
2.  Щелкните правой кнопкой мыши **InternalClient** в решении, а затем выберите **просмотреть в браузере**. Будет отображена страница `InternalClient` по умолчанию. Удостоверьтесь, что службы работают, и щелкните ссылку.  
  
3.  **HiringRequest** будет отображен модуль. Далее можно выполнить описанный здесь сценарий.  
  
4.  После выполнения `HiringRequest` можно запустить `ResumeRequest`. Далее можно выполнить описанный здесь сценарий.  
  
5.  При размещении `ResumeRequest` она появляется на открытом веб-узле (странице с вакансиями в компании Contoso). Чтобы увидеть объявление о вакансии (и подать заявление о приеме на работу), перейдите на страницу веб-узла с вакансиями.  
  
6.  Щелкните правой кнопкой мыши **CareersWebSite** в решение и выберите **просмотреть в браузере**.  
  
7.  Вернитесь к `InternalClient` щелкните правой кнопкой мыши **InternalClient** в решении и выбрав **просмотреть в браузере**.  
  
8.  Перейдите к **JobPostings** щелкнуть **вакансиях** ссылка в верхнем меню папки "Входящие". Далее можно выполнить описанный здесь сценарий.  
  
## <a name="scenarios"></a>Сценарии  
  
### <a name="hiring-request"></a>Запрос о найме  
  
1.  Майкл Александр (инженер-программист) отправил запрос о найме нового сотрудника на должность «Инженер-программист по тестированию» в отдел разработок, имеющего не менее трех лет стажа работы с языком C#.  
  
2.  После создания запрос появится в папку "Входящие" Майкла (щелкните **обновить** Если вы не видите запрос) ожидает Питера брема, который является менеджером Майкла.  
  
3.  Питер принимает решение по запросу Майкла. Он полагает, что для этой должности нужен человек с пятилетним, а не с трехлетним опытом работы с C#, о чем он и сообщил Майклу в своем комментарии.  
  
4.  Майкл видит сообщение от менеджера в своем ящике и принимает решение. Майкл видит историю запроса и соглашается с Питером. Майкл изменяет описание, указав требование пятилетнего опыта работы с C# и принимает изменение.  
  
5.  Питер получает измененный запрос Майкла и принимает его. Теперь запрос должен быть одобрен главой отдела разработок Цви Рейтиром.  
  
6.  Цви Рейтир хочет ускорить запрос, поэтому в своем комментарии он пишет, что запрос является срочным и принимает его.  
  
7.  Теперь запрос должен быть одобрен двумя менеджерами по персоналу и главой компании. Глава компании Брайан Ричард Голдштайн видит срочный запрос от Цви. Он принимает запрос, обойдя, таким образом, одобрение двух менеджеров по персоналу.  
  
8.  Запрос удаляется из ящика Майкла, и процесс найма нового программиста запускается.  
  
### <a name="start-resume-request"></a>Запуск запроса резюме  
  
1.  Теперь вакансию необходимо разместить на на внешние веб-сайте, где люди смогут присылать (вы можете увидеть его щелкнув **вакансиях** ссылку). В настоящий момент задача по размещению вакансии лежит на представителе отдела кадров, который отвечает за ее размещение.  
  
2.  Отдела Кадров хочет изменить это объявление о вакансии (щелкнув **изменить** ссылку), задав время ожидания 60 минут (на самом деле это может быть дни или недели). Значение времени ожидания позволяет убрать объявление о вакансии с внешнего веб-узла по истечении указанного времени.  
  
3.  После сохранения измененного объявления, оно отображается в **получение резюме** вкладке (обновить веб-страницы, чтобы увидеть новое объявление о вакансии).  
  
### <a name="collecting-resumes"></a>Сбор резюме  
  
1.  Объявление о вакансии должно появиться на внешнем веб-узле. Если вы заинтересованы в этой работе, можно подать заявление на эту должность и подать свое резюме.  
  
2.  Если вернуться к службе Job Postings List, можно «просмотреть резюме» собранные на данный момент.  
  
3.  Отдел кадров также может остановить сбор резюме (например, после того как нужный кандидат был найден).  
  
## <a name="troubleshooting"></a>Устранение неполадок  
  
1.  Убедитесь, что Visual Studio выполняется с правами администратора.  
  
2.  Если решение не было построено, то проверьте следующее.  
  
    -   Ссылка на `ContosoHR` не пропущен `InternalClient` или `CareersWebSite` проектов.  
  
3.  Если решение не выполняется, убедитесь в следующем.  
  
    1.  Все службы работают.  
  
    2.  Ссылки на службы обновлены.  
  
        1.  Откройте папку App_WebReferences.  
  
        2.  Щелкните правой кнопкой мыши **Contoso** и выберите **обновление ссылок на веб-/ службы**.  
  
        3.  Перестройте решение, нажав клавиши CTRL + SHIFT + B в Visual Studio.  
  
## <a name="uninstalling"></a>Удаление  
  
1.  Удалите хранилище экземпляров SQL Server, для этого запустите файл Cleanup.bat из папки DbSetup.  
  
2.  Удалите исходный код с жесткого диска.