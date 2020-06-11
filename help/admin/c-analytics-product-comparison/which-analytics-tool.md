---
description: Esta página de ajuda contém casos de uso recomendados para cada ferramenta do Adobe Analytics. As ferramentas devem ser consideradas na ordem em que estão listadas. Se uma ferramenta específica não atender à necessidade, considere a próxima.
title: Qual ferramenta do Adobe Analytics devo usar?
uuid: 1179e49d-3cfc-4abd-a8eb-35c5ae380c16
translation-type: tm+mt
source-git-commit: c53580905e6bb22b9cdb2917734a189e1f83d72f
workflow-type: tm+mt
source-wordcount: '1102'
ht-degree: 99%

---


# Qual ferramenta do Adobe Analytics devo usar?

Esta página de ajuda contém casos de uso recomendados para cada ferramenta do Adobe Analytics. As ferramentas devem ser consideradas na ordem em que estão listadas. Se uma ferramenta específica não atender à necessidade, considere a próxima.

Para mais comparações entre produtos do Adobe Analytics, clique [aqui](/help/admin/c-analytics-product-comparison/analytics-product-comparison.md).

## Interfaces do usuário de relatórios do Adobe Analytics {#section_8265460EBB47405AB19A3B2B0729C8A4}

A **[Analysis Workspace](/help/analyze/analysis-workspace/home.md)**deve ser a interface principal do usuário para todas as suas necessidades de relatórios e análises. A Adobe continua a investir e lançar atualizações mensais para este produto. Caso haja uma tarefa que não possa ser executada na Analysis Workspace, considere as outras interfaces abaixo.**

**[Reports &amp; Analytics](/help/analyze/reports-analytics/overview/report-overview.md)**deve ser usado:

* Por usuários iniciantes que requerem acesso a relatórios pré-criados e fáceis de navegar.
* Para acessar dados em tempo real na interface.
* Para configurar eventos do Calendário.
* Para configurar Metas.
* Para visualizar relatórios de Bot.
* Para acessar visualizações exclusivas de Vídeo referentes a Visualizadores simultâneos, Período de transmissão de vídeo, e Abandono do visualizador.
* Para aproveitar Listas de publicação em relatórios agendados.

**[Ad Hoc Analysis](/help/analyze/ad-hoc-analysis/adhoc-home.md)**deve ser usada:

* Para exportar 50.000 linhas de dados
* Se a organização da guia de trabalho do projeto for necessária.
* Para usar o relatório de Análise do site (relatório de definição de caminho 3D).

**[Data Workbench](https://docs.adobe.com/content/help/en/data-workbench/using/home.html)**deve ser usada:

* Como a opção de ferramenta mais flexível do Analytics (análise de perda a nível de visitantes, a nível de ocorrência).
* Para criar um conjunto de dados multicanal e interações online e offline de CRM para POS, até a Web.
* Para atribuição avançada (com base nas regras e modelos algorítmicos).
* Para modelagem preditiva e estatística (pontuação de propensão, agrupamento, correlações, etc.).
* Para análise de Latência (tempo antes / depois de um evento).
* Para identificação e exportação de segmentos complexos em toda a Adobe Experience Cloud.

## Importação de dados para o Adobe Analytics {#section_B42B998D6E3E4357B024AEFA4EC69A23}

**[Classificações](/help/components/c-classifications2/c-classifications.md)**devem ser usadas:

* Quando há metadados que você deseja associar a um valor de coleta (eVar, prop, canal de marketing)
* Opções:

   * Construtor de regras: usar quando tiver valores formatados previsíveis sendo coletados para uma variável, por exemplo, valores delimitados. Esta abordagem permite configurar regras uma vez e “defini-las e esquecê-las” de forma global.
   * Importador de navegador: use quando não houver valores previsíveis ou quando tiver uma lista finita de valores que exigem uma atualização única. Esta abordagem requer um monitoramento contínuo das classificações para novos valores.

**[Fontes de dados](/help/import/c-data-sources/datasrc-home.md)**devem ser usadas:

* Quando há dados offline que você deseja gravar permanentemente no Adobe Analytics
* Opções:

   * Resumo: uploads de dados simples, por dia ou dimensões limitadas
   * ID da transação: uploads de dados que conectam um terminal online a dados offline e associam totalmente os dados importados a um instantâneo de visitante capturado online (por exemplo, os pedidos são concluídos online e devolvidos offline)
   * Processamento completo: fontes de dados com data e hora, processadas como se fossem uma ocorrência coletada pelos servidores da Adobe. Isto é, os dados são inseridos diretamente na jornada do visitante.

**[Data Connectors](https://www.adobeexchange.com/experiencecloud.html)(conhecidos formalmente como Genesis)**devem ser usados:

* Ao ter contato com um provedor terceirizado que criou uma conexão que oferece suporte ao Adobe Analytics. Em geral, os Data Connectors incorporam dados a nível de resumo no Adobe Analytics de modo permanente e automático, em uma base recorrente.

**[API da inserção de dados](/help/import/c-data-insertion-api/c-data-insertion-api.md)**deve ser usada:

* Quando você precisa fazer o upload de dados no Adobe Analytics e não pode usar o código do Adobe App Measurement ou do SDK para dispositivos móveis.

**[Atributos do cliente](https://docs.adobe.com/content/help/pt-BR/core-services/interface/customer-attributes/attributes.html)**devem ser usados:

* Se você capturar dados de clientes empresariais em um banco de dados de gerenciamento de relacionamento com o cliente (CRM) e desejar fazer o upload dos dados para a Experience Cloud.
* Se você deseja usar os dados de CRM para executar análises mais aprofundadas no Analytics ou como critérios de segmentação no Adobe Target.

**[Análise de público-alvo](/help/integrate/c-audience-analytics/mc-audiences-aam.md)**deve ser usada:

* Se você deseja incorporar os dados de público-alvo do Adobe Audience Manager (AAM), como informações demográficas (por exemplo, sexo ou faixa salarial), informações psicográficas (por exemplo, interesses e hobbies), dados de CRM ou dados de impressões do anúncio, em qualquer fluxo de trabalho do Analytics.
* Se você deseja que os dados de CRM carregados sejam com base no tempo, pois essa integração envia novas informações ao Analytics a cada ocorrência.

## Exportação de dados do Adobe Analytics {#section_901C06ABF2014E92B2952906723DF235}

**[Report Builder](/help/analyze/report-builder/home.md)**deve ser usado:

* Se as opções de layout personalizadas do Workspace estiverem com limitações (tudo é possível no Report Builder, dentro dos limites do Excel).
* Para vincular livremente as entradas do usuário ou as fontes de dados offline (impressões, custo) aos dados da Adobe. As Fontes de dados são uma solução mais permanente para vincular os dados (consulte Importação de dados para o Analytics).
* Para mesclar os dados em conjunto de diferentes relatórios dimensionais (por exemplo, relatório de impressões promocionais associado ao relatório de clique para conversão promocional).
* Para exibições de conjunto de relatórios cruzados.
* Se a automação por meio de agendamento for necessária (XLSX, XLSM, CSV, PDF, TXT, XML, MHT).

**[O Data Warehouse](/help/export/data-warehouse/data-warehouse.md)**deve ser usado:

* Para acessar as variáveis ocultas na interface do usuário - endereço IP, Experience Cloud ID, ID de visitante do Analytics, URL da página)
* Para acessar dados mais granulares do que a interface do usuário (exibição de tabela desnormalizada)
* Para baixar dados em um formato adequado para uma entrada de Tabela dinâmica
* Se o cliente quiser inserir dados da Adobe em uma ferramenta de dados de visualização de terceiros (ligeiramente resumida e não a nível de ocorrência)
* Para acessar todos os valores de dimensões únicas se estiver executando de forma &quot;Baixo tráfego&quot; no Adobe Analytics

O **[Feed de dados do Analytics](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md)**deve ser usado:

* Para utilizar o feed de dados mais granular que podemos fornecer (ID do visitante, ocorrência).
* Se o cliente quiser os dados da Adobe armazenados em um banco de dados do lado do cliente, no nível mais granular, eles poderão ser enviados.
* Se o cliente quiser desenvolver uma ferramenta de Inteligência empresarial (BI, Business Intelligence) ou inserir dados da Adobe a nível de ocorrência em uma ferramenta de terceiros.

As **[APIs de relatórios](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-guide.md)**devem ser usadas quando outras opções de visualização não atenderem às suas necessidades. As 3 opções de API incluem:

* **Totalmente processada**: quando quiser dados ricos em recursos (inclusive visitas, visitantes e segmentos). Isso são dados resumidos, típicos da interface do usuário do Analytics, disponíveis dentro de 30 a 90 minutos. Podem ser usados por meio do Report Builder.
* **Em tempo real**: quando quiser visualizar algumas métricas e dimensões com segundos de latência. Isso são dados limitados, parcialmente processados e resumidos, disponíveis dentro de 30 segundos. Inclui algoritmos exclusivos dos mais populares, ganhadores e perdedores. Podem ser usados por meio do Report Builder.
* **[!UICONTROL Livestream]**: quando quiser um fluxo de dados a nível de ocorrência, parcialmente processado do Analytics em segundos de coleção. Isso são dados parcialmente processados, disponíveis dentro de 30 segundos. Disponível apenas no Analytics Premium. Requer alguma forma de visualizar os dados, geralmente por meio de uma participação nos serviços de engenharia.

## Soluções personalizadas {#section_4A212F26A15947599DFB0399A0440CB6}

Os Serviços de engenharia devem ser usados quando:

* As outras ferramentas da Adobe não atenderem as suas necessidades.
* Você quiser uma experiência personalizada.
* Você quiser uma solução totalmente automatizada.
* Você quiser alcançar vários dispositivos.
* Você tiver múltiplas fontes de dados.
* Você possuir requisitos de dados ETL (Extract-Transform-Load) complexos.
* Você quiser uma marca personalizada.
* Você desejar visualizar o [!UICONTROL Analytics Live Stream].
