---
description: Esta página de ajuda contém casos de uso recomendados para cada ferramenta do Adobe Analytics. As ferramentas devem ser consideradas na ordem em que são listadas. Se determinada ferramenta não atender à necessidade, passe para a próxima para consideração.
title: Qual ferramenta do Adobe Analytics devo usar?
feature: Analytics Basics
exl-id: d65575df-19c6-4129-89c8-d36de7bb6b2f
TQID: https://experienceleague.adobe.com/xk485fKU7Q2DeZIYaTtN-a4JKnyVamAygW03z7ffAOk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: a421fb65-2c82-457a-921c-28c46b697a39
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: c2ae876122715b4fa6367326dc23479dd9648021
workflow-type: tm+mt
source-wordcount: 1175
ht-degree: 66%

---

# Qual ferramenta do Adobe Analytics devo usar?

Esta página de ajuda contém casos de uso recomendados para cada ferramenta do Adobe Analytics. As ferramentas devem ser consideradas na ordem em que são listadas. Se determinada ferramenta não atender à necessidade, passe para a próxima para consideração.

Para obter mais informações sobre comparações de produtos do Adobe Analytics, consulte [Comparação entre produtos do Analytics](/help/analyze/get-started/analytics-product-comparison.md).


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Comparação das ferramentas](https://video.tv.adobe.com/v/30585?captions=por_br&quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

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

* Se você capturar os dados de clientes de empresas em um banco de dados de gerenciamento de relacionamento com o cliente (CRM) e quiser fazer upload dos dados para o CX Enterprise.
* Se quiser usar os dados do CRM para uma análise mais profunda no Analytics ou como critério de direcionamento no Adobe Target.

**[Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md)** deve ser usada:

* Se você deseja incorporar os dados de público-alvo do Adobe Audience Manager, como informações demográficas (por exemplo, gênero ou faixa salarial), informações psicográficas (por exemplo, interesses e hobbies), dados de CRM ou dados de impressões de anúncio em qualquer fluxo de trabalho do Analytics.
* Se você quiser que os dados do CRM carregados sejam baseados em tempo, pois essa integração envia novas informações para o Analytics ocorrência por ocorrência.

## Exportação de dados do Adobe Analytics {#export}

**[Report Builder](/help/analyze/report-builder/rb-overview.md)** deve ser usado:

* Se as opções de layout personalizadas do Workspace estiverem com limitações (tudo é possível no Report Builder, dentro dos limites do Excel).
* Para vincular livremente as entradas do usuário ou as fontes de dados offline (impressões, custo) aos dados do Adobe. Uma solução mais permanente para vinculação de dados é a das Fontes de dados (consulte Importação de dados para o Analytics).
* Para mesclar os dados em conjunto de diferentes relatórios dimensionais (por exemplo, relatório de impressões promocionais associado ao relatório de clique para conversão promocional).
* Para mesclar dados de conjuntos de relatórios diferentes, resumindo ou exibindo na mesma tabela lado a lado.
* Se a automação por meio de agendamento for necessária (XLSX, XLSM, CSV, PDF, TXT, XML, MHT).

**[O Data Warehouse](/help/export/data-warehouse/data-warehouse.md)** deve ser usado:

* Para acessar as variáveis ocultas na interface do usuário - endereço IP, Experience Cloud ID, ID de visitante do Analytics, URL da página)
* Para acessar dados mais granulares que a interface do usuário (exibição de tabela desnormalizada)
* Para baixar dados em um formato adequado para uma entrada de Tabela Dinâmica
* Se o cliente quiser inserir dados do Adobe em uma ferramenta de visualização de dados de terceiros (ligeiramente resumida e não no nível de ocorrência)
* Para acessar todos os itens de dimensão únicos se estiver executando em “Baixo tráfego” no Adobe Analytics

O **[Feed de dados do Analytics](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md)** deve ser usado:

* Para utilizar o feed de dados mais granular que podemos fornecer (ID de visitante, ocorrência).
* Se o cliente quiser os dados da Adobe armazenados em um banco de dados do lado do cliente, no nível mais granular, eles poderão ser enviados.
* Se o cliente quiser desenvolver uma ferramenta Business Intelligence (BI) ou inserir dados de nível de ocorrência do Adobe em uma ferramenta de terceiros.

As **[APIs de relatórios](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-guide.md)** devem ser usadas quando outras opções de visualização não atenderem às suas necessidades. As 3 opções de API incluem:

* **Totalmente processado**: quando quiser dados com muitos recursos (incluindo visitas, visitantes e segmentos). Esses são dados resumidos típicos da interface do usuário do Analytics, disponíveis em ~30 a 90 minutos. Pode ser usado por meio do Report Builder.
* **Tempo real**: quando quiser exibir algumas métricas e dimensões com segundos de latência. São dados limitados, parcialmente processados e resumidos que estão disponíveis em aproximadamente 30 segundos. Inclui algoritmos exclusivos dos mais populares, ganhadores e perdedores. Pode ser usado por meio do Report Builder.
* **[!UICONTROL Livestream]**: quando quiser um fluxo de dados a nível de ocorrência, parcialmente processado do Analytics em segundos de coleção. São dados parcialmente processados, disponíveis em ~30 segundos. Disponível somente para o Analytics Premium. Exige alguma maneira de visualizar os dados, normalmente por meio de um contrato dos Serviços de engenharia.

## Soluções personalizadas {#custom-solutions}

Os Serviços de engenharia devem ser usados quando:

* As outras ferramentas da Adobe não atenderem as suas necessidades.
* Você quer uma experiência personalizada.
* Você deseja uma solução totalmente automatizada.
* Você deseja acessar muitos dispositivos.
* Você tem várias fontes de dados.
* Você tem requisitos complexos de dados do ETL (Extract-Transform-Load).
* Você quer uma marca personalizada.
* Você deseja visualizar o [!UICONTROL Analytics Live Stream].
