---
description: Informações gerais sobre o Adobe Analytics
title: Visão geral do Adobe Analytics
feature: Analytics Basics
hide: true
hidefromtoc: true
source-git-commit: 1c6cc23c9cb6b4b007d2f296ea23e697cc135bd4
workflow-type: tm+mt
source-wordcount: '3101'
ht-degree: 32%

---

# Visão geral do Adobe Analytics

O Adobe Analytics permite que as organizações reúnam dados e obtenham insights acionáveis de qualquer interação digital com o cliente. Com análise detalhada, relatórios versáteis e inteligência preditiva, as organizações obtêm a base inteligente de que precisam para criar melhores experiências para seus clientes.

## Principais benefícios

A seguir estão algumas das principais maneiras pelas quais a Adobe Analytics ajuda as organizações a obter insights críticos para atender melhor seus clientes.

Para obter detalhes adicionais sobre os benefícios oferecidos pela Adobe Analytics, consulte a [Página do produto Adobe Analytics](https://business.adobe.com/products/analytics/adobe-analytics.html).

### Análise da Web

O Adobe Analytics fornece as seguintes ferramentas complexas de segmentação e previsão para analisar o tráfego do site:

* [Ad hoc analysis no Analysis Workspace](/help/analyze/analysis-workspace/home.md)

* [Análise de fluxo](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)

* [Segmentação avançada](/https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html)

### Análise de marketing

O Adobe Analytics ajuda as organizações a entender onde os clientes interagem com suas marcas, quais canais os clientes preferem e quais experiências refletem neles.

Os principais recursos do Adobe Analytics a seguir oferecem esses recursos de marketing:

* Coleção de dados multicanal

* [Integração de dados offline](https://experienceleague.adobe.com/docs/analytics/import/data-sources/overview.html?lang=en)

* [Ad hoc analysis no Analysis Workspace](/help/analyze/analysis-workspace/home.md)

### Atribuição

A atribuição permite que as organizações vejam como diferentes interações na jornada do cliente afetam a conversão. Além de fornecer opções de atribuição mais tradicionais, como modelos Linear ou de Primeiro contato, o Attribution no Adobe Analytics também usa aprendizado de máquina e modelos estatísticos avançados para entender o impacto preciso de cada contato.

Para obter mais informações, consulte [Modelos de atribuição e janelas de pesquisa](/help/analyze/analysis-workspace/attribution/models.md).


### Análise preditiva

A Análise preditiva usa aprendizagem de máquina e modelagem estatística avançada para analisar dados do cliente, encontrar padrões e prever o comportamento futuro, como churn ou uma probabilidade de conversão. Ele permite que os analistas de dados aproveitem grandes conjuntos de dados que, de outra forma, seriam desperdiçados.

Os principais recursos do Adobe Analytics a seguir fornecem esses recursos preditivos:

* [Detecção de anomalias](#anomaly-detection)

* [Análise de contribuição](#contribution-analysis)

* [Alertas inteligentes](#intelligent-alerts)

## Pré-requisitos para usar o Adobe Analytics

Antes de usar o Adobe Analytics, você deve ter:

* Uma licença válida do Adobe Analytics

  O Adobe Analytics exige uma licença de site. Entre em contato com seu representante de conta Adobe para obter mais informações. <!--is this phrased correctly? Is this important? -->

* Um navegador compatível

  Cada usuário que acessa o Adobe Analytics deve usar um navegador compatível. Para obter mais informações, consulte [Requisitos de sistema do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/admin-overview/sys-reqs.html?lang=en).

<!-- are there more? -->

## Entender a interface do Analytics

A interface do Adobe Analytics consiste nas seguintes áreas principais:

### Guia Espaço de trabalho

A variável [!UICONTROL Workspace] mostra uma lista de projetos do Analysis Workspace.

1. No Adobe Analytics, selecione a variável [!UICONTROL **Workspace**] guia.

   ![Guia Espaço de trabalho](assets/landing-all2.png)

Para obter mais informações sobre os recursos e as funções disponíveis no [!UICONTROL Workspace] , consulte [Página de aterrissagem do Adobe Analytics](/help/analyze/landing.md).

### Guia Relatórios

A partir de 31 de dezembro de 2023, a Adobe pretende descontinuar o Reports &amp; Analytics, juntamente com os relatórios e recursos que o acompanham.

Use o botão [!UICONTROL **Relatórios**] área no painel esquerdo na [!UICONTROL **Workspace**] guia. Para obter mais informações, consulte *Navegue até a guia Relatórios* in [Página de aterrissagem do Adobe Analytics](/help/analyze/landing.md).

### Guia Componentes

A variável [!UICONTROL Componentes] A guia inclui recursos que ajudam a ajustar e potencializar a análise de dados.

1. No Adobe Analytics, selecione a variável [!UICONTROL **Componentes**] e selecione [!UICONTROL **Todos os componentes**].

   ![Guia Espaço de trabalho](assets/components-tab.png)

2. Selecione qualquer um dos seguintes recursos do produto para configurá-lo:


   | Recurso do produto | Função | Mais informações |
   |---------|----------|----------|
   | Segmentos  | O Adobe Analytics permite construir, gerenciar, compartilhar e aplicar segmentos avançados de público-alvo em seus relatórios usando os recursos do Analytics, a Adobe Experience Cloud, o Adobe Target e outros produtos integrados da Adobe. | [Segmentação do Analytics](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html?lang=pt-BR) |
   | Métricas calculadas  | Métricas calculadas e calculadas avançadas (ou derivadas) são métricas personalizadas que podem ser criadas a partir de métricas existentes.  Eles permitem que profissionais de marketing, gerentes de produtos e analistas façam perguntas sobre os dados sem precisarem alterar a implementação do Analytics. | [Métricas calculadas e calculadas avançadas (derivadas)](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/cm-overview.html?lang=pt-BR) |
   | Intervalos de datas | O Analysis Workspace inclui uma lista de intervalos de datas padrão que os usuários podem usar ao criar análises. Além disso, você pode criar intervalos de datas personalizados e disponibilizá-los aos usuários no Analysis Workspace. | [Criar intervalos de datas personalizados](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=pt-BR) <!-- should create an article in the Components Guide for managing/creating date ranges. This article in the Tools Guide needs updating. --> |
   | Conjuntos de relatórios virtuais |  |  |
   | Alertas | Os Alertas inteligentes permitem um controle mais detalhado dos alertas e integra a detecção de anomalias ao sistema de alertas. | [Alertas inteligentes](https://experienceleague.adobe.com/docs/analytics/components/alerts/intellligent-alerts.html?lang=en) |
   | Metas | Metas permitem medir o desempenho do site e acompanhar o progresso em relação às metas-alvo. Quando você cria metas, você seleciona quais métricas de atributo ou eVars você quer medir ou você pode optar por medir o seu site inteiro contra a métrica selecionada. <p>As metas fazem parte do Reports &amp; Analytics. Leia mais sobre o [Anúncio do fim da vida útil](https://express.adobe.com/page/6WnF8JK6IRDhf/) do Reports &amp; Analytics.</p> | [Metas](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/targets.html?lang=en) |
   | Eventos de calendário | Para os relatórios com tendência ao longo do tempo, os eventos do calendário permitem exibir graficamente os eventos e verificar se as campanhas ou outros eventos afetaram o tráfego do site, a receita ou qualquer outra métrica. | [Eventos de calendário](https://experienceleague.adobe.com/docs/analytics/components/t-calendar-event.html?lang=en) |
   | Anotações | As anotações no Espaço de trabalho permitem comunicar com eficiência nuances de dados contextuais e insights à sua organização. Eles permitem vincular eventos de calendário a dimensões e métricas específicas. | [Gerenciar anotações](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/annotations/manage-annotations.html?lang=en) |
   | Conjuntos de classificação | Os conjuntos de classificações fornecem uma única interface para gerenciar classificações e regras. <p>Classificação é uma forma de categorização de dados variáveis do Analytics, que exibe os dados de diferentes maneiras quando você gera os relatórios. Você estabelece uma relação entre um valor variável e os metadados relacionados a esse valor. As classificações podem ser usadas na maioria das dimensões personalizadas, como Código de rastreamento, props e eVars.</p> | [Visão geral dos conjuntos de classificação](https://experienceleague.adobe.com/docs/analytics/components/classifications/sets/overview.html?lang=pt-BR) |
   | Localizações | Para importar dados de classificação do Adobe Analytics de um destino na nuvem, primeiro adicione e configure o local onde deseja que os dados de classificação sejam coletados. É possível criar, editar ou excluir locais. | [Gerenciador de locais](https://experienceleague.adobe.com/docs/analytics/components/locations/locations-manager.html?lang=en) |
   | Projetos programados | Ao gerenciar projetos agendados, você pode editar e excluir agendamentos de projetos recorrentes; pesquisar um agendamento na barra de pesquisa ou usando as opções de filtro no painel esquerdo; e filtrar por tag, agendamentos aprovados, proprietários e muito mais. | [Projetos programados](/help/components/scheduled-projects-manager.md) |
   | Marcadores | Os marcadores concedem acesso aos relatórios que você mais usa. Os marcadores criados são adicionados à Experience Cloud e estão disponíveis em recursos integrados como conectores de dados. <p>Os marcadores fazem parte do Reports &amp; Analytics. Leia mais sobre o [Anúncio do fim da vida útil](https://express.adobe.com/page/6WnF8JK6IRDhf/) do Reports &amp; Analytics. | [Gerenciador de marcador](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/bookmarks.html?lang=en) |
   | Painéis | Os painéis são criados para visualizar métricas e fornecer recursos de análise interativa com dados. Ao clicar em itens em um painel, você pode segmentar os dados de forma rápida e fácil para derivar informações de sua análise. <p>Os painéis fazem parte do Data Workbench. Leia mais sobre a Data Workbench [Anúncio de fim da vida útil](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=en). | [Gerenciador de painel](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/dashboard-manage.html?lang=en) |
   | Relatórios agendados | Os usuários de nível administrativo podem visualizar e gerenciar relatórios agendados em toda a organização. | [Relação de relatórios agendados](https://experienceleague.adobe.com/docs/analytics/components/scheduled-reports-admin.html?lang=en) |
   | Configurações do relatório | Essas configurações se referem a produtos Adobe Analytics herdados, o que exclui o Analysis Workspace e seus componentes relacionados. Para fazer ajustes nas configurações do Analysis Workspace, acesse Componentes > Preferências. |  |
   | Preferências | Gerencie configurações para o Analysis Workspace e seus componentes relacionados para todos os novos projetos ou painéis que você criar. Os projetos e painéis existentes não são afetados. | [Preferências](/help/analyze/analysis-workspace/user-preferences.md) |

   {style="table-layout:auto"}

### Guia Ferramentas

A guia Ferramentas ...

1. No Adobe Analytics, selecione a variável [!UICONTROL **Ferramentas**] e selecione [!UICONTROL **Todas as ferramentas**].

   ![Guia Espaço de trabalho](assets/tools-tab.png)

2. Selecione qualquer um dos seguintes recursos do produto para configurá-lo:

   | Recurso do produto | Função | Mais informações |
   |---------|----------|----------|
   | Data Warehouse | Data Warehouse refere-se à cópia dos dados do Analytics para fins de armazenamento e relatórios personalizados, que podem ser executados ao filtrar os dados. <p>O Gerenciador de solicitações permite que você visualize, duplique e priorize novamente as solicitações.</p> | [Gerenciar solicitações do Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-requests-manage.html?lang=en) |
   | Activity Map | O Activity Map foi projetado para classificar a atividade de links, usando sobreposições visuais e fornecer um painel de análise em tempo real para monitorar a participação do público-alvo nas páginas da Web. Ele permite configurar diferentes exibições para identificar visualmente a aceleração da atividade do cliente, quantificar as iniciativas de marketing e agir de acordo com as necessidades e os comportamentos do público-alvo. | [Visão geral do Activity Map](https://experienceleague.adobe.com/docs/analytics/analyze/activity-map/activity-map.html?lang=pt-BR) |
   | Recommendations Classic |  |  |
   | Search&amp;Promote |  |  |
   | Mobile Services |  |  |
   | Painéis do Analytics (aplicativo móvel) |  |  |
   | Report Builder |  |  |

   {style="table-layout:auto"}

### Guia Admin

A guia Administrador ...

1. No Adobe Analytics, selecione a variável [!UICONTROL **Admin**] e selecione [!UICONTROL **Todos os administradores**].

   ![Guia Espaço de trabalho](assets/admin-tab.png)

## Introdução para administradores, analistas e usuários finais

Há três tipos de usuários do Adobe Analytics em uma organização típica: administradores, analistas e usuários finais.

Os administradores implementam e configuram o Adobe Analytics; os analistas configuram projetos e criam análises usando o Analysis Workspace, e os usuários finais obtêm insights acionáveis sobre seus clientes, criando suas próprias análises ou trabalhando com analistas para criá-las.

Expanda as seções abaixo para saber como cada um desses usuários pode começar a usar o Adobe Analytics.

### Introdução para administradores

Os administradores do Analytics são responsáveis por escolher o método de implementação mais apropriado para sua organização.

Depois que o Adobe Analytics é implementado, os administradores precisam executar várias tarefas de configuração para garantir que os analistas e usuários finais estejam obtendo o valor total do Adobe Analytics.

#### Determine os tipos de dados que devem ser coletados

O Adobe Analytics permite coletar dados de vários tipos de canais e reuni-los para fornecer insights significativos e em tempo real ao cliente.

A seguir estão alguns dos canais compatíveis nos quais os dados podem ser coletados:

* Telefones celulares

* A Internet das Coisas

* TV

* Assistentes de voz

* Carros conectados

* E muito mais (novos canais compatíveis são adicionados regularmente)

A variável [método de implementação](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=pt-BR) escolha determina o tipo de dados que podem ser coletados.

#### Implementação do Adobe Analytics

Vários métodos de implementação estão disponíveis ao implementar o Adobe Analytics em seu site ou aplicativo móvel.

Para obter informações sobre cada método disponível, consulte [Implementar o Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=pt-BR).

| | Métodos de implementação |
|---------|---------|
| **Sites** | <ul><li>Extensão SDK da Web (recomendado)</li><li>SDK da Web</li><li>Extensão do Analytics</li><li>JavaScript herdado</li></ul> |
| **Aplicativos móveis** | <ul><li>Extensão SDK móvel (recomendado)</li><li>Extensão do Analytics</li></ul> |

{style="table-layout:auto"}

#### Configurar Adobe Analytics

Os administradores do Analytics devem concluir as seguintes tarefas antes de disponibilizar o Adobe Analytics para os usuários na organização:

| Tarefa | Uso previsto | Mais informações |
|---------|----------|---------|
| Definir funções de administrador | O Adobe Analytics é compatível com vários tipos de administradores | [Funções de administrador no Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/admin-roles-in-analytics.html?lang=en) |
| Definir permissões | Os administradores do Analytics precisam atribuir perfis de produto no Admin Console para o Adobe Analytics, as Ferramentas de conjuntos de relatórios e as Ferramentas do Analytics. | [Permissões do Analytics no Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html?lang=pt-BR) |
| Configurar conjuntos de relatórios e definir configurações para sua empresa | Um conjunto de relatórios é um silo de dados que o Adobe Analytics usa para gerar relatórios.<p>Os administradores também podem configurar [conjuntos de relatórios virtuais](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=pt-BR) para segmentar mais dados.</p> | <ul><li>[Criar um novo conjunto de relatórios](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/c-new-report-suite/t-create-a-report-suite.html?lang=en)</li><li>[Visão geral das configurações da empresa](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/company-settings/c-company-settings.html?lang=en)</li></ul> |
| Importar dados | As fontes de dados do Adobe Analytics permitem importar dados online e offline adicionais para os relatórios. | [Visão geral das fontes de dados](https://experienceleague.adobe.com/docs/analytics/import/data-sources/overview.html?lang=en) |
| Classificar dados com classificações | As classificações permitem classificar dados para melhor uso das variáveis, permitindo incluir mais conteúdo em uma única variável. | |
| Gerenciamento de componentes | Use o Dicionário de dados e as áreas de gerenciamento para cada tipo de componente para definir quais componentes estão disponíveis na implementação do Analytics, bem como quais são aprovados para sua organização.<p>Essa deve ser uma atividade contínua para garantir que os componentes estejam sendo usados com eficiência em sua organização. </p> | <ul><li>[Visão geral do dicionário de dados](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.html?lang=pt-BR)</li><li>[Gerenciador de métricas calculadas](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=en)</li><li>[Gerenciar segmentos](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=pt-BR)</li><li>[Criar intervalos de datas personalizados](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=pt-BR)</li></ul> |
| Detecção de anomalias e Análise de contribuição | | |
| Segmentação avançada | | |
| Publicar públicos no Audience Manager | | |
| Atribuição | | |
| Gerenciador de atividades de relatórios | | |
| Integrações | Você pode exibir informações de outros aplicativos no Adobe Analytics. <p>Veja a seguir algumas integrações comuns:</p><ul><li><a href="https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=en">Analytics for Target</a></li><li><a href="https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=pt-BR">Media Analytics</a></li> | |

{style="table-layout:auto"}

### Introdução para analistas

Embora qualquer pessoa em uma organização possa usar o Adobe Analytics para obter insights acionáveis sobre o comportamento do cliente em sites e aplicativos, o Adobe Analytics foi projetado tendo os analistas de dados em mente.

Veja a seguir as principais tarefas e recursos que os analistas devem conhecer para aproveitar todo o potencial do Adobe Analytics e do Analysis Workspace.

| Recurso | Uso previsto | Mais informações |
|---------|----------|---------|
| Criar e compartilhar projetos no Analysis Workspace | O Analysis Workspace é uma ferramenta de navegador flexível que permite criar análises e compartilhar insights rapidamente. Usando a interface de arrastar e soltar, você pode criar a análise, adicionar visualizações para dar vida aos dados, preparar um conjunto de dados, compartilhar e agendar projetos com qualquer pessoa em sua organização.<p>Os analistas de dados geralmente são responsáveis por criar projetos no Analysis Workspace para usuários em sua organização.</p><p>Após a criação dos projetos, os analistas compartilham esses projetos com a [usuários finais](#end-users)(não analistas) em suas organizações que solicitaram os dados e os ajudaram a entender como interpretá-los.</p> | <ul><li>[Criar projetos](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md)</li><li>[Compartilhar projetos](/help/analyze/analysis-workspace/curate-share/share-projects.md)</li></ul> |
| Atribuição | Os analistas podem personalizar como os itens de dimensão recebem crédito por eventos bem-sucedidos empregando vários modelos de atribuição e janelas de pesquisa no Analysis Workspace.<p>Modelos de atribuição linear oferecem crédito igual a todos os pontos de contato que levam a uma conversão, enquanto Primeiro contato oferece crédito total ao primeiro ponto de contato. Muitos outros modelos de atribuição estão disponíveis, incluindo o Modelo algorítmico, que usa técnicas estatísticas para determinar dinamicamente a alocação ideal de crédito. </p> | [Modelos de atribuição e janelas de pesquisa](/help/analyze/analysis-workspace/attribution/models.md) |
| Detecção de anomalias | O modelo estatístico no Analysis Workspace encontra automaticamente tendências inesperadas em seus dados, analisando métricas e determinando um limite inferior, um limite superior e o intervalo esperado de valores. Quando ocorrer um pico ou uma queda inesperada, o sistema irá alertá-lo no relatório. | [Visão geral da Detecção de anomalias](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) |
| Análise de contribuição | Use o Analysis Workspace para descobrir padrões ocultos nos dados para explicar anomalias estatísticas e identificar correlações por trás das ações inesperadas do cliente, dos valores fora do limite e dos picos ou declínios repentinos nas métricas nos segmentos de público-alvo. | [Visão geral da análise de contribuição](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md) |
| Alertas inteligentes | Crie e gerencie alertas com base em anomalias de dados e alertas &quot;empilhados&quot;, que capturam várias métricas em um único alerta. | [Visão geral de alertas inteligentes](help/analyze/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md) |
| Exportação de dados | O Data Warehouse e os Feeds de dados permitem exportar dados para vários destinos na nuvem, como Google Cloud Platform, Azure RBAC, Azure SAS e Amazon S3. | [Guia de exportação do Analytics](https://experienceleague.adobe.com/docs/analytics/export/home.html?lang=pt-BR) |
| Activity Map | O Activity Map é um aplicativo do Adobe Analytics projetado para classificar a atividade de links, com o uso de sobreposições visuais e a disponibilização de um painel de análise em tempo real para monitorar a participação do público-alvo nas páginas da Web.<p>O Activity Map permite configurar diferentes exibições para identificar visualmente a aceleração da atividade do cliente, quantificar as iniciativas de marketing e agir conforme as necessidades e os comportamentos do público-alvo.</p> | [Activity Map](https://experienceleague.adobe.com/docs/analytics/analyze/activity-map/activity-map.html?lang=pt-BR) |
| Report Builder | O Report Builder é um suplemento do Microsoft Excel. O Report Builder permite criar solicitações personalizadas a partir de dados do Adobe Analytics que foram inseridos em suas planilhas do Excel. As solicitações podem fazer referência, de forma dinâmica, a células da planilha, e você pode atualizar e personalizar o modo como o Report Builder apresenta os dados. | [Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/home.html?lang=pt-BR) |

{style="table-layout:auto"}

<!-- * Realtime reporting? -->

### Introdução para usuários finais

Os usuários finais que não são analistas profissionais podem trabalhar com analistas em sua organização para aproveitar todo o potencial do Adobe Analytics e do Analysis Workspace ou podem aprender as noções básicas do Analysis Workspace para começar a obter insights acionáveis sobre seus clientes.

#### Trabalhar com analistas

Normalmente, os usuários em uma organização que estão interessados em saber mais sobre o comportamento do cliente em seus vários sites não são analistas profissionais.

Idealmente, esses usuários devem trabalhar com [analistas](#analysts) em uma organização para:

1. Defina os requisitos das análises explicando ao analista o que ele espera saber sobre os clientes.

1. Revise as análises para garantir que atendam aos objetivos.

1. Discuta os dados obtidos com as análises.

1. Modifique as análises conforme necessário ao longo do tempo.

#### Criar análises no Analysis Workspace

Você não precisa ser um analista de dados para obter insights acionáveis do Adobe Analytics.

Alguns usuários podem achar útil trabalhar com um analista de dados para configurar um projeto no Analysis Workspace e explicar como interpretar os dados, conforme descrito em [Trabalhar com analistas](#work-with-analysts); outros usuários podem se sentir confortáveis em criar o projeto e interpretar os dados.

O Analysis Workspace permite criar análises rapidamente para coletar insights e compartilhá-los com outras pessoas. Usando a interface de arrastar e soltar do navegador, você pode criar a análise, adicionar visualizações para dar vida aos dados, preparar um conjunto de dados e compartilhar e agendar projetos com quem você escolher.

Para obter informações sobre como criar análises no Analysis Workspace, consulte [Visão geral do Analysis Workspace](/help/analyze/analysis-workspace/home.md).

### Introdução para desenvolvedores

[As APIs do Analytics permitem que você chame diretamente os servidores da Adobe para executar quase todas as ações possíveis a partir da interface.](https://developer.adobe.com/analytics-apis/docs/2.0/)

Você pode criar relatórios para explorar, obter insights ou responder perguntas importantes sobre seus dados. Você também pode gerenciar componentes do Adobe Analytics, como a criação de segmentos ou métricas calculadas.

## Vídeo de visão geral

Para saber mais sobre as noções básicas do Adobe Analytics, confira este *Introdução ao Adobe Analytics - Webinário do Skill Builder* vídeo. O vídeo aborda as noções básicas de como os dados são obtidos e enviados para o Adobe Analytics, além de quais recursos de visualização podem ser usados no Adobe Analytics. O vídeo fornece uma base para você criar, implantar, coletar e interpretar dados, permitindo que você forneça insights e recomendações acionáveis com base nos dados coletados.

>[!VIDEO](https://video.tv.adobe.com/v/27429/?quality=12)

Caso tenha dúvidas sobre qual ferramenta usar, consulte [Qual ferramenta do Adobe Analytics devo usar?](https://experienceleague.adobe.com/docs/analytics/analyze/admin-overview/which-analytics-tool.html?lang=pt-BR).

## Vá além com o Customer Journey Analytics

O Customer Journey Analytics é a solução analítica de próxima geração da Adobe que permite usar o potencial do Analysis Workspace com dados da Adobe Experience Platform. Ele pode detalhar, filtrar, consultar e visualizar os dados de anos, e é combinado com a capacidade da Platform de armazenar todos os tipos de esquemas e tipos de dados.

Veja a seguir algumas das vantagens do Customer Journey Analytics em relação ao Adobe Analytics:

* **Variáveis e eventos ilimitados**: os conceitos de eVars, props e eventos não existem mais. Os dados se concentram principalmente em dimensões e métricas. Os conjuntos de dados podem ter um número ilimitado de dimensões e métricas exclusivas.

* **Valores exclusivos limitados**: a Adobe Experience Platform não está restrita a qualquer limitação exclusiva.

* **Alterar dados históricos**: com a Adobe Experience Platform, os dados podem ser removidos ou corrigidos.

* **Dados entre conjuntos de relatórios**: as implementações existentes de vários conjuntos de dados podem ser combinadas na Platform.

Para obter mais informações, consulte [visão geral do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=pt-BR).

