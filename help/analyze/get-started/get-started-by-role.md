---
description: Informações gerais sobre o Adobe Analytics, incluindo informações sobre sua interface e informações introdutórias para admins, analistas, usuários e desenvolvedores.
title: Introdução para administradores, analistas, usuários finais e desenvolvedores
feature: Analytics Basics
exl-id: 11800de5-224a-4bd2-8cb1-a6318925db71
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: tm+mt
source-wordcount: '1695'
ht-degree: 99%

---

# Introdução para administradores, analistas, usuários finais e desenvolvedores

Há quatro tipos de usuários do Adobe Analytics em uma organização típica:

* **Administradores:** implementam e configuram o Adobe Analytics.

* **Analistas:** configuram projetos e criam análises usando o Analysis Workspace

* **Usuários finais:** obtêm insights acionáveis sobre seus clientes, seja criando suas próprias análises ou trabalhando com analistas para criá-las

* **Desenvolvedores:** usam as APIs 2.0 do Adobe Analytics para chamar diretamente os servidores da Adobe e executar praticamente qualquer ação que possa ser executada na interface, como criar relatórios para explorar, obter insights ou responder a perguntas importantes sobre dados.

As informações abaixo descrevem como cada um desses usuários pode começar a usar o Adobe Analytics.

## Introdução para administradores

Administradores(as) do Analytics são os(as) responsáveis por escolher o método de implementação mais apropriado para sua organização.

Depois que o Adobe Analytics é implementado, os administradores precisam executar várias tarefas de configuração para garantir que os analistas e usuários finais estejam obtendo o máximo do Adobe Analytics. Os administradores também devem monitorar regularmente o seu ambiente do Analytics para garantir que o sistema esteja funcionando com eficiência.

### Determine os tipos de dados que devem ser coletados

O Adobe Analytics permite coletar dados de vários tipos de canais e reuni-los para fornecer insights significativos de clientes em tempo real.

A seguir estão alguns dos canais compatíveis nos quais os dados podem ser coletados:

* Telefones celulares

* A Internet das coisas

* TV

* Assistentes de voz

* Carros conectados

* E muito mais (novos canais compatíveis são adicionados regularmente)

O [método de implementação](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=pt-BR) escolhido determina o tipo dos dados que podem ser coletados.

### Implementação do Adobe Analytics

Vários métodos de implementação estão disponíveis ao implementar o Adobe Analytics em seu site ou aplicativo móvel.

Para obter informações sobre cada método disponível, consulte [Implementação do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=pt-BR).

| | Métodos de implementação |
|---------|---------|
| **Sites** | <ul><li>Extensão do SDK da Web (recomendado)</li><li>SDK da web</li><li>Extensão do Analytics</li><li>JavaScript herdado</li></ul> |
| **Aplicativos móveis** | <ul><li>Extensão do SDK móvel (recomendado)</li><li>Extensão do Analytics</li></ul> |

{style="table-layout:auto"}

### Configuração do Adobe Analytics

Administradores do Analytics devem concluir as seguintes tarefas antes de disponibilizar o Adobe Analytics para os usuários ou usuárias na organização:

| Tarefa | Uso pretendido | Mais informações |
|---------|----------|---------|
| Definir funções de administrador | O Adobe Analytics é compatível com vários tipos de administradores | [Funções de administrador no Adobe Analytics](https://experienceleague.adobe.com/pt-br/docs/analytics/admin/admin-console/admin-roles-in-analytics) |
| Definir permissões | Administradores(as) do Analytics precisam atribuir perfis de produto no Admin Console para o Adobe Analytics, as Ferramentas de conjuntos de relatórios e as Ferramentas do Analytics. | [Permissões do Analytics no Admin Console](/help/admin/admin-console/permissions/analytics-tools.md) |
| Configurar conjuntos de relatórios e definir as configurações para sua empresa | Um conjunto de relatórios é um silo de dados que o Adobe Analytics usa para gerar relatórios.<p>Administradores(as) também podem configurar [conjuntos de relatórios virtuais](https://experienceleague.adobe.com/pt-br/docs/analytics/components/virtual-report-suites/vrs-about) para segmentar ainda mais os dados.</p> | <ul><li>[Criar um novo conjunto de relatórios](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/c-new-report-suite/t-create-a-report-suite.html?lang=pt-BR)</li><li>[Visão geral das Configurações da empresa](https://experienceleague.adobe.com/pt-br/docs/analytics/admin/admin-tools/company-settings/c-company-settings)</li></ul> |
| Importação de dados | As fontes de dados do Adobe Analytics permitem importar dados adicionais, seja online ou offline, para relatórios. | [Visão geral das fontes de dados](https://experienceleague.adobe.com/pt-br/docs/analytics/import/data-sources/overview) |
| Classificação dos dados com Classificações | Classificações permitem classificar dados para um melhor uso das variáveis, permitindo incluir mais conteúdo em uma única variável. | [Visão geral das classificações](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-overview.html) |
| Gerenciamento de componentes | Use o Dicionário de dados e as áreas de gerenciamento em cada tipo de componente para definir quais componentes estão disponíveis na implementação do Analytics, bem como quais são aprovados para sua organização.<p>Essa deve ser uma atividade contínua para garantir que os componentes estejam sendo usados com eficiência em sua organização. </p> | <ul><li>[Visão geral do dicionário de dados](https://experienceleague.adobe.com/pt-br/docs/analytics/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview)</li><li>[Gerenciador de métricas calculadas](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=pt-BR)</li><li>[Gerenciar segmentos](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=pt-BR)</li><li>[Criar intervalos de datas personalizados](https://experienceleague.adobe.com/pt-br/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges)</li></ul> |
| Detecção de anomalias | A Detecção de anomalias oferece um método estatístico para determinar como uma certa métrica foi alterada com relação aos dados anteriores. | [Visão geral da Detecção de anomalias](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html?lang=pt-BR) |
| Análise de contribuição | A Análise de contribuição revela padrões ocultos nos dados para explicar anomalias estatísticas e identificar correlações por trás das ações inesperadas do cliente, dos valores fora do limite e dos picos ou declínios repentinos nas métricas selecionadas em segmentos convergentes do público-alvo. | [Visão geral da análise de contribuição](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis) |
| Segmentação do Analytics | Permite criar, gerenciar, compartilhar e aplicar segmentos de público-alvo avançados e focados em seus relatórios usando os recursos do Analytics, a Adobe Experience Cloud, o Adobe Target e outros produtos integrados da Adobe. | [Segmentação do Analytics](https://experienceleague.adobe.com/pt-br/docs/analytics/components/segmentation/seg-home) |
| Publicar públicos-alvo no Audience Manager | Adobe Audience Manager é uma eficiente plataforma de gerenciamento de dados que ajuda a criar perfis de público-alvo exclusivos a partir de integrações de dados primários, secundários (parceiros) e de terceiros. | [Visão geral do Audience Analytics](https://experienceleague.adobe.com/pt-br/docs/analytics/integration/audience-analytics/mc-audiences-aam) |
| Integrações | É possível exibir informações de outros aplicativos no Adobe Analytics. <p>Veja a seguir algumas integrações comuns:</p><ul><li><a href="https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=pt-BR">Analytics for Target</a></li><li><a href="https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/media-overview">Serviços de streaming de mídia</a></li> | [Integração do Analytics](https://experienceleague.adobe.com/docs/analytics/integration/home.html?lang=pt-BR) |

{style="table-layout:auto"}

### Monitoramento do Adobe Analytics

Vários recursos estão disponíveis para ajudar você a monitorar o ambiente do Adobe Analytics.

Os administradores do Analytics devem conhecer os seguintes recursos disponíveis que ajudam a monitorar aspectos importantes do ambiente do Analytics:

| Tarefa | Uso pretendido | Mais informações |
|---------|----------|---------|
| Gerenciador de atividades de relatórios | O Gerenciador de atividades de relatórios permite ver a capacidade de gerar relatórios para cada conjunto de relatórios na sua organização. Esse dispositivo oferece visibilidade detalhada do consumo de relatórios e ajuda a diagnosticar e corrigir problemas de capacidade facilmente durante os horários de pico de relatórios. | [Gerenciador de atividades de relatórios](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/reporting-activity.html) |
| Uso de chamadas do servidor | Uma chamada de servidor, também conhecida como “ocorrência” ou uma “solicitação de imagem”, é uma instância na qual os dados são enviados para os servidores da Adobe para processamento. Um painel de Uso de chamadas do servidor que monitora seus dados de consumo de chamadas do servidor e os compara ao limite contratual está disponível. É possível configurar alertas para evitar excessos. | [Visão geral do uso de chamadas do servidor](https://experienceleague.adobe.com/pt-br/docs/analytics/admin/admin-tools/server-call-usage/overage-overview) |
| Arquivos de log | Os arquivos de log ajudam a identificar quando os usuários fazem logon, suas atividades, acessos, conjuntos de relatórios e alterações de administrador. | [Logs](https://experienceleague.adobe.com/pt-br/docs/analytics/admin/admin-tools/logs) |

{style="table-layout:auto"}

## Introdução para Analistas

Embora qualquer pessoa em uma organização possa usar o Adobe Analytics para obter insights acionáveis sobre o comportamento de clientes em sites e aplicativos, o Adobe Analytics foi projetado tendo analistas de dados em mente.

Veja a seguir as principais tarefas e recursos que analistas devem conhecer para aproveitar todo o potencial do Adobe Analytics e do Analysis Workspace.

| Recurso | Uso pretendido | Mais informações |
|---------|----------|---------|
| Criação e compartilhamento de projetos no Analysis Workspace | O Analysis Workspace é uma ferramenta de navegador flexível que permite criar análises e compartilhar insights rapidamente. Usando a interface de arrastar e soltar, você pode criar a análise, adicionar visualizações para dar vida aos dados, preparar um conjunto de dados, compartilhar e agendar projetos com qualquer pessoa em sua organização.<p>Analistas de dados geralmente são responsáveis por criar projetos no Analysis Workspace para usuários ou usuárias em sua organização.</p><p>Após a criação dos projetos, os analistas os compartilham com os [usuários finais](#end-users)(não analistas) que solicitaram os dados em suas organizações e os ajudam a entender como interpretá-los.</p> | <ul><li>[Criação de projetos](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md)</li><li>[Compartilhamento de projetos](/help/analyze/analysis-workspace/curate-share/share-projects.md)</li></ul> |
| Atribuição | Analistas podem personalizar como os itens de dimensão recebem crédito por eventos bem-sucedidos empregando vários modelos de atribuição e janelas de pesquisa no Analysis Workspace.<p>Modelos de atribuição Linear distribui o crédito igualmente a todos os pontos de contato que levam a uma conversão, enquanto Primeiro contato distribui todo o crédito ao primeiro ponto de contato. Muitos outros modelos de atribuição estão disponíveis, incluindo o modelo Algorítmico, que usa técnicas estatísticas para determinar dinamicamente a alocação ideal de crédito. </p> | [Modelos de atribuição e janelas de pesquisa](/help/analyze/analysis-workspace/attribution/models.md) |
| Detecção de anomalias | O modelo estatístico no Analysis Workspace encontra tendências inesperadas em seus dados automaticamente, analisando métricas e determinando um limite inferior, um superior e, assim, o intervalo de valores esperado. Quando ocorrer um pico ou uma queda inesperada, o sistema irá alertá-lo no relatório. | [Visão geral da Detecção de anomalias](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) |
| Análise de contribuição | Use o Analysis Workspace para descobrir padrões ocultos nos dados e explicar anomalias estatísticas, identificando correlações por trás de ações inesperadas de clientes, de valores fora do limite e de picos ou declínios repentinos de métricas pelos segmentos de público-alvo. | [Análise de contribuição](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis) na [Visão geral da Detecção de anomalias](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) |
| Alertas | Crie e gerencie alertas com base em anomalias de dados e alertas “empilhados”, que capturam várias métricas em um único alerta. | [Visão geral de alertas](/help/components/c-alerts/intellligent-alerts.md) |
| Exportação de dados | O Data Warehouse e os Feeds de dados permitem exportar dados para vários destinos na nuvem, como Google Cloud Platform, Azure RBAC, Azure SAS ou Amazon S3. | [Guia de exportação do Analytics](https://experienceleague.adobe.com/docs/analytics/export/home.html?lang=pt-BR) |
| Activity Map | O Activity Map é um aplicativo do Adobe Analytics projetado para classificar a atividade de links, com o uso de sobreposições visuais e a disponibilização de um painel de análise em tempo real para monitorar a participação do público-alvo nas páginas da Web.<p>O Activity Map permite configurar diferentes exibições para identificar visualmente a aceleração da atividade do cliente, quantificar as iniciativas de marketing e agir conforme as necessidades e os comportamentos do público-alvo.</p> | [Activity Map](https://experienceleague.adobe.com/pt-br/docs/analytics/analyze/activity-map/activity-map) |
| Report Builder | O Report Builder é um suplemento do Microsoft Excel. O Report Builder permite criar solicitações personalizadas a partir de dados do Adobe Analytics que foram inseridos em suas planilhas do Excel. As solicitações podem fazer referência, de forma dinâmica, a células da planilha, e você pode atualizar e personalizar o modo como o Report Builder apresenta os dados. | [Report Builder](https://experienceleague.adobe.com/pt-br/docs/analytics/analyze/report-builder/rb-overview) |

<!-- * Realtime reporting? -->

## Introdução para usuários finais

Usuários finais que não são analistas profissionais podem trabalhar com analistas em sua organização para aproveitar todo o potencial do Adobe Analytics e do Analysis Workspace ou podem aprender as noções básicas do Analysis Workspace para obter insights acionáveis sobre seus clientes.

### Trabalhar com analistas

Normalmente, os usuários ou usuárias em uma organização que estão interessados em saber mais sobre o comportamento de clientes em seus vários sites não são analistas profissionais.

De forma ideal, esses usuários ou usuárias devem trabalhar com [analistas](#analysts) em uma organização para:

1. Definir os requisitos das análises explicando ao analista o que esperam saber sobre clientes.

1. Revisar as análises para garantir que atendam aos objetivos.

1. Discutir os dados obtidos das análises.

1. Modificar as análises conforme necessário ao longo do tempo.

### Criar análises no Analysis Workspace

Não é necessário ser um analista de dados para obter insights acionáveis do Adobe Analytics.

Alguns usuários ou usuárias podem achar útil trabalhar com um analista de dados para configurar um projeto no Analysis Workspace e para entender como interpretar os dados, conforme descrito em [Trabalhar com analistas](#work-with-analysts). Outros usuários ou usuárias podem se sentir confortáveis criando o projeto e interpretando os dados sozinhos.

O Analysis Workspace permite criar análises rapidamente para coletar insights e compartilhá-los com outras pessoas. Usando a interface de arrastar e soltar do navegador, você pode criar a análise, adicionar visualizações para dar vida aos dados, preparar um conjunto de dados e compartilhar e agendar projetos com quem você escolher.

Para obter informações sobre como criar análises no Analysis Workspace, consulte [Visão geral do Analysis Workspace](/help/analyze/analysis-workspace/home.md).

## Introdução para desenvolvedores

As [APIs do Analytics](https://developer.adobe.com/analytics-apis/docs/2.0/) permitem chamar diretamente os servidores da Adobe para executar quase todas as ações possíveis a partir da interface.

Você pode criar relatórios para explorar, obter insights ou responder perguntas importantes sobre seus dados. Você também pode gerenciar componentes do Adobe Analytics, como a criação de segmentos ou métricas calculadas.

>[!MORELIKETHIS]
>
>[Criar um documento de design de solução](/help/implement/prepare/solution-design.md)
>
