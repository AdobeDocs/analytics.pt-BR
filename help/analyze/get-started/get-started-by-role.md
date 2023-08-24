---
description: Informações gerais de visão geral sobre o Adobe Analytics, incluindo informações sobre a interface do Analytics e informações de introdução para administradores, analistas, usuários e desenvolvedores.
title: Introdução para administradores, analistas, usuários finais e desenvolvedores
feature: Analytics Basics
hide: true
hidefromtoc: true
source-git-commit: f23e0c74072d38d5c6559288b2ced60d98634fac
workflow-type: tm+mt
source-wordcount: '1812'
ht-degree: 34%

---

# Introdução para administradores, analistas, usuários finais e desenvolvedores

Há três tipos de usuários do Adobe Analytics em uma organização típica: administradores, analistas e usuários finais.

Os administradores implementam e configuram o Adobe Analytics; os analistas configuram projetos e criam análises usando o Analysis Workspace, e os usuários finais obtêm insights acionáveis sobre seus clientes, criando suas próprias análises ou trabalhando com analistas para criá-las.

As informações abaixo descrevem como cada um desses usuários pode começar a usar o Adobe Analytics.

## Introdução para administradores

Os administradores do Analytics são responsáveis por escolher o método de implementação mais apropriado para sua organização.

Depois que o Adobe Analytics é implementado, os administradores precisam executar várias tarefas de configuração para garantir que os analistas e usuários finais estejam obtendo o valor total do Adobe Analytics. Os administradores também devem monitorar regularmente o ambiente do Analytics para garantir que o sistema esteja funcionando com eficiência.

### Determine os tipos de dados que devem ser coletados

O Adobe Analytics permite coletar dados de vários tipos de canais e reuni-los para fornecer insights significativos e em tempo real ao cliente.

A seguir estão alguns dos canais compatíveis nos quais os dados podem ser coletados:

* Telefones celulares

* A Internet das Coisas

* TV

* Assistentes de voz

* Carros conectados

* E muito mais (novos canais compatíveis são adicionados regularmente)

A variável [método de implementação](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=pt-BR) escolha determina o tipo de dados que podem ser coletados.

### Implementação do Adobe Analytics

Vários métodos de implementação estão disponíveis ao implementar o Adobe Analytics em seu site ou aplicativo móvel.

Para obter informações sobre cada método disponível, consulte [Implementar o Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=pt-BR).

| | Métodos de implementação |
|---------|---------|
| **Sites** | <ul><li>Extensão SDK da Web (recomendado)</li><li>SDK da Web</li><li>Extensão do Analytics</li><li>JavaScript herdado</li></ul> |
| **Aplicativos móveis** | <ul><li>Extensão SDK móvel (recomendado)</li><li>Extensão do Analytics</li></ul> |

{style="table-layout:auto"}

### Configurar Adobe Analytics

Os administradores do Analytics devem concluir as seguintes tarefas antes de disponibilizar o Adobe Analytics para os usuários na organização:

| Tarefa | Uso previsto | Mais informações |
|---------|----------|---------|
| Definir funções de administrador | O Adobe Analytics é compatível com vários tipos de administradores | [Funções de administrador no Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/admin-roles-in-analytics.html?lang=en) |
| Definir permissões | Os administradores do Analytics precisam atribuir perfis de produto no Admin Console para o Adobe Analytics, as Ferramentas de conjuntos de relatórios e as Ferramentas do Analytics. | [Permissões do Analytics no Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html?lang=pt-BR) |
| Configurar conjuntos de relatórios e definir configurações para sua empresa | Um conjunto de relatórios é um silo de dados que o Adobe Analytics usa para gerar relatórios.<p>Os administradores também podem configurar [conjuntos de relatórios virtuais](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=pt-BR) para segmentar mais dados.</p> | <ul><li>[Criar um novo conjunto de relatórios](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/c-new-report-suite/t-create-a-report-suite.html?lang=en)</li><li>[Visão geral das configurações da empresa](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/company-settings/c-company-settings.html?lang=en)</li></ul> |
| Importar dados | As fontes de dados do Adobe Analytics permitem importar dados online e offline adicionais para os relatórios. | [Visão geral das fontes de dados](https://experienceleague.adobe.com/docs/analytics/import/data-sources/overview.html?lang=en) |
| Classificar dados com classificações | As classificações permitem classificar dados para melhor uso das variáveis, permitindo incluir mais conteúdo em uma única variável. | |
| Gerenciamento de componentes | Use o Dicionário de dados e as áreas de gerenciamento para cada tipo de componente para definir quais componentes estão disponíveis na implementação do Analytics, bem como quais são aprovados para sua organização.<p>Essa deve ser uma atividade contínua para garantir que os componentes estejam sendo usados com eficiência em sua organização. </p> | <ul><li>[Visão geral do dicionário de dados](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.html?lang=pt-BR)</li><li>[Gerenciador de métricas calculadas](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=en)</li><li>[Gerenciar segmentos](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=pt-BR)</li><li>[Criar intervalos de datas personalizados](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=pt-BR)</li></ul> |
| Detecção de anomalias | A Detecção de anomalias oferece um método estatístico para determinar como uma certa métrica foi alterada com relação aos dados anteriores. | [Visão geral da Detecção de anomalias](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html?lang=pt-BR) |
| Análise de contribuição | A Análise de contribuição revela padrões ocultos nos dados para explicar anomalias estatísticas e identificar correlações por trás das ações inesperadas do cliente, dos valores fora do limite e dos picos ou declínios repentinos nas métricas selecionadas em segmentos convergentes do público-alvo. | [Visão geral da análise de contribuição](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.html?lang=pt-BR) |
| Segmentação do Analytics | Permite criar, gerenciar, compartilhar e aplicar segmentos avançados de público-alvo em seus relatórios usando os recursos do Analytics, o Adobe Experience Cloud, o Adobe Target e outros produtos Adobe integrados. | [Segmentação do Analytics](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html?lang=pt-BR) |
| Publicar públicos no Audience Manager | | |
| Integrações | Você pode exibir informações de outros aplicativos no Adobe Analytics. <p>Veja a seguir algumas integrações comuns:</p><ul><li><a href="https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=en">Analytics for Target</a></li><li><a href="https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=pt-BR">Media Analytics</a></li> | |

{style="table-layout:auto"}

### Monitorar Adobe Analytics

Vários recursos estão disponíveis para ajudar você a monitorar o ambiente do Adobe Analytics.

Os administradores do Analytics devem estar cientes dos seguintes recursos disponíveis para ajudar a monitorar aspectos importantes do seu ambiente do Analytics:

| Tarefa | Uso previsto | Mais informações |
|---------|----------|---------|
| Gerenciador de atividades de relatórios | O Gerente de atividades de relatórios permite ver a capacidade de gerar relatórios para cada conjunto de relatórios na sua organização. Ele oferece visibilidade detalhada do consumo de relatórios e ajuda a diagnosticar e corrigir problemas de capacidade facilmente durante o pico dos relatórios. | [Gerenciador de atividades de relatórios](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/reporting-activity.html?lang=en) |
| Uso de chamadas do servidor | Uma chamada de servidor, também conhecida como &quot;ocorrência&quot; ou uma &quot;solicitação de imagem&quot;, é uma instância na qual os dados são enviados para os servidores da Adobe para processamento. Um painel de Uso de chamadas do servidor está disponível e rastreia os dados de consumo de chamadas do servidor e os compara ao limite contratual. Você pode configurar alertas para evitar sobreposições. | [Visão geral do Uso de chamadas do servidor](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-call-usage/overage-overview.html?lang=en) |
| Arquivos de log | Os arquivos de log ajudam a identificar quando os usuários fazem logon, suas atividades, acessos, conjuntos de relatórios e alterações de Admin. | [Logs](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/logs.html?lang=pt-BR) |

{style="table-layout:auto"}

## Introdução para analistas

Embora qualquer pessoa em uma organização possa usar o Adobe Analytics para obter insights acionáveis sobre o comportamento do cliente em sites e aplicativos, o Adobe Analytics foi projetado tendo os analistas de dados em mente.

Veja a seguir as principais tarefas e recursos que os analistas devem conhecer para aproveitar todo o potencial do Adobe Analytics e do Analysis Workspace.

| Recurso | Uso previsto | Mais informações |
|---------|----------|---------|
| Criar e compartilhar projetos no Analysis Workspace | O Analysis Workspace é uma ferramenta de navegador flexível que permite criar análises e compartilhar insights rapidamente. Usando a interface de arrastar e soltar, você pode criar a análise, adicionar visualizações para dar vida aos dados, preparar um conjunto de dados, compartilhar e agendar projetos com qualquer pessoa em sua organização.<p>Os analistas de dados geralmente são responsáveis por criar projetos no Analysis Workspace para usuários em sua organização.</p><p>Após a criação dos projetos, os analistas compartilham esses projetos com a [usuários finais](#end-users)(não analistas) em suas organizações que solicitaram os dados e os ajudaram a entender como interpretá-los.</p> | <ul><li>[Criar projetos](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md)</li><li>[Compartilhar projetos](/help/analyze/analysis-workspace/curate-share/share-projects.md)</li></ul> |
| Atribuição | Os analistas podem personalizar como os itens de dimensão recebem crédito por eventos bem-sucedidos empregando vários modelos de atribuição e janelas de pesquisa no Analysis Workspace.<p>Modelos de atribuição linear oferecem crédito igual a todos os pontos de contato que levam a uma conversão, enquanto Primeiro contato oferece crédito total ao primeiro ponto de contato. Muitos outros modelos de atribuição estão disponíveis, incluindo o Modelo algorítmico, que usa técnicas estatísticas para determinar dinamicamente a alocação ideal de crédito. </p> | [Modelos de atribuição e janelas de pesquisa](/help/analyze/analysis-workspace/attribution/models.md) |
| Detecção de anomalias | O modelo estatístico no Analysis Workspace encontra automaticamente tendências inesperadas em seus dados, analisando métricas e determinando um limite inferior, um limite superior e o intervalo esperado de valores. Quando ocorrer um pico ou uma queda inesperada, o sistema irá alertá-lo no relatório. | [Visão geral da Detecção de anomalias](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) |
| Análise de contribuição | Use o Analysis Workspace para descobrir padrões ocultos nos dados para explicar anomalias estatísticas e identificar correlações por trás das ações inesperadas do cliente, dos valores fora do limite e dos picos ou declínios repentinos nas métricas nos segmentos de público-alvo. | [Visão geral da análise de contribuição](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md) |
| Alertas inteligentes | Crie e gerencie alertas com base em anomalias de dados e alertas &quot;empilhados&quot;, que capturam várias métricas em um único alerta. | [Visão geral de alertas inteligentes](/help/analyze/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md) |
| Exportação de dados | O Data Warehouse e os Feeds de dados permitem exportar dados para vários destinos na nuvem, como Google Cloud Platform, Azure RBAC, Azure SAS e Amazon S3. | [Guia de exportação do Analytics](https://experienceleague.adobe.com/docs/analytics/export/home.html?lang=pt-BR) |
| Activity Map | O Activity Map é um aplicativo do Adobe Analytics projetado para classificar a atividade de links, com o uso de sobreposições visuais e a disponibilização de um painel de análise em tempo real para monitorar a participação do público-alvo nas páginas da Web.<p>O Activity Map permite configurar diferentes exibições para identificar visualmente a aceleração da atividade do cliente, quantificar as iniciativas de marketing e agir conforme as necessidades e os comportamentos do público-alvo.</p> | [Activity Map](https://experienceleague.adobe.com/docs/analytics/analyze/activity-map/activity-map.html?lang=pt-BR) |
| Report Builder | O Report Builder é um suplemento do Microsoft Excel. O Report Builder permite criar solicitações personalizadas a partir de dados do Adobe Analytics que foram inseridos em suas planilhas do Excel. As solicitações podem fazer referência, de forma dinâmica, a células da planilha, e você pode atualizar e personalizar o modo como o Report Builder apresenta os dados. | [Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/home.html?lang=pt-BR) |

{style="table-layout:auto"}

<!-- * Realtime reporting? -->

## Introdução para usuários finais

Os usuários finais que não são analistas profissionais podem trabalhar com analistas em sua organização para aproveitar todo o potencial do Adobe Analytics e do Analysis Workspace ou podem aprender as noções básicas do Analysis Workspace para começar a obter insights acionáveis sobre seus clientes.

### Trabalhar com analistas

Normalmente, os usuários em uma organização que estão interessados em saber mais sobre o comportamento do cliente em seus vários sites não são analistas profissionais.

Idealmente, esses usuários devem trabalhar com [analistas](#analysts) em uma organização para:

1. Defina os requisitos das análises explicando ao analista o que ele espera saber sobre os clientes.

1. Revise as análises para garantir que atendam aos objetivos.

1. Discuta os dados obtidos com as análises.

1. Modifique as análises conforme necessário ao longo do tempo.

### Criar análises no Analysis Workspace

Você não precisa ser um analista de dados para obter insights acionáveis do Adobe Analytics.

Alguns usuários podem achar útil trabalhar com um analista de dados para configurar um projeto no Analysis Workspace e explicar como interpretar os dados, conforme descrito em [Trabalhar com analistas](#work-with-analysts); outros usuários podem se sentir confortáveis em criar o projeto e interpretar os dados.

O Analysis Workspace permite criar análises rapidamente para coletar insights e compartilhá-los com outras pessoas. Usando a interface de arrastar e soltar do navegador, você pode criar a análise, adicionar visualizações para dar vida aos dados, preparar um conjunto de dados e compartilhar e agendar projetos com quem você escolher.

Para obter informações sobre como criar análises no Analysis Workspace, consulte [Visão geral do Analysis Workspace](/help/analyze/analysis-workspace/home.md).

## Introdução para desenvolvedores

[As APIs do Analytics permitem que você chame diretamente os servidores da Adobe para executar quase todas as ações possíveis a partir da interface.](https://developer.adobe.com/analytics-apis/docs/2.0/)

Você pode criar relatórios para explorar, obter insights ou responder perguntas importantes sobre seus dados. Você também pode gerenciar componentes do Adobe Analytics, como a criação de segmentos ou métricas calculadas.