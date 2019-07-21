---
description: Esta página de ajuda contém casos de uso recomendados para cada ferramenta do Adobe Analytics. As ferramentas devem ser consideradas na ordem em que estão listadas. Se uma ferramenta específica não atender à necessidade, considere a próxima.
seo-description: Esta página de ajuda contém casos de uso recomendados para cada ferramenta do Adobe Analytics. As ferramentas devem ser consideradas na ordem em que estão listadas. Se uma ferramenta específica não atender à necessidade, considere a próxima.
seo-title: Qual ferramenta do Adobe Analytics devo usar?
title: Qual ferramenta do Adobe Analytics devo usar?
uuid: 1179 e 49 d -3 cfc -4 abd-a 8 eb -35 c 5 ae 380 c 16
translation-type: tm+mt
source-git-commit: bf9152741507c75e1f92e8d5d515127eadf5d590

---


# Qual ferramenta do Adobe Analytics devo usar?

Esta página de ajuda contém casos de uso recomendados para cada ferramenta do Adobe Analytics. As ferramentas devem ser consideradas na ordem em que estão listadas. Se uma ferramenta específica não atender à necessidade, considere a próxima.

Para mais comparações entre produtos do Adobe Analytics, clique [aqui](../../admin/c-analytics-product-comparison/analytics-product-comparison.md#concept_D9DB9FA42CA04F4C97765B6B31A0005D).

## Interfaces do usuário de relatórios do Adobe Analytics {#section_8265460EBB47405AB19A3B2B0729C8A4}

A **[Analysis Workspace](/help/analyze/analysis-workspace/analysis-workspace-features.md)** deve ser a interface principal do usuário para todas as suas necessidades de relatórios e análises. A Adobe continua a investir e lançar atualizações mensais para este produto. Caso haja uma tarefa que não possa ser executada na Analysis Workspace, considere as outras interfaces abaixo.**

**[Reports &amp; Analytics](/help/analyze/reports-analytics/overview/report-overview.md)** deve ser usado:

* Por usuários iniciantes que requerem acesso a relatórios pré-criados e fáceis de navegar.
* Para contagem precisa de Impressões e conversões de atividade do A4T.
* Para entender a atividade de Lift e Confidence (Analytics para Target/A4T) do Target.
* Para acessar dados em tempo real na interface.
* Para configurar eventos do Calendário.
* Para configurar Metas.
* Para visualizar relatórios de Bot.
* Para visualizar vários conjuntos de relatórios em um único painel na interface.
* Para acessar visualizações exclusivas de Vídeo referentes a Visualizadores simultâneos, Período de transmissão de vídeo, e Abandono do visualizador.
* Para aproveitar Listas de publicação em relatórios agendados.

**[Interface do usuário do Mobile Services](https://docs.adobe.com/content/help/en/mobile-services/using/home.html)** deve ser usada:

* Se uma exibição agrupada dos dados do aplicativo para dispositivos móveis for necessária.
* Para gerenciar a implementação do SDK para aplicativos para dispositivos móveis.
* Para configurar anúncios em dispositivos moveis, como mensagens dentro do aplicativo, mensagens de push e direcionamento por localização.
* Se mais visualizações interativas forem necessárias para os dados do aplicativo (Sunburst).
* Para visualizar pontos de interesse em um mapa.
* Para métricas de valor do ciclo de vida.

**[Ad Hoc Analysis](/help/analyze/ad-hoc-analysis/adhoc-home.md)** deve ser usada:

* Se a funcionalidade do criador de tabela verdadeira for necessária. Por exemplo: a) a Analysis Workspace não é capaz de suportar o que precisa ser criado; b) você quer ser capaz de controlar quando a tabela será recriada; c) você quer que a tabela se lembre dos vários níveis de detalhamento que deseja aplicar às linhas; d) você quer classificar as linhas de métrica manualmente
* Para exportar 50.000 linhas de dados
* Se a organização da guia de trabalho do projeto for necessária.
* Para usar o relatório de Análise do site (relatório de definição de caminho 3D).

**[Data Workbench](https://marketing.adobe.com/resources/help/en_US/insight/)** deve ser usada:

* Como a opção de ferramenta mais flexível do Analytics (análise de perda a nível de visitantes, a nível de ocorrência).
* Para criar um conjunto de dados multicanal e interações online e offline de CRM para POS, até a Web.
* Para atribuição avançada (com base nas regras e modelos algorítmicos).
* Para modelagem preditiva e estatística (pontuação de propensão, agrupamento, correlações, etc.).
* Para análise de Latência (tempo antes / depois de um evento).
* Para identificação e exportação de segmentos complexos em toda a Adobe Experience Cloud.

## Importação de dados para o Adobe Analytics {#section_B42B998D6E3E4357B024AEFA4EC69A23}

**[Classificações](/help/components/c-classifications2/c-classifications.md)** devem ser usadas:

* Quando há metadados que você deseja associar a um valor de coleta (eVar, prop, canal de marketing)
* Opções:

   * Construtor de regras: usar quando tiver valores formatados previsíveis sendo coletados para uma variável, por exemplo, valores delimitados. Esta abordagem permite configurar regras uma vez e “defini-las e esquecê-las” de forma global.
   * Importador de navegador: usar quando não houver valores previsíveis ou quando tiver uma lista finita de valores que exigem uma atualização única. Esta abordagem requer um monitoramento contínuo das classificações para novos valores.

**[Fontes de dados](/help/import/c-data-sources/datasrc-home.md)** devem ser usadas:

* Quando há dados offline que você deseja gravar permanentemente no Adobe Analytics
* Opções:

   * Resumo: uploads de dados simples, por dia ou dimensões limitadas
   * ID da transação: uploads de dados que conectam um terminal online a dados offline e associam totalmente os dados importados a um instantâneo de visitante capturado online (por exemplo, os pedidos são concluídos online e devolvidos offline)
   * Processamento completo: fontes de dados com data e hora, processadas como se fossem uma ocorrência coletada pelos servidores da Adobe. Isto é, os dados são inseridos diretamente na jornada do visitante.

**[Data Connectors](https://www.adobeexchange.com/experiencecloud.html)(conhecidos formalmente como Genesis)** devem ser usados:

* Ao ter contato com um provedor terceirizado que criou uma conexão que oferece suporte ao Adobe Analytics. Em geral, os Data Connectors incorporam dados a nível de resumo no Adobe Analytics de modo permanente e automático, em uma base recorrente.

**[API da inserção de dados](https://marketing.adobe.com/developer/documentation/data-insertion/c-data-insertion-api)** deve ser usada:

* Quando você precisa fazer o upload de dados no Adobe Analytics e não pode usar o código do Adobe AppMeasurement ou do SDK para dispositivos móveis.

**[Atributos do cliente](/help/components/c-variables/dimensionslist/reports-customer-attributes.md)** devem ser usados:

* Se você capturar dados de clientes empresariais em um banco de dados de gerenciamento de relacionamento com o cliente (CRM) e desejar fazer o upload dos dados para a Experience Cloud.
* Se você deseja usar os dados de CRM para executar análises mais aprofundadas no Analytics ou como critérios de segmentação no Adobe Target.

**[Análise de público-alvo](/help/integrate/c-audience-analytics/mc-audiences-aam.md)** deve ser usada:

* Se você deseja incorporar os dados de público-alvo do Adobe Audience Manager (AAM), como informações demográficas (por exemplo, sexo ou faixa salarial), informações psicográficas (por exemplo, interesses e hobbies), dados de CRM ou dados de impressões do anúncio, em qualquer fluxo de trabalho do Analytics.
* Se você deseja que os dados de CRM carregados sejam com base no tempo, pois essa integração envia novas informações ao Analytics a cada ocorrência.

## Exportação de dados do Adobe Analytics {#section_901C06ABF2014E92B2952906723DF235}

**[Report Builder](/help/analyze/report-builder/home.md)** deve ser usado:

* Se as opções de layout personalizadas do Espaço de trabalho estiverem com limitações (tudo é possível no Report Builder, dentro dos limites do Excel).
* Para vincular livremente as entradas do usuário ou as fontes de dados offline (impressões, custo) aos dados da Adobe. As Fontes de dados são uma solução mais permanente para vincular os dados (consulte Importação de dados para o Analytics).
* Para mesclar os dados em conjunto de diferentes relatórios dimensionais (por exemplo, relatório de impressões promocionais associado ao relatório de clique para conversão promocional).
* Para exibições de conjunto de relatórios cruzados.
* Se a automação por meio de agendamento for necessária (XLSX, XLSM, CSV, PDF, TXT, XML, MHT).

**[O Data Warehouse](/help/export/data-warehouse/data-warehouse.md)** deve ser usado:

* Para acessar variáveis ocultas na interface do usuário - endereço IP, Experience Cloud ID, ID do visitante do Analytics, URL da página)
* Para acessar dados mais granulares do que a interface do usuário (exibição de tabela desnormalizada)
* Para baixar dados em um formato adequado para uma entrada de Tabela dinâmica
* Se o cliente quiser inserir dados da Adobe em uma ferramenta de dados de visualização de terceiros (ligeiramente resumida e não a nível de ocorrência)
* Para acessar todos os valores de dimensões únicas se estiver executando de forma “Baixo tráfego” no Adobe Analytics

**[O Feed de dados do Analytics](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md)** deve ser usado:

* Para utilizar o feed de dados mais granular que podemos fornecer (ID do visitante, ocorrência).
* Se o cliente quiser os dados da Adobe armazenados no seu banco de dados no nível mais granular, eles poderão ser enviados.
* Se o cliente quiser desenvolver uma ferramenta de Inteligência empresarial (BI, Business Intelligence) ou inserir dados da Adobe a nível de ocorrência em uma ferramenta de terceiros.

As **[APIs de relatórios](https://marketing.adobe.com/developer/get-started/introduction/c-introduction)** devem ser usadas quando outras opções de visualização não atenderem às suas necessidades. As 3 opções de API incluem:

* **Totalmente processada**: quando quiser dados ricos em recursos (inclusive visitas, visitantes e segmentos). Isso são dados resumidos, típicos da interface do usuário do Analytics, disponíveis dentro de 30 a 90 minutos. Podem ser usados por meio do Report Builder.
* **Em tempo real**: quando quiser visualizar algumas métricas e dimensões com segundos de latência. Isso são dados limitados, parcialmente processados e resumidos, disponíveis dentro de 30 segundos. Inclui algoritmos exclusivos dos mais populares, ganhadores e perdedores. Podem ser usados por meio do Report Builder.
* **[!UICONTROL Livestream]**: quando quiser um fluxo de dados a nível de ocorrência, parcialmente processado do Analytics em segundos de coleção. Isso são dados parcialmente processados, disponíveis dentro de 30 segundos. Disponível apenas no Analytics Premium. Requer alguma forma de visualizar os dados, geralmente por meio de uma participação nos serviços de engenharia.

## Soluções personalizadas {#section_4A212F26A15947599DFB0399A0440CB6}

Os Serviços de engenharia devem ser usados quando:

* As outras ferramentas da Adobe não atenderem às suas necessidades.
* Você quiser uma experiência personalizada.
* Você quiser uma solução totalmente automatizada.
* Você quiser alcançar vários dispositivos.
* Você tiver múltiplas fontes de dados.
* Você possuir requisitos de dados ETL (Extract-Transform-Load) complexos.
* Você quiser uma marca personalizada.
* Você desejar visualizar o [!UICONTROL Analytics Live Stream].
