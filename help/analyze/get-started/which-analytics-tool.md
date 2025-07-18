---
description: Esta página de ajuda contém casos de uso recomendados para cada ferramenta do Adobe Analytics. As ferramentas devem ser consideradas na ordem em que estão listadas. Se uma ferramenta específica não atender à necessidade, considere a próxima.
title: Qual ferramenta do Adobe Analytics devo usar?
feature: Analytics Basics
exl-id: d65575df-19c6-4129-89c8-d36de7bb6b2f
source-git-commit: a40f30bbe8fdbf98862c4c9a05341fb63962cdd1
workflow-type: ht
source-wordcount: '1122'
ht-degree: 100%

---

# Qual ferramenta do Adobe Analytics devo usar?

Esta página de ajuda contém casos de uso recomendados para cada ferramenta do Adobe Analytics. As ferramentas devem ser consideradas na ordem em que estão listadas. Se uma ferramenta específica não atender à necessidade, considere a próxima.

Para obter mais informações sobre comparações de produtos do Adobe Analytics, consulte [Comparação entre produtos do Analytics](/help/analyze/get-started/analytics-product-comparison.md).


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Comparação das ferramentas](https://video.tv.adobe.com/v/30585?quality=12&learn=on&captions=por_br){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]


## Interfaces de relatórios do Adobe Analytics {#user-interfaces}

A **[Analysis Workspace](/help/analyze/analysis-workspace/home.md)** deve ser a interface principal do usuário para todas as suas necessidades de relatórios e análises. A Adobe continua a investir e lançar atualizações mensais para este produto. Caso haja uma tarefa que não possa ser executada na Analysis Workspace, considere as outras interfaces abaixo.**

Os **[painéis do Adobe Analytics](/help/analyze/mobile-app/home.md)** permitem acessar em dispositivos móveis os cartões de pontuação intuitivos. Os scorecards são uma coleção das métricas principais e de outros componentes apresentados em um layout lado a lado, que você pode usar para obter detalhamentos mais minuciosos e relatórios de tendências. O aplicativo móvel é compatível com os sistemas operacionais iOS e Android.

O **[Report Builder](/help/analyze/report-builder/rb-overview.md)** é um complemento para Microsoft Excel executado no Mac, Windows e navegadores da web. Ele permite criar solicitações personalizadas com base em dados do Adobe Analytics, que você pode inserir em planilhas do Excel. As solicitações podem fazer referência, de forma dinâmica, a células da planilha, e você pode atualizar e personalizar o modo como o Report Builder apresenta os dados.

O **[Report Builder legado](/help/analyze/legacy-report-builder/home.md)** é um complemento para Microsoft Excel executado apenas no Windows. Ele permite criar solicitações personalizadas com base em dados do Adobe Analytics, que você pode inserir em planilhas do Excel. As solicitações podem fazer referência, de forma dinâmica, a células da planilha, e você pode atualizar e personalizar o modo como o Report Builder apresenta os dados.

O **[Activity Map](/help/analyze/activity-map/overview.md)** é um recurso do Adobe Analytics que fornece uma representação visual do engajamento do usuário em páginas da web e aplicativos móveis. Ele permite que profissionais de marketing e analistas rastreiem e analisem interações de usuários, como cliques, movimentos de cursor e comportamento de rolagem.

## Importação de dados para o Adobe Analytics {#import}

As **[classificações](/help/components/classifications/classifications-overview.md)** devem ser usadas:

* Quando houver metadados que você deseja associar a um valor de coleta (eVar, prop, canal de marketing). A Adobe recomenda usar os [conjuntos de classificação](/help/components/classifications/sets/overview.md). O construtor de regras de classificação e o importador de classificação são métodos legados para trazer os dados de classificação para o Adobe Analytics.

**[Fontes de dados](/help/import/data-sources/overview.md)** devem ser usadas:

* Quando há dados offline que você deseja gravar permanentemente no Adobe Analytics.
* Opções:
   * Resumo: uploads de dados simples, por dia ou dimensões limitadas.
   * ID da transação: uploads de dados que conectam um terminal online a dados offline e associam totalmente os dados importados a um instantâneo de visitante capturado online (por exemplo, os pedidos são concluídos online e devolvidos offline).

As **[integrações do Adobe Exchange](https://www.adobeexchange.com/experiencecloud.html)** devem ser usadas:

* Ao ter contato com um provedor terceirizado que criou uma conexão que oferece suporte ao Adobe Analytics. Em geral, os aplicativos de integração incorporam dados a nível de resumo no Adobe Analytics de modo permanente e automático, regularmente.

**[API de inserção de dados em massa](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)**

* A API de inserção de dados em massa aceita arquivos formatados em CSV que contêm dados de evento, um evento por linha. A Adobe recomenda usar a API de inserção em massa para qualquer implementação que exija codificação do lado do servidor ou que não possa usar o AppMeasurement ou o SDK da web para coleta de dados.

A **[API de inserção de dados (legado)](/help/import/c-data-insertion-api/c-data-insertion-api.md)** deve ser usada:

* Quando for necessário trazer dados para o Adobe Analytics e não for possível usar o AppMeasurement, o SDK da web ou a API de inserção de dados em massa.

**[Atributos do cliente](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=pt-BR)** devem ser usados:

* Se você capturar dados de clientes empresariais em um banco de dados de gerenciamento de relacionamento com o cliente (CRM) e desejar fazer o upload dos dados para a Experience Cloud.
* Se você deseja usar os dados de CRM para executar análises mais aprofundadas no Analytics ou como critérios de segmentação no Adobe Target.

**[Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md)** deve ser usada:

* Se você deseja incorporar os dados de público-alvo do Adobe Audience Manager, como informações demográficas (por exemplo, gênero ou faixa salarial), informações psicográficas (por exemplo, interesses e hobbies), dados de CRM ou dados de impressões de anúncio em qualquer fluxo de trabalho do Analytics.
* Se você deseja que os dados de CRM carregados sejam com base no tempo, pois essa integração envia novas informações ao Analytics a cada ocorrência.

## Exportação de dados do Adobe Analytics {#export}

**[Report Builder](/help/analyze/report-builder/rb-overview.md)** deve ser usado:

* Se as opções de layout personalizadas do Workspace estiverem com limitações (tudo é possível no Report Builder, dentro dos limites do Excel).
* Para vincular livremente as entradas do usuário ou as fontes de dados offline (impressões, custo) aos dados da Adobe. As Fontes de dados são uma solução mais permanente para vincular os dados (consulte Importação de dados para o Analytics).
* Para mesclar os dados em conjunto de diferentes relatórios dimensionais (por exemplo, relatório de impressões promocionais associado ao relatório de clique para conversão promocional).
* Para mesclar dados de conjuntos de relatórios diferentes, resumindo ou exibindo na mesma tabela lado a lado.
* Se a automação por meio de agendamento for necessária (XLSX, XLSM, CSV, PDF, TXT, XML, MHT).

**[O Data Warehouse](/help/export/data-warehouse/data-warehouse.md)** deve ser usado:

* Para acessar as variáveis ocultas na interface do usuário - endereço IP, Experience Cloud ID, ID de visitante do Analytics, URL da página)
* Para acessar dados mais granulares do que a interface do usuário (exibição de tabela desnormalizada)
* Para baixar dados em um formato adequado para uma entrada de Tabela dinâmica
* Se o cliente quiser inserir dados da Adobe em uma ferramenta de dados de visualização de terceiros (ligeiramente resumida e não a nível de ocorrência)
* Para acessar todos os itens de dimensão únicos se estiver executando em “Baixo tráfego” no Adobe Analytics

O **[Feed de dados do Analytics](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md)** deve ser usado:

* Para utilizar o feed de dados mais granular que podemos fornecer (ID do visitante, ocorrência).
* Se o cliente quiser os dados da Adobe armazenados em um banco de dados do lado do cliente, no nível mais granular, eles poderão ser enviados.
* Se o cliente quiser desenvolver uma ferramenta de Inteligência empresarial (BI, Business Intelligence) ou inserir dados da Adobe a nível de ocorrência em uma ferramenta de terceiros.

As **[APIs de relatórios](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-guide.md)** devem ser usadas quando outras opções de visualização não atenderem às suas necessidades. As 3 opções de API incluem:

* **Totalmente processada**: quando quiser dados ricos em recursos (inclusive visitas, visitantes e segmentos). Isso são dados resumidos, típicos da interface do usuário do Analytics, disponíveis dentro de 30 a 90 minutos. Podem ser usados por meio do Report Builder.
* **Em tempo real**: quando quiser visualizar algumas métricas e dimensões com segundos de latência. Isso são dados limitados, parcialmente processados e resumidos, disponíveis dentro de 30 segundos. Inclui algoritmos únicos dos mais populares, ganhadores e perdedores. Podem ser usados por meio do Report Builder.
* **[!UICONTROL Livestream]**: quando quiser um fluxo de dados a nível de ocorrência, parcialmente processado do Analytics em segundos de coleção. Isso são dados parcialmente processados, disponíveis dentro de 30 segundos. Disponível apenas no Analytics Premium. Requer alguma forma de visualizar os dados, geralmente por meio de uma participação nos serviços de engenharia.

## Soluções personalizadas {#custom-solutions}

Os Serviços de engenharia devem ser usados quando:

* As outras ferramentas da Adobe não atenderem as suas necessidades.
* Você quiser uma experiência personalizada.
* Você quiser uma solução totalmente automatizada.
* Você quiser alcançar vários dispositivos.
* Você tiver múltiplas fontes de dados.
* Você possuir requisitos de dados ETL (Extract-Transform-Load) complexos.
* Você quiser uma marca personalizada.
* Você desejar visualizar o [!UICONTROL Analytics Live Stream].
