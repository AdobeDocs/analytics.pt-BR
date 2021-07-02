---
description: Esta seção contém os principais conceitos do Adobe Analytics, uma breve descrição do conceito e um link de documentação específica com detalhes adicionais sobre o tópico.
title: Adobe Analytics - Principais conceitos
exl-id: 359c6663-33fd-4491-8ea0-55cd9ae31859
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: ht
source-wordcount: '1822'
ht-degree: 100%

---

# Adobe Analytics - Principais conceitos

Esta seção contém os principais conceitos do Adobe Analytics, uma breve descrição do conceito e um link de documentação específica com detalhes adicionais sobre o tópico.

## Ferramentas do Analytics {#concept_833EDD4EB056491DA1BC5A3A45FE285B}

| Produto | Descrição | Link da documentação |
| --- | --- | --- |
| Analysis Workspace | Solução de navegador para desenvolver projetos de análise avançados e personalizados, bem como para democratizar informações. Oferece mais flexibilidade de relatórios que o Reports and Analytics. | [Página inicial do Analysis Workspace](/help/analyze/analysis-workspace/home.md) |
| Reports and Analytics (antigo SiteCatalyst) | Solução de navegador para relatórios e análises. Ferramenta inicial no pacote do Analytics. | [Página inicial do Reports and Analytics](/help/analyze/reports-analytics/getting-started.md) |
| Report Builder | Complemento do Excel que permite a criação de solicitações personalizadas de dados do Adobe Analytics e a visualização usando o Microsoft Excel. | [Página inicial do Report Builder](/help/analyze/report-builder/home.md) |
| Data Workbench (antigo Insight) | Desenvolvido para coletar, processar, analisar e visualizar dados de interações online e offline do cliente em vários canais. | [Cliente do Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/client/t-open-ins.html?lang=pt-BR) |
| Data Warehouse | Dados brutos e não processados para armazenamento e relatórios personalizados, que podem ser executados por meio da filtragem de dados. Sem nível de ocorrências. | [Página inicial do Data Warehouse](/help/export/data-warehouse/data-warehouse.md) |
| Adobe Mobile Services | Reúne recursos de marketing móvel para aplicativos móveis de toda a Adobe Experience Cloud, permitindo que você entenda e aprimore a participação do usuário com seus aplicativos. | [Página inicial do Mobile Services](https://experienceleague.adobe.com/docs/mobile-services/using/home.html?lang=pt-BR) |
| Data Connectors do Adobe Exchange (antigo Genesis) | Importe dados de rastreamento de aplicativos de terceiros para o Analytics, oferecendo visibilidade completa ao desempenho em um local central. A partir de 1º de agosto de 2021, a Adobe pretende descontinuar as integrações dos Data Connectors. | [Página inicial dos Data Connectors](/help/import/data-connectors/data-connectors-eol.md) |
| Adobe Experience Platform Launch | A próxima geração de recursos de Gerenciamento de tags de site e de SDKs móveis da Adobe. | [Página inicial do Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/home.html?lang=pt-BR) |

## Terminologia principal {#concept_E473ACBB8E4A42B4AC005538AC12F154}

Clique [aqui](/help/technotes/terms.md) para obter um glossário expandido com os termos do Adobe Analytics.

| Termo | Descrição | Link da documentação |
| --- | --- | --- |
| Props (tráfego personalizado) | Dimensões usadas para rastrear a atividade de tráfego do site página por página. As props não persistem entre páginas. Principais aplicações das variáveis de tráfego: <ul> <li>Contagem simples para encontrar o &#39;mais popular&#39; de um valor específico</li> <li>Visibilidade sobre a trajetória dos usuários em seu site</li> </ul> <br> Exemplos de variáveis de tráfego: Nome da página, Seções do site, Navegadores. | [Props](/help/admin/admin/c-traffic-variables/traffic-var.md) |
| eVar (conversão personalizada) | Dimensões que persistem por um período personalizado por você. As opções de expiração incluem expiração de evento, expiração de visita ou expiração do dia X, e devem ser orientadas pelo tipo de análise que será realizada nessa variável. <br> Principais diferenças entre eVars e props: <ul> <li>As props geralmente são usadas para a análise de definição de caminho porque a persistência é removida.</li> <li>Geralmente, as eVars são usadas para análise de conversão.</li> </ul> <br> Exemplos de variáveis de conversão: Termos de pesquisa interna, Promoções internas, Campanhas externas (s.campaign). | [eVars](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) |
| Eventos/métricas (s.events) | As métricas que avaliam as principais ações que gostaríamos que os visitantes realizassem no site. Há três tipos de eventos: Contador, Numérico e Moeda. Os eventos são mais úteis quando adicionados aos relatórios da variável de conversão (eVar). A eVar oferece as informações qualitativas sobre o que aconteceu, e o Evento oferece informações quantitativas sobre o que aconteceu. <br> Principais diferenças entre eVars e eventos: <ul> <li>As eVars informam quem ou o que afetou a conversão</li> <li>Os eventos avaliam quantas conversões ocorreram</li> </ul> <br> Exemplos de eventos de conversão: Pedidos, Inícios de aplicação, Clientes potenciais, Receita. | [Eventos](/help/admin/admin/c-success-events/success-event.md) |
| Componentes | Dimensões, métricas, segmentos e granularidades de tempo (intervalos de datas) que você pode arrastar e soltar em um projeto. | [Componentes](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) |
| Dimensões | Coleta de eVars, props, classificações e valores coletados padrão da Adobe. | [Dimensões](/help/components/dimensions/overview.md) |
| Métricas | Coleta de eventos implementados e métricas calculadas. | [Métricas](/help/analyze/analysis-workspace/components/apply-create-metrics.md) |
| Métricas calculadas | Capacidade de derivar métricas personalizadas a partir de métricas existentes capturadas pela sua implementação. | [Métricas calculadas](/help/components/c-calcmetrics/cm-overview.md) |
| Segmentos | Capacidade de criar, gerenciar, compartilhar e aplicar segmentos de público-alvo focados nos relatórios do Analytics. Os segmentos são compartilhados nos produtos do Analytics e podem ser compartilhados na Experience Cloud. | [Segmentação](/help/components/segmentation/seg-home.md) |
| Hora (intervalos de datas) | Capacidade de filtrar a data para qualquer período de tempo e criar intervalos de datas personalizados que podem ser reutilizados em sua análise. | [Intervalos de datas](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md) |
| Visualizações | Visualizações avançadas que podem ajudar a dar vida aos dados em seus projetos. | [Visualizações](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) |
| Preparação | Capacidade de limitar os componentes acessíveis em um projeto ou Conjunto de relatórios virtuais. | [Curadoria de VRS](/help/components/vrs/vrs-components.md) <br> [Curadoria de projeto](/help/analyze/analysis-workspace/curate-share/curate.md) |

## Relatórios principais

| Relatório | Descrição | Link da documentação |
| --- | --- | --- |
| Lista completa de dimensões/relatórios | Definição de todas as dimensões e relatórios disponíveis no Adobe Analytics. | [Dimensões](/help/components/dimensions/overview.md) |
| Advertising Analytics | Analise todos os dados de pesquisa paga do Google e do Bing lado a lado no Adobe Analytics. As dimensões criadas por meio da integração incluem Plataforma de publicidade, Palavra-chave, Tipo de correspondência etc. As métricas criadas são: Impressões AMO, Cliques AMO, Custo AMO, Média. Posição e Média. Pontuação de qualidade do AMO. | [Advertising Analytics](/help/integrate/c-advertising-analytics/overview.md) |
| Audience Analytics | Enriqueça as ocorrências de entrada do Analytics com a associação de público-alvo de um usuário no AAM. você pode incorporar os dados de público-alvo do AAM, como informações demográficas (por exemplo, sexo ou faixa salarial), informações psicográficas (interesses e hobbies), dados de CRM ou dados de impressões do anúncio, em qualquer fluxo de trabalho do Analytics. As dimensões criadas por meio dessa integração são ID de público-alvo e Nome de público-alvo. | [Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md) |
| Attribution IQ | Permite compreender como a participação significativa é aplicada ao longo da jornada do cliente, identificando de maneira inteligente pontos de inflexão que causam clientes a direcionar resultados, e consequentemente otimizando iniciativas de marketing. Os modelos incluem primeiro, último, linear, participação, em forma de j, em forma de j inversa, em forma de u, mesmo toque, personalizado e declínio de tempo. | [Attribution IQ](/help/analyze/analysis-workspace/c-panels/attribution.md) |
| Detecção de anomalias | Um método estatístico para definir como uma determinada métrica foi alterada em relação aos dados anteriores. A AD é ativada por padrão para todas as visualizações de tendências na Analysis Workspace. | [Detecção de anomalias](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) |
| Análise de contribuição | Explora o &quot;porquê&quot; por trás das anomalias que ocorrem, executando uma análise automatizada de cada métrica e dimensão a que você tem acesso. | [Análise de contribuição](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md) |
| Análise de coorte | O coorte é um grupo de pessoas com características comuns em um período específico. A análise de coorte ajuda a analisar a retenção e a rotatividade de seus usuários. | [Análise de coorte](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) |
| Relatórios de jornada do cliente | Exibe informações sobre o caminho que seus usuários tomam em seu site ou aplicativo. Prop, eVars e eventos podem ser usados nessa análise na Analysis Workspace. | [Fallout do Analysis Workspace](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md) <br> [Fluxo do Analysis Workspace](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) <br> [Definição de caminho do Reports and Analytics](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) |
| Canais de marketing | Relatórios que ajudam você a entender quais canais externos levam os usuários ao seu site e o que é mais eficaz para impulsionar a conversão. As exibições da atribuição de Primeiro e Último contato são fornecidas. Esse é o relatório de fonte de tráfego externo preferido no Adobe Analytics (em vez de Campanhas ou Fontes de tráfego) por ser o olhar mais abrangente nos canais pagos e orgânicos. | [Canais de marketing](/help/components/c-marketing-channels/c-getting-started-mchannel.md) |
| Dispositivo móvel | Exibe informações sobre os sites acessados em um dispositivo móvel ou tablet. | [Relatório móvel](/help/components/dimensions/mobile-dimensions.md) |
| Aplicativo móvel | Exibe informações de uso básico relacionadas aos seus aplicativos móveis. Esses relatórios são disponibilizados depois que o SDK é implementado e os relatórios ativados.  O Adobe Mobile Services também criou uma interface de aplicativo móvel diferente, que oferece dados mais abrangentes do aplicativo e permite entender e melhorar a participação do usuário nos seus aplicativos.  Acesse a interface [aqui](https://mobilemarketing.adobe.com). | [Adobe Mobile Services](https://experienceleague.adobe.com/docs/mobile-services/using/home.html?lang=pt-BR) |
| Produtos | Identifica como os produtos individuais e grupos de produtos (categorias) contribuem para diversas métricas de conversão, tais como Receita ou Finalizações. | [Relatório de Produtos](/help/components/dimensions/product.md) |
| Comparação de segmentos | Mostra as diferenças estatisticamente mais importantes entre dois segmentos por meio de uma análise automatizada de todas as métricas e dimensões as quais você tem acesso. | [Comparação de segmentos](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md) |
| Relatório de conteúdo do site | Exibe informações sobre quais páginas e áreas do site são mais ativas e quais servidores estão sendo mais usados. | [Relatório de conteúdo do site](/help/components/dimensions/page.md) |
| Relatório de métricas do site | Exibe informações quantitativas sobre seu site, como visitantes únicos, pedidos, receita etc. As métricas podem ser colocadas em outros relatórios baseados em itens. | [Relatório de métricas do site](/help/components/metrics/overview.md) |
| Perfil do visitante | Relatórios que ajudam você a visualizar padrões de compras dos clientes de várias categorias de perfil, incluindo países, estados, CEP/códigos postais e domínios. | [Perfil do visitante](/help/components/dimensions/language.md) |
| Retenção de visitante | Exibe informações sobre a fidelidade do cliente, como quantos visitantes retornaram ao site e com que frequência. | [Retenção de visitante](/help/components/dimensions/customer-loyalty.md) |
| Link do projeto, compartilhamento e agendamento | Métodos para salvar e/ou compartilhar seu trabalho com outras pessoas na interface do Analytics. | [Envie e programe arquivos](/help/analyze/analysis-workspace/curate-share/send-schedule-files.md) |

## Métricas principais {#concept_392819DC275C48688E2CE4ABD4C5EE43}

| Nome da métrica | Definição | Link da documentação |
| --- | --- | --- |
| Lista completa de métricas | Definição de todas as métricas no Adobe Analytics. | [Visão geral das métricas](/help/components/metrics/overview.md) |
| Visitantes únicos | O número de visitantes não duplicados do site durante um intervalo de tempo especificado. | [Visitantes únicos](/help/components/metrics/unique-visitors.md) |
| Visitas | Uma sequência de exibições da página em uma sessão. A visita começa quando uma pessoa visualiza uma página do site pela primeira vez e a fecha depois de 30 minutos de inatividade. | [Visitas](/help/components/metrics/visits.md) |
| Exibições de página | Uma exibição de página ocorre quando um visitante acessa uma página do site da Web. | [Exibições de página](/help/components/metrics/page-views.md) |
| Instâncias | O número de vezes que uma variável foi definida. Toda vez que o Adobe Analytics vê um valor em uma variável, as instâncias são aumentadas em um no respectivo relatório. | [Instâncias](/help/components/metrics/instances.md) |
| Ocorrências | O número de vezes que uma variável foi definida ou mantida. | [Ocorrências](/help/components/metrics/occurrences.md) |

## Opções de importação {#concept_7C6DF03B5F9149E2A77F36C739432059}

| Opção | Descrição | Link da documentação |
| --- | --- | --- |
| Classificação do importador | Importe metadados de dimensões capturadas pelo navegador ou por meio do upload de FTP. Método manual comparado ao Construtor de regras. | [Classificação do importador](/help/components/classifications/importer/c-working-with-saint.md) |
| Construtor de regras | Cria classificações de metadados de dimensões automaticamente, com base nas regras definidas pelo usuário. | [Criador de regras de classificação](/help/components/classifications/crb/classification-rule-builder.md) |
| Atributos do cliente | Dados do CRM carregados na Experience Cloud para uso no Adobe Analytics e no Adobe Target. | [Atributos do cliente](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=pt-BR) |
| Fontes de dados | Importe métricas offline no Analytics em relação a dimensões ou diariamente. | [Fontes de dados](/help/import/c-data-sources/datasrc-home.md) |
| Data Connectors do Adobe Exchange | Consulte [Ferramentas do Analytics.](/help/import/data-connectors/data-connectors-eol.md) |  |
| Integrações nativas | Audience Analytics e Advertising Analytics. | Consulte a seção &quot;Relatórios principais&quot;. |

## Opções de exportação {#concept_C62B688E259141CF92C048E8110464BE}

| Opção | Descrição | Link da documentação |
| --- | --- | --- |
| Downloads da interface do usuário e agendamento | Exportar dados da Analysis Workspace como CSV ou PDF. | [Baixar arquivos PDF ou CSV](/help/analyze/analysis-workspace/curate-share/download-send.md) |
| Report Builder | Consulte Ferramentas do Analytics. |  |
| API do Analytics | Crie suas próprias consultas personalizadas de dados do Analytics. | <ul><li>[API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html)</li><li>[API 1.4](https://github.com/AdobeDocs/analytics-1.4-apis)</li></ul> |
| Data Warehouse | Consulte Ferramentas do Analytics. |  |
| Feed de dados do Analytics | A maneira mais granular de obter dados do Analytics. Configura um feed do nível de ocorrência do Analytics. | [Feed de dados do Analytics](/help/export/analytics-data-feed/data-feed-overview.md) |

## Coleção e validação de dados {#concept_E07350D4CA5047DAA7D81F762F29606A}

| Método/Recurso | Descrição | Link da documentação |
| --- | --- | --- |
| Recursos do desenvolvedor | Documentação que descreve as bibliotecas disponíveis para coletar dados do Analytics em todas as plataformas disponíveis (Web, aplicativos móveis, vídeo, Flash etc.) | [Documentos o desenvolvedor](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| Guia de Implementação | Uma descrição das variáveis de coleta de dados e detalhes sobre a implementação do código da coleta de dados em JavaScript. | [Guia de Implementação](/help/implement/home.md) |
| AppMeasurement (s_code) | Gerenciamento global de variáveis. | [AppMeasurement](/help/implement/js/migrate-from-hcode.md) |
| SDKs do aplicativo | Pacote personalizado que inclui uma versão pré-preenchida do arquivo de configuração para aplicativos. | <ul><li>[iOS](https://experienceleague.adobe.com/docs/mobile-services/ios/overview.html?lang=pt-BR)</li><li>[Android](https://experienceleague.adobe.com/docs/mobile-services/android/getting-started-android/requirements.html?lang=pt-BR)</li></ul> |
| Adobe Experience Platform Launch | Consulte Ferramentas do Analytics. |  |
| VISTA | Permite aplicar a lógica do lado do servidor para alterar ou segmentar dados conforme são coletados. | [Regras VISTA](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/processing-rule-order.md) |
| Regras de processamento | Capacidade de definir, modificar e copiar variáveis na interface do usuário do Analytics para alterar os dados coletados. | [Regras de processamento](/help/admin/admin/c-processing-rules/processing-rules.md) |
| Opções de depuração | Há vários depuradores e analisadores de pacotes disponíveis para ajudar a validar sua implementação, incluindo o Adobe Experience Cloud Debugger. | [Adobe Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj?hl=pt) |
| API de inserção de dados | A API de inserção de dados fornece um mecanismo para a coleta de dados do lado do servidor e o envio para os servidores da Experience Cloud. Em vez de usar beacons do JavaScript em cada página da Web para transmitir dados do visitante para os servidores da Experience Cloud, a coleta de dados do lado do servidor coleta dados com base exclusivamente nas solicitações do navegador da Web e nas respostas do servidor da Web. | [Etapas para implementar a API de inserção de dados do Adobe Analytics usando o POST](https://helpx.adobe.com/br/analytics/kb/data-insertion-api-post-method-adobe-analytics.html) |
