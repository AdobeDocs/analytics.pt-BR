---
description: Esta seção contém os principais conceitos do Adobe Analytics, uma breve descrição do conceito e um link de documentação específica com detalhes adicionais sobre o tópico.
title: Adobe Analytics - Principais conceitos
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Adobe Analytics - Principais conceitos

Esta seção contém os principais conceitos do Adobe Analytics, uma breve descrição do conceito e um link de documentação específica com detalhes adicionais sobre o tópico.

## Analytics tools {#concept_833EDD4EB056491DA1BC5A3A45FE285B}

| Produto | Descrição | Link da documentação |
|--- |--- |--- |
| Analysis Workspace | Solução de navegador para criar projetos de análise robustos e personalizados e democratizar insights. Oferece mais flexibilidade de relatórios que os Relatórios e análises | [adobe.ly/aaworkspacedocs](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/analysis-workspace-features.html) |
| Relatórios e análises (antigo SiteCatalyst) | Solução de navegador para relatórios e análises. Ferramenta inicial no pacote do Analytics. | [Página inicial do Relatórios e análises](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/getting-started.html) |
| Report Builder | O suplemento do Excel que permite criar solicitações personalizadas a partir de dados do Adobe Analytics e visualizá-las usando o Microsoft Excel. | [Página inicial do Construtor de relatórios](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/home.html) |
| Análise ad hoc (antigo Discover) | Ferramenta baseada em Java para análise digital avançada. | [Página inicial da análise ad hoc](https://docs.adobe.com/content/help/en/analytics/analyze/ad-hoc-analysis/adhoc-home.html) |
| Análise de big data (antigo Insight) | Desenvolvido para coletar, processar, analisar e visualizar dados de interações online e offline do cliente em vários canais. | [Cliente da análise de big data](https://marketing.adobe.com/resources/help/en_US/insight/client/) |
| Data Warehouse | Dados brutos e não processados para armazenamento e relatórios personalizados, que podem ser executados por meio da filtragem de dados. Sem nível de ocorrências. | [Página inicial do Data Warehouse](https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/data-warehouse.html) |
| Adobe Mobile Services | Reúne recursos de marketing móvel para aplicativos móveis de toda a Adobe Experience Cloud, permitindo que você entenda e aprimore a participação do usuário com seus aplicativos. | [Página inicial do Mobile Services](https://docs.adobe.com/content/help/en/mobile-services/using/home.html) |
| Conectores de dados do Adobe Exchange (antigo Genesis) | Importe dados de rastreamento de aplicativos de terceiros para o Analytics, para dar visibilidade completa ao desempenho em um local central. | [Página inicial dos Conectores de dados](https://marketing.adobe.com/developer/documentation/genesis/c-overview-how-it-works) |
| Gerenciamento dinâmico de tags (DTM) | Ajuda a gerenciar suas tags do Analytics, do Target e de outras soluções em todos os seus sites, independentemente do número de domínios. | [Página inicial do DTM](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/dtm-implementation-overview.html) |
| Adobe Launch | A próxima geração de recursos de gerenciamento de tags do site e SDK móvel da Adobe. | [Início do Adobe Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html) |

## Key terminology {#concept_E473ACBB8E4A42B4AC005538AC12F154}

Clique [aqui](https://docs.adobe.com/content/help/en/analytics/technotes/terms.html) para obter um glossário expandido com os termos do Adobe Analytics.

| Termo | Descrição | Link da documentação |
|--- |--- |--- |
| Props (Tráfego personalizado) | Dimensões usadas para rastrear a atividade de tráfego do site página por página. As props não persistem entre páginas. Principais aplicações das variáveis de tráfego: <ul><li>Contagem simples para encontrar o 'mais popular' de um valor específico</li><li>Visibilidade de como os usuários estão definindo caminho pelo site </li></ul><br>Exemplos de variáveis de tráfego: Nome da página, Seções do site, Navegadores</br> | [Props](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/traffic-variables/traffic-var.html) |
| eVar (conversão personalizada) | Dimensões que persistem por um período personalizado por você. As opções de expiração incluem expiração de evento, expiração de visita ou expiração do dia X, e devem ser orientadas pelo tipo de análise que será realizada nessa variável.<br>Principais diferenças entre eVars e props:</br><ul><li>As props são frequentemente usadas para a análise de definição de caminho porque a persistência é removida.</li><li>Geralmente, as eVars são usadas para análise de conversão.</li></ul><br>Exemplos de variáveis de conversão: Termos de pesquisa interna, Promoções internas, Campanhas externas (s.campaign)</br> | [eVars](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html) |
| Eventos/métricas (s.events) | Métricas que medem as principais ações que queremos que nossos visitantes executem em nosso site. Há três tipos de eventos: Contador, Numérico e Moeda. Os eventos são mais úteis quando adicionados aos relatórios da variável de conversão (eVar). A eVar oferece as informações qualitativas sobre o que aconteceu, e o Evento oferece informações quantitativas sobre o que aconteceu. <br>Principais diferenças entre eVars e eventos:</br><ul><li>As eVars informam quem, o que ou qual afetou a conversão</li><li>Os eventos medem quantas conversões ocorreram</li></ul><br>Exemplos de eventos de conversão: Pedidos, Inícios de aplicação, Clientes potenciais, Receita.</br> | [Eventos](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/success-events/success-event.html) |
| Componentes | Dimensões, métricas, segmentos e granularidades de tempo (intervalos de datas) que você pode arrastar e soltar em um projeto. | [Componentes](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html) |
| Dimensões | Coleção de eVars, props, classificações e valores coletados padrão da Adobe. | [Dimensões](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-descriptions.html) |
| Métricas | Coleção de eventos implementados e métricas calculadas. | [Métricas](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/apply-create-metrics.html) |
| Métricas calculadas | Capacidade de derivar métricas personalizadas de métricas existentes capturadas por meio de sua implementação. | [Métricas calculadas](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/cm-overview.html) |
| Segmentos | Capacidade de criar, gerenciar, compartilhar e aplicar segmentos de público-alvo focados nos relatórios do Analytics. Os segmentos são compartilhados nos produtos do Analytics e podem ser compartilhados na Experience Cloud. | [Segmentação](https://docs.adobe.com/content/help/en/analytics/components/segmentation/seg-home.html) |
| Hora (intervalos de datas) | Capacidade de filtrar a data para qualquer período de tempo e criar intervalos de datas personalizados que podem ser reutilizados em sua análise. | [Intervalos de datas](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html) |
| Visualizações | Visualizações avançadas que podem ajudar a dar vida aos dados em seus projetos. | [Visualizações](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) |
| Preparação | Capacidade de limitar os componentes acessíveis em um projeto ou Conjunto de relatórios virtuais. | [Comparação](https://docs.adobe.com/content/help/en/analytics/components/virtual-report-suites/vrs-components.html)<br>[deCuradoria de](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html)</br><br>[Projeto de VRS](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate-projects-vrs.html) |

## Relatórios principais

| Relatório | Descrição | Link da documentação |
|--- |--- |--- |
| Lista completa de dimensões/relatórios | Definição de todas as dimensões e relatórios disponíveis no Adobe Analytics. | [Dimensões](https://marketing.adobe.com/resources/help/en_US/reference/reports_descriptions.html) |
| Advertising Analytics | Analise todos os dados de pesquisa paga do Google e do Bing lado a lado no Adobe Analytics. As dimensões criadas por meio da integração incluem Plataforma de anúncio, Palavra-chave, Tipo de correspondência etc. As métricas criadas são Impressões AMO, Cliques AMO, Custo AMO, Média. Posição e Média. Pontuação de qualidade do AMO. | [Advertising Analytics](https://docs.adobe.com/help/en/analytics/integration/advertising-analytics/overview.html) |
| Audience Analytics | Enriqueça as ocorrências de entrada do Analytics com a associação de público-alvo de um usuário no AAM. você pode incorporar dados de público-alvo do AAM, como informações demográficas (por exemplo, gênero ou nível de renda), informações psicográficas (por exemplo, interesses e hobbies), dados do CRM e dados de impressão de anúncios em qualquer fluxo de trabalho do Analytics. As dimensões criadas por meio dessa integração são ID de público-alvo e Nome de público-alvo. | [Audience Analytics](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/mc-audiences-aam.html) |
| Attribution IQ | Permite que você entenda como um envolvimento significativo ocorre na jornada do cliente, identificando de forma inteligente os pontos de inflexão que levam os clientes a direcionar os resultados, otimizando efetivamente as iniciativas de marketing. Os modelos incluem primeiro, último, linear, participação, em forma de j, em forma de j inversa, forma de u, mesmo toque, personalizado e decaimento de tempo. | [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution.html) |
| Detecção de anomalias | Um método estatístico para determinar como uma determinada métrica foi alterada em relação aos dados anteriores. O AD é ativado por padrão para todas as visualizações de tendências na Analysis Workspace. | [Detecção de anomalias](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html) |
| Análise de contribuição | Explora o "porquê" por trás das anomalias que ocorrem, executando uma análise automatizada de cada métrica e dimensão a que você tem acesso. | [Análise de contribuição](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.html) |
| Análise de coorte | Um coorte é um grupo de pessoas que compartilham características comuns em um período especificado. A análise de coorte ajuda a analisar a retenção e a rotatividade de seus usuários. | [Análise de coorte](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.html) |
| Relatórios de jornada do cliente | Exibe informações sobre o caminho que seus usuários tomam em seu site ou aplicativo. Prop, eVars e eventos podem ser usados nesta análise na Analysis Workspace. | [Fallout da Analysis Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html)[Análise do espaço de trabalho](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/flow/flow.html)[Fluxo Relatórios e análises](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-paths.html) |
| Canais de marketing | Relatórios que ajudam você a entender quais canais externos levam os usuários ao seu site e o que é mais eficaz para impulsionar a conversão. As exibições da atribuição de Primeiro e Último contato são fornecidas. Esse é o relatório de fonte de tráfego externo preferido no Adobe Analytics (em vez de Campanhas ou Fontes de tráfego) por ser o olhar mais abrangente nos canais pagos e orgânicos. | [Canais de marketing](https://docs.adobe.com/content/help/en/analytics/components/marketing-channels/c-getting-started-mchannel.html) |
| Mobile | Exibe informações sobre os sites acessados em um dispositivo móvel ou tablet. | [Relatório móvel | (https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-mobile.html) |
| Aplicativo móvel | Exibe informações de uso básico relacionadas aos seus aplicativos móveis. Esses relatórios são disponibilizados depois que o SDK é implementado e os relatórios ativados.  O Adobe Mobile Services também criou uma interface de aplicativo móvel diferente, que oferece dados mais abrangentes do aplicativo e permite entender e melhorar a participação do usuário nos seus aplicativos.  Acesse a interface [aqui](https://mobilemarketing.adobe.com). | [Serviços Adobe Mobile](https://docs.adobe.com/content/help/en/mobile-services/using/home.html) | Produtos | Identifica como os produtos individuais e grupos de produtos (categorias) contribuem para diversas métricas de conversão, tais como Receita ou Finalizações. | [Relatório de produtos](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-products.html) |
| Comparação de segmentos | Descobre as diferenças estatisticamente mais significativas entre segmentos por meio de uma análise automatizada de cada métrica e dimensão a que você tem acesso. | [Comparação de segmentos](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/segment-comparison/segment-comparison.html) |
| Relatório de conteúdo do site | Exibe informações sobre quais páginas e áreas do site são mais ativas e quais servidores estão sendo mais usados. | [Relatório de conteúdo do site](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-site-content.html) |
| Relatório de métricas do site | Exibe informações quantitativas sobre seu site, como visitantes únicos, pedidos, receita etc. As métricas podem ser colocadas em outros relatórios baseados em itens. | [Relatório de métricas do site](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-site-metrics.html) |
| Perfil do visitante | Relatórios que ajudam você a visualizar padrões de compras dos clientes de várias categorias de perfil, incluindo países, estados, CEP/códigos postais e domínios. | [Perfil do visitante](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-visitor-profile.html) |
| Retenção de visitante | Exibe informações sobre a fidelidade do cliente, como quantos visitantes retornaram ao site e com que frequência. | [Retenção de visitante](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-visitor-retention.html) |
| Link do projeto, compartilhamento e agendamento | Métodos para salvar e/ou compartilhar seu trabalho com outras pessoas na interface do Analytics. | [Enviar e agendar arquivos](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/send-schedule-files.html) |

## Key metrics {#concept_392819DC275C48688E2CE4ABD4C5EE43}

| Nome da métrica | Definição | Link da documentação |
|---|---|---|
| Lista completa de métricas | Definição de todas as métricas no Adobe Analytics. | [Visão geral das métricas](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-overview.html) |
| Visitantes únicos | O número de visitantes não duplicados do site durante um intervalo de tempo especificado. | [Visitantes únicos](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-unique-visitors-v15-dsc.html) |
| Visitas | Uma sequência de exibições da página em uma sessão. A visita começa quando uma pessoa visualiza uma página do site pela primeira vez e a fecha depois de 30 minutos de inatividade. | [Visitas](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-visit.html) |
| Exibições de página | Uma exibição de página ocorre quando um visitante acessa uma página do site da Web.  | [Exibições de página](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-page-view.html) |
| Instâncias | O número de vezes que uma variável foi definida. Toda vez que o Adobe Analytics vê um valor em uma variável, as instâncias são aumentadas em um no respectivo relatório. | [Instâncias](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-instance.html) |
| Ocorrências | O número de vezes que uma variável foi definida ou persistiu. | [Ocorrências](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-occurrences.html) |

## Opções de importação {#concept_7C6DF03B5F9149E2A77F36C739432059}

| Opção | Descrição | Link da documentação |
|---|---|---|
| Classificação do importador | Importe metadados de dimensões capturadas pelo navegador ou por meio do upload de FTP. Método manual comparado ao Construtor de regras. | [Classificação do importador](https://marketing.adobe.com/resources/help/en_US/reference/c_working_with_saint.html) |
| Construtor de regras | Cria classificações de metadados de dimensões automaticamente, com base nas regras definidas pelo usuário. | [Criador de regras de classificação](https://marketing.adobe.com/resources/help/en_US/reference/classification_rule_builder.html) |
| Atributos do cliente | Dados do CRM carregados na Experience Cloud para uso no Adobe Analytics e no Adobe Target. | [Atributos do cliente](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/attributes.html) |
| Fontes de dados | Importe métricas offline para o Analytics em relação a dimensões ou simplesmente ao dia. | [Fontes de dados](https://docs.adobe.com/content/help/en/analytics/import/data-sources/datasrc-home.html) |
| Conectores de dados do Adobe Exchange | Consulte Ferramentas [do Analytics](/help/landing/an-key-concepts.md) |  |
| Integrações nativas | Análise de público-alvo e Análise de publicidade. | Consulte a seção "Relatórios principais". |

## Export options {#concept_C62B688E259141CF92C048E8110464BE}

| Opção | Descrição | Link da documentação |
|---|---|---|
| Downloads da interface e agendamento | Exportar dados da Analysis Workspace como CSV ou PDF | [Baixar arquivos PDF ou CSV](/help/analyze/analysis-workspace/curate-share/download-send.md) |
| Report Builder | Consulte Ferramentas do Analytics. |
| API do Analytics | Crie suas próprias consultas personalizadas de dados do Analytics. | <ul><li>[API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html)</li><li>[API 1.4](https://github.com/AdobeDocs/analytics-1.4-apis)</li></ul> |
| Data Warehouse | Consulte Ferramentas do Analytics. |  |
| Feed de dados do Analytics | A maneira mais granular de obter dados do Analytics. Configura um feed do nível de ocorrência do Analytics. | [Feed de dados do Analytics](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/get-started/data-feed-overview.html) |

## Data collection and validation {#concept_E07350D4CA5047DAA7D81F762F29606A}

| Método/Recurso | Descrição | Link da documentação |
|--- |--- |--- |
| Recursos do desenvolvedor | Documentação que descreve as bibliotecas disponíveis para coletar dados do Analytics em todas as plataformas disponíveis (Web, aplicativos móveis, vídeo, Flash etc.) | [Documentos do desenvolvedor](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| Guia de implementação | Uma descrição das variáveis de coleta de dados e detalhes sobre a implementação do código da coleta de dados em JavaScript. | [Guia de Implementação](https://docs.adobe.com/content/help/en/analytics/implementation/home.html) |
| AppMeasurement (s_code) | Gerenciamento global de variáveis | [AppMeasurement](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html) |
| SDKs do aplicativo | Pacote personalizado que inclui uma versão pré-preenchida do arquivo de configuração para aplicativos. | <ul><li>[iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/overview.html)</li><li>[Android](https://docs.adobe.com/content/help/en/mobile-services/android/getting-started-android/requirements.html)</li></ul> |
| DTM e Adobe Launch | Consulte Ferramentas do Analytics. |  |
| VISTA | Permite aplicar lógica do lado do servidor para alterar ou segmentar dados conforme são coletados. | [Regras VISTA](https://marketing.adobe.com/resources/help/en_US/reference/VISTA.html) |
| Regras de processamento | Capacidade de definir, modificar e copiar variáveis na interface do usuário do Analytics para alterar os dados coletados. | [Regras de processamento](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules.html) |
| Opções de depuração | Há vários depuradores e sniffers de pacotes disponíveis para ajudar a validar sua implementação, incluindo o depurador da Adobe Experience Cloud. | [Adobe Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj?hl=en) |
| API de inserção de dados | A API de inserção de dados fornece um mecanismo para a coleta de dados do lado do servidor e o envio para os servidores da Experience Cloud. Em vez de usar beacons JavaScript em cada página da Web para transmitir dados do visitante para os servidores da Experience Cloud, a coleta de dados do lado do servidor coleta dados com base exclusivamente nas solicitações do navegador da Web e nas respostas do servidor da Web. | [Etapas para implementar a API de inserção de dados do Adobe Analytics usando o POST](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html) |
