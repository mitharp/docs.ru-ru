---
title: Действия в рабочем процессе внешнего цикла DevOps для приложения Docker
description: Инструкции по «внешний цикл» рабочего процесса DevOps
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: b75e9df1c31e8bcebcaa6d56336a6aa499d13e1d
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/13/2019
ms.locfileid: "56220943"
---
# <a name="steps-in-the-outer-loop-devops-workflow-for-a-docker-application"></a>Действия в рабочем процессе внешнего цикла DevOps для приложения Docker

Рис. 5-1 представляет end-to-end, описание шагов, составляющих рабочий процесс DevOps для внешнего цикла.

![](./media/image1.png)

Рис. 5-1. Рабочий процесс внешнего цикла DevOps для приложений Docker с использованием средств Майкрософт

Теперь давайте рассмотрим каждое из этих действий более подробно.

## <a name="step-1-inner-loop-development-workflow"></a>Шаг 1. Рабочий процесс внутреннего цикла разработки

Этот шаг описан подробно в главе 4, но Напомню, Вот где начинается внешний цикл некоторое время, по которому разработчик помещает код в систему управления версиями (например, Git), инициированные действия конвейера непрерывной Интеграции.

## <a name="step-2-source-code-control-integration-and-management-with-azure-devops-services-and-git"></a>Шаг 2. Интеграция системы управления версиями и управление с помощью служб Azure DevOps и Git

На этом этапе необходимо иметь систему управления версиями для сбора консолидированных версию весь код, поступающие от разные разработчики в команде.

Несмотря на то, что система управления версиями (SCC) и управления версиями может показаться привычкой цикл для большинства разработчиков, при создании приложений с помощью Docker жизни DevOps, очень важно подчеркнуть, что вам не нужно отправить образов Docker с приложением непосредственно в глобальной Docker реестр (например, реестр контейнеров Azure или Docker Hub) с компьютера разработчика. Напротив образов Docker освобождение и развертываемых в рабочих средах должны создаваться только на исходный код, который интегрируется в глобальной сборке или конвейер непрерывной Интеграции, исходя из репозитория исходного кода (например, Git).

Локальные изображения, созданные разработчиками, сами следует использовать только разработчиками при тестировании в своих собственных компьютерах. Именно поэтому крайне важно иметь конвейер DevOps, активировать из кода SCC.

Azure DevOps Services и Team Foundation Server поддерживает Git и системы управления версиями Team Foundation. Можно выбрать между ними и использовать его для качества Microsoft end-to-end. Тем не менее, также можно управлять код во внешних репозиториях (например, GitHub, на локальном репозитории Git или Subversion) и по-прежнему иметь возможность подключиться к нему и получите код как начальную точку для конвейера DevOps CI.

## <a name="step-3-build-ci-integrate-and-test-with-azure-devops-services-and-docker"></a>Шаг 3. Сборки непрерывной Интеграции, интеграции и тестирование с помощью Azure DevOps служб и Docker

Непрерывная Интеграция стал стандартом для тестирования современного программного обеспечения и доставки. Решение Docker обеспечивает четкое разделение между командами разработки и операций. Неизменность образов Docker обеспечивает Повторяемое развертывание между что разработки, тестирования через непрерывной Интеграции и запустить в рабочей среде. Подсистема docker развернуть на ноутбуках разработчика и инфраструктуру тестирования делает контейнеры портативных в средах.

На этом этапе после систему управления версиями с правильный код отправки, вам потребуется *служба сборок* для кода и запустить глобальной сборки и тестирования.

О построении конвейера непрерывной Интеграции, состоящий из репозитория кода (Git т. д.), сервер сборки (службы Azure DevOps), подсистема Docker и в реестр Docker является внутреннего рабочего процесса для выполнения этого шага (непрерывной Интеграции, сборки, тестирования).

Позволяет службам DevOps в Azure как основа для построения приложений и настройка конвейера непрерывной Интеграции, а также для публикации «артефактов сборки» «репозитория артефактов,» как описано в следующем шаге.

При использовании Docker для развертывания «итоговые версии артефактов» для развертывания образов Docker с помощью приложения или служб, внедренных в них. Эти образы являются отправлена или опубликовать его *реестра Docker* (частный репозиторий, например тех, которые имеются в реестре контейнеров Azure, или любой общедоступный как реестре центра Docker, которая часто используется для официальных базовых образах).

Вот основной принцип: Конвейер непрерывной Интеграции будет создан off путем фиксации в репозиторий SCC как Git. Фиксация вызовет служб Azure DevOps запустить задание сборки в контейнере Docker и, после успешного завершения этого задания можно передать образ Docker в реестр Docker, как показано на рисунке 5-2.

![](./media/image2.png)

Рис. 5-2. Действия, связанные с непрерывной Интеграции

Ниже приведены основные этапы рабочего процесса непрерывной Интеграции с решениями Docker и служб Azure DevOps.

1.  Разработчик отправляет фиксацию с репозиторием SCC (Git/Azure DevOps Services, GitHub, и т.д.).

2.  Если вы используете Azure DevOps Services или Git, CI является встроенной, что означает, что это сложнее, чем установка флажка в службах Azure DevOps. Если вы используете внешние SCC (например, GitHub), *веб-перехватчика* будет уведомлять служб Azure DevOps, обновления или передать в Git и GitHub.

3.  Службы Azure DevOps извлекает хранилище SCC, включая DockerFile, описывающий изображение, а также код приложения и тестов.

4.  Службы DevOps Azure создает образ Docker и помечает его с номером сборки.

5.  Службы Azure DevOps создает в контейнере Docker в подготовленный компьютер Docker и запускает соответствующие тесты.

6.  Если тесты проходят успешно, изображение сначала помечается значащее имя, чтобы вы знаете, «blessed сборки» (например «/ 1.0.0» или любые другие метки) и затем передается в реестр Docker (Docker Hub, реестр контейнеров Azure, DTR т. д.)

### <a name="implementing-the-ci-pipeline-with-azure-devops-services-and-the-docker-extension-for-azure-devops-services"></a>Реализация в конвейер непрерывной Интеграции с помощью служб Azure DevOps и расширения Docker для служб Azure DevOps

[Расширения Docker служб Azure DevOps](https://aka.ms/vstsdockerextension) добавляет задачу в ваш конвейер непрерывной Интеграции, с помощью которого можно создание образов Docker, отправлять образы Docker в реестр Docker с поддержкой аутентификации, запуска образов Docker или выполнить другие операции, предоставляемые Docker ИНТЕРФЕЙС КОМАНДНОЙ СТРОКИ. Он также добавляет задачи Docker Compose, который можно использовать для сборки, Push-уведомлений и запуска многоконтейнерного приложения Docker или выполнить другие операции, предоставляемые Docker Compose интерфейса командной строки, как показано на рисунке 5-3.

![](./media/image3.png)

Рис. 5-3. Конвейер непрерывной Интеграции Docker в службах Azure DevOps

Расширение Docker можно использовать конечные точки службы, для узлов Docker, а также для контейнера и реестры образов. По умолчанию задачи с помощью локального узла Docker, если он доступен (в настоящее время для этого создайте пользовательский агент служб Azure DevOps); в противном случае они требуют введения подключения к узлу Docker. Действия, которые зависят от того, выполняется проверка подлинности с помощью реестра Docker, такие как отправка образа, необходимо предоставить Docker подключения к реестру.

Расширение Docker службы DevOps Azure устанавливает следующие компоненты в вашей учетной записи служб Azure DevOps:

-   Конечную точку службы для подключения к реестру Docker

-   Конечную точку службы для подключения к узлу контейнера Docker

-   Выполните следующие задачи Docker:

-   Создайте образ

-   Отправка образа или репозитория в реестр

-   Запуск образа в контейнере

-   Выполнение команд Docker

-   Задачи Docker Compose для выполнения команды Docker Compose

Эти задачи служб Azure DevOps, сборки узлов и виртуальных Машин Docker в Linux, подготовленного в Azure и предпочтительным реестра Docker (реестр контейнеров Azure, Docker Hub, закрытый DTR Docker или другой реестр Docker) можно создать конвейер непрерывной Интеграции Docker в очень согласованность.

***Требования:***

-   Службы Azure DevOps, или для локальных установок Team Foundation Server 2015 с обновлением 3 или более поздней версии.

-   Агент служб Azure DevOps, который содержит двоичные файлы Docker.

Простой способ создать один из них — использовать Docker для запуска контейнера на основе образа Docker агент служб Azure DevOps.

**Дополнительные сведения о** для чтения сведения о создании элемента конфигурации Docker служб Azure DevOps конвейера и просмотр пошаговые руководства, посетите следующие сайты:

Агент служб Azure DevOps, как контейнер Docker: [ https://hub.docker.com/r/\ microsoft/vsts-agent /](https://hub.docker.com/r/microsoft/vsts-agent/)

Расширение Azure Docker службы DevOps: <https://aka.ms/vstsdockerextension>

Создание образов Docker для Linux .NET Core с помощью служб Azure DevOps: <https://blogs.msdn.microsoft.com/stevelasker/2016/06/13/building-net-core-linux-docker-images-with-visual-studio-team-services/>

Создание компьютера под управлением Linux Visual Studio Team Service сборки с поддержкой Docker: <http://donovanbrown.com/post/2016/06/03/Building-a-Linux-Based-Visual-Studio-Team-Service-Build-Machine-with-Docker-Support>

### <a name="integrate-test-and-validate-multicontainer-docker-applications"></a>Интеграция, тестировать и проверять многоконтейнерного приложения Docker

Как правило большинство приложений Docker состоят из нескольких контейнеров, а не в одном контейнере. Хороший пример — это приложение, ориентированных на микрослужбы, для которого имеется один контейнер на микрослужбы. Но даже без строго следующим шаблонам микрослужб подход, это очень вероятно, что приложение Docker будет состоять из нескольких контейнеров или служб.

Таким образом после создания контейнеров приложений в конвейере непрерывной Интеграции, необходимо также развернуть, интеграции и тестирование приложения в целом все его контейнеры в узле Docker integration или даже в кластер тестирования, к которому будут контейнеров распределенные.

Если вы используете один узел, можно использовать команды Docker, такие как docker-compose для создания и развертывания связанных контейнеров для тестирования и проверки среды Docker в одной виртуальной Машины. Но если вы работаете с кластером orchestrator, такие как DC/OS, Kubernetes или Docker Swarm, необходимо выполнить развертывание контейнеров посредством другого механизма или orchestrator, в зависимости от выбранного кластера или планировщика.

Ниже приведены несколько типов тестов, которые можно выполнять на контейнеры Docker.

-   Модульные тесты для контейнеров Docker

-   Тестирование групп взаимосвязанных приложений и микрослужб

-   Тестирование в рабочей среде и «перестраховочным» выпуски

Важно то, что при выполнении интеграционных и функциональных тестов, необходимо выполнить эти тесты из вне контейнеров. Тесты должны не определен и выполняющихся в контейнерах, которые вы выполняете развертывание, так как контейнеры основаны на статические изображения, которые должны быть так же, как те, которые вы будете развертывать в рабочей среде.

Очень неразумны при тестировании более сложные сценарии, такие как тестирование нескольких кластеров (проверки кластера, промежуточный кластер и рабочий кластер) является публикация образов в реестр для проверки в различных кластеров.

### <a name="push-the-custom-application-docker-image-into-your-global-docker-registry"></a>Передать образ Docker пользовательского приложения в глобальной реестра Docker

После тестирования и проверки образов Docker, стоит теги и публиковать их в реестр Docker. Реестр Docker — ключевой компонент в жизненный цикл приложения Docker, так как это централизованное место, где хранятся пользовательские теста (также называемые «blessed images») будет развернут в контроля Качества и рабочей средах.

Подобно как код приложения, хранящиеся в репозитории SCC (например, Git) — «источник истины», реестр Docker — «источник истины» для двоичных приложения или bits для контроля Качества или рабочей среде развертывания.

Как правило может потребоваться у ваших частных репозиториев для пользовательских образов в частный репозиторий в реестре контейнеров Azure на локальный реестр как доверенный реестр Docker или в реестре и общедоступное облако с ограниченным доступом (например Docker Hub), несмотря на то что в последнем случае если код не является открытым исходным кодом, должны доверять безопасности поставщика. В любом случае метод, по которому этого многом схоже, в конечном счете по команде docker Push-уведомлений, как показано на рисунке 5-4.

![](./media/image4.png)

Рис. 5-4. Публикация пользовательских образов в реестре Docker

Имеется несколько предложений реестров Docker из поставщиков облачных решений, таких как реестр контейнеров Azure, реестр контейнеров Amazon Web Services, реестр контейнеров Google, Quay реестра и т. д.

Использование расширения Docker служб Azure DevOps, вы можете передать набор обслуживания образов, определением в файле docker-compose.yml с несколько тегов, в реестр Docker, прошедшего проверку подлинности (например, реестр контейнеров Azure), как показано на рисунке 5-5.

![](./media/image5.png)

Рис. 5-5: Использование служб Azure DevOps для публикации пользовательских образов в реестр Docker

**Дополнительные сведения о** Дополнительные сведения о расширении Docker для служб Azure DevOps, перейдите к <https://aka.ms/vstsdockerextension>. Дополнительные сведения о реестре контейнеров Azure, перейдите к <https://aka.ms/azurecontainerregistry>.

## <a name="step-4-cd-deploy"></a>Шаг 4. Компакт-ДИСК, развертывание

Неизменность образов Docker гарантирует воспроизводимые развертывания с что разработки, тестирования через непрерывной Интеграции и запустить в рабочей среде. После образы Docker приложений, опубликованных в реестр Docker (частный или общедоступный), их можно развернуть в нескольких средах, которые могут иметь (производство, контроля Качества, промежуточного хранения, и т.д.) из конвейера компакт-диска с помощью служб Azure DevOps конвейер задачи или Azure DevOps Services Release Management.

Однако на этом этапе он зависит от какого рода приложения Docker при развертывании. Развертывание простого приложения (с композиции и развертывания точки зрения) как монолитного приложения, включающего в себя несколько контейнеров или служб и развернутых несколько серверов или виртуальных машин — очень отличается от процесса развертывания более сложное приложение как ориентированных на микрослужбы приложения с возможностями обработки. Эти два сценария описаны в следующих разделах.

### <a name="deploying-composed-docker-applications-to-multiple-docker-environments"></a>Развертывание составных приложений Docker в нескольких средах Docker

Рассмотрим сначала в менее сложных сценарий: развертывание в простой узлов Docker (виртуальные машины или серверы) в среде одного или нескольких сред (контроля Качества, промежуточной и рабочей). В этом случае конвейере непрерывной Поставки можно использовать внутри docker-compose (из задач развертывания служб Azure DevOps) для развертывания приложений Docker с набором связанных контейнеров или служб, как показано на рисунке 5-6.

![](./media/image6.png)

Рис. 5-6. Развертывание контейнеров приложения простой реестр среды узла Docker

Рис. 5-7 выделяет, как можно соединиться с вашей сборки CI среды контроля Качества и тестирования с помощью служб Azure DevOps, щелкнув Docker Compose в диалоговом окне Добавить задачу. Тем не менее, при развертывании в промежуточной или рабочей среде, обычно используется Release Management возможности обработки нескольких сред (например контроля Качества, промежуточной и рабочей). При развертывании на отдельные узлы Docker, она использует службы Azure DevOps «Docker Compose» задачи (который вызывает docker-команды взгляд изнутри compose up). При развертывании в службе контейнеров Azure, использует задачу развертывания Docker, как описано в следующем разделе.

![](./media/image7.png)

Рис. 5-7: Добавление задачи Docker Compose в конвейере служб Azure DevOps

При создании выпуска в службах Azure DevOps, он принимает набор входных артефакты. Они предназначены быть неизменными на протяжении всего времени существования выпуска в нескольких средах. При введении контейнеры входной артефакты идентификации образов в реестре для развертывания. В зависимости от того, как они определены они не гарантированно не изменяются на протяжении выпуска, самый очевидный случай, при создании ссылки «myimage:latest» из файла docker-Compose.

Расширение Docker для служб Azure DevOps дает возможность создать артефакты сборки, содержащие изображения реестра формирует дайджест, гарантированно уникальным идентификатором один двоичный образ. Это те, что Вы действительно хотите использовать в качестве входных данных для выпуска.

### <a name="managing-releases-to-docker-environments-by-using-azure-devops-services-release-management"></a>Управление выпусками в средах Docker с помощью управления выпусками служб Azure DevOps

Через расширения служб Azure DevOps, как создавать новый образ, опубликуйте его в реестр Docker, запустите его на узлах Linux или Windows и использовать команды, такие как docker-compose для развертывания нескольких контейнеров в качестве приложение целиком, все это Azure DevOps Возможности управления выпусками, предназначены для нескольких сред служб, как показано на рис. 5-8.

![](./media/image8.png)

Рис. 5-8. Настройка задачи Azure DevOps служб Docker Compose в управлении выпусками служб Azure DevOps

Однако следует помнить, что в сценарии, показано на рис. 5-6 и реализован на рис. 5-8 довольно прост (развертывание простой Docker узлов и виртуальных машин, и будет существовать на одном контейнере или экземпляр каждого образа) и, возможно, следует использовать только для разработки или тестирования sc enarios. В большинстве корпоративных сценариев рабочей среде, следует иметь высокий уровень доступности (HA) и более простой в управлении масштабируемость, балансировку нагрузки нескольких узлов, серверы и виртуальные машины, а также «интеллектуальные отработки отказа» таким образом, если сервер или узел в случае сбоя его службы и контейнеры будут переведены на другом сервере узла или виртуальной Машины. В этом случае необходимо более сложных технологий, таких как кластеры контейнеров, планировщики и оркестраторы. Таким образом способ развертывания к этим кластерам – точно сложных сценариев, как описано в следующем разделе.

### <a name="deploying-complex-docker-applications-to-docker-clusters-dcos-kubernetes-and-docker-swarm"></a>Развертывание сложных приложений Docker в кластеры Docker (DC/OS, Kubernetes и Docker Swarm)

Характер распределенных приложений требует вычислительных ресурсов, которые также распространяются. Чтобы рабочая возможности, необходимо иметь кластеризации возможности, которые обеспечивают высокий уровень масштабируемости и высокой ДОСТУПНОСТИ на основе пула ресурсов.

Можно развернуть контейнеры вручную к этим кластерам с помощью интерфейса командной строки средства, такие как Docker Swarm (например, использование [создания службы docker](https://docs.docker.com/engine/swarm/swarm-tutorial/deploy-service/)) или веб-интерфейса такие как [Mesosphere Marathon](https://mesosphere.github.io/marathon/docs/marathon-ui.html) DC/OS кластеров, но вы должны Зарезервируйте, только для тестирования punctual развертывания или в целях управления, таких как масштабирование или наблюдения.

С точки зрения компакт-диска, а также службам DevOps в Azure в частности, можно выполнять задачи по развертыванию специально сделан из среды Azure DevOps Services Release Management, которые развернет контейнерное приложение распределенные кластеры в контейнере Службы, как показано на рисунке 5-9.

![](./media/image9.png)

Рис. 5-9. Развертывание распределенных приложений в службе контейнеров

Изначально при развертывании для некоторых кластеров или оркестраторы, традиционно используется сценарии развертывания и механизма каждого каждого оркестратора (то есть, Mesosphere DC/OS или Kubernetes реализуйте механизмы развертывания, чем Docker и Docker Swarm) вместо более простой и простой в использовании docker-compose средство на основе файла docker-compose.yml определения. Тем не менее, благодаря DevOps служб Microsoft Azure Docker Deploy задаче показано на рисунке 5-10, теперь также развертыванием для DC/OS, просто с помощью файла знаком docker-compose.yml, так как Майкрософт не выполняет этот «перевод» автоматически (из вашей файл docker-compose.yml в другие форматы, необходимые для DC/OS).

![](./media/image10.png)

Рис. 5-10. Добавление задачи развертывания Docker RM вашей среды

Рис. 5-11 показано, как можно изменить в задачу развертывания Docker и указать тип объекта (Azure DC/OS службы контейнеров, в данном случае), файл Docker Compose и подключение к реестру Docker (например, реестр контейнеров Azure или Docker Hub). Это происходит, когда задача извлечет готовые к использованию пользовательских образов Docker для развертывания как контейнеры в кластере DC/OS.

![](./media/image11.png)

Рис. 5-11. Docker развернуть задача определения развертывание в Azure DC/OS службы контейнеров

**Дополнительные сведения о** Дополнительные сведения о конвейере компакт-диска с помощью служб Azure DevOps и Docker, посетите следующие сайты:

Расширение службы DevOps в Azure для Docker и службы контейнеров Azure: [ https://aka.ms/\ vstsdockerextension](https://aka.ms/vstsdockerextension)

Служба контейнеров Azure: <https://aka.ms/azurecontainerservice>

Mesosphere DC/OS: <https://mesosphere.com/product/>

## <a name="step-5-run-and-manage"></a>Шаг 5. Запуск и управление ими

Так как выполнение приложений и управления ими в рабочей среде корпоративного уровня является главной темой в самого себя и из-за тип операций, людей, работающих на этом уровне (ИТ-операций), а также большого объема в этой области, мы приложили все рядом Глава описано его.

## <a name="step-6-monitor-and-diagnose"></a>Шаг 6. Мониторинг и диагностика

В этом разделе также рассматривается в следующей главе как часть задач, выполняемых ИТ-операций в рабочих системах; Тем не менее важно подчеркнуть, что информации, полученной на этом шаге нужно передать обратно к группе разработки, таким образом, чтобы приложение постоянно повышается. С этой точки зрения, он также является частью DevOps, несмотря на то, что задачи и операции, обычно выполняются с ИТ.

Только в том случае, если мониторинг и диагностика — 100 процентов, в области DevOps являются мониторинга процессов и аналитики, выполняемая команда разработчиков средах тестирования или бета-версии. Это делается путем выполнения нагрузочного тестирования или просто отслеживая бета-версии или контроля Качества средах, где тест-инженеров бета-версия устанавливается на новые версии.

>[!div class="step-by-step"]
>[Назад](index.md)
>[Вперед](create-ci-cd-pipelines-azure-devops-services-aspnetcore-kubernetes.md)
