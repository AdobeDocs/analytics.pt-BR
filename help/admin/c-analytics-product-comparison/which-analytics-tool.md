---
description: Esta página de ajuda contém casos de uso recomendados para cada ferramenta do Adobe Analytics. As ferramentas devem ser consideradas na ordem em que estão listadas. Se uma determinada ferramenta não atender à necessidade, vá para a próxima para consideração.
title: Qual ferramenta do Adobe Analytics devo usar?
uuid: 1179e49d-3cfc-4abd-a8eb-35c5ae380c16
translation-type: tm+mt
source-git-commit: f7125e6845a653ca3d4dd3f1313d1b39f564459c

---


# Qual ferramenta do Adobe Analytics devo usar?

Esta página de ajuda contém casos de uso recomendados para cada ferramenta do Adobe Analytics. As ferramentas devem ser consideradas na ordem em que estão listadas. Se uma determinada ferramenta não atender à necessidade, vá para a próxima para consideração.

Para mais comparações entre produtos do Adobe Analytics, clique [aqui](/help/admin/c-analytics-product-comparison/analytics-product-comparison.md).

## Interfaces do usuário de relatórios do Adobe Analytics {#section_8265460EBB47405AB19A3B2B0729C8A4}

A **[Analysis Workspace](/help/analyze/analysis-workspace/analysis-workspace-features.md)**deve ser a interface principal do usuário para todas as suas necessidades de relatórios e análises. A Adobe continua a investir e lançar atualizações mensais para este produto. Caso haja uma tarefa que não possa ser executada na Analysis Workspace, considere as outras interfaces abaixo.**

**[Reports &amp; Analytics](/help/analyze/reports-analytics/overview/report-overview.md)**deve ser usado:

* Por usuários iniciantes que requerem acesso a relatórios pré-criados e fáceis de navegar.
* Para entender o incentivo e a confiança da atividade do Público alvo (Analytics para Público alvo/A4T).
* Para acessar dados em tempo real na interface do usuário.
* Para configurar eventos de calendário.
* Para configurar Públicos alvos.
* Para visualização do relatórios Bot.
* Para acessar visualizações de vídeo exclusivas do Visualizador simultâneo, Faixa de horário do vídeo e Suspensão do visualizador.
* Para aproveitar Listas de publicação em relatórios programados.

**[Interface do usuário do Mobile Services](https://docs.adobe.com/content/help/en/mobile-services/using/home.html)**deve ser usada:

* Se uma visualização siloada de dados do aplicativo móvel for necessária.
* Para gerenciar a implementação do SDK do seu aplicativo móvel.
* Para configurar anúncios móveis, como mensagens no aplicativo, mensagens de push e direcionamento de localização.
* Se desejarem visualizações mais interativas para dados do aplicativo (Sunburst).
* Para visualizar pontos de interesse em um mapa.
* Para métricas de valor da duração.

**[Ad Hoc Analysis](/help/analyze/ad-hoc-analysis/adhoc-home.md)**deve ser usada:

* Para exportar 50.000 linhas de dados
* Se a organização da guia do trabalho do projeto for desejada.
* Para usar o relatório de Análise do site (relatório de definição de caminho 3D).

**[Data Workbench](https://docs.adobe.com/content/help/en/data-workbench/using/home.html)**deve ser usada:

* Como a opção de ferramenta mais flexível do Analytics (análise de nível de visitante e de ocorrência).
* Para criar um conjunto de dados de vários canais de interações online e offline do CRM para o POS para a Web.
* Para atribuição avançada (com base em regras e modelos algorítmicos).
* Para modelagem preditiva e estatística (pontuação de propensão, agrupamento, correlações etc.).
* Para análise de latência (tempo antes / depois de um evento).
* Para identificação e exportação de segmentos complexos em toda a Adobe Experience Cloud.

## Importação de dados para o Adobe Analytics {#section_B42B998D6E3E4357B024AEFA4EC69A23}

**[Classificações](/help/components/c-classifications2/c-classifications.md)**devem ser usadas:

* Quando houver metadados que você deseja associar a um valor de coleta (eVar, prop, canal de marketing)
* Opções:

   * Construtor de regras: use quando houver valores formatados previsíveis sendo coletados para uma variável, por exemplo, valores delimitados. Essa abordagem permite que você configure regras uma vez e, em grande parte, &quot;configure e esqueça&quot;.
   * Importador de navegador: use quando não houver valores previsíveis ou quando tiver uma lista finita de valores que exigem uma atualização única. Esta abordagem requer um monitoramento contínuo das classificações para novos valores.

**[Fontes de dados](/help/import/c-data-sources/datasrc-home.md)**devem ser usadas:

* Quando há dados offline que você deseja gravar permanentemente no Adobe Analytics
* Opções:

   * Resumo: carregamentos de dados simples, por dia ou dimensões limitadas
   * ID da transação: uploads de dados que conectam um terminal on-line a dados off-line e associam totalmente os dados importados a um instantâneo de visitante capturado on-line (por exemplo, pedidos concluídos on-line e retornados off-line)
   * Processamento completo: fontes de dados com carimbo de data e hora, processadas como se fosse uma ocorrência coletada pelos servidores da Adobe. Ou seja, os dados são inseridos diretamente na jornada do visitante.

**[Data Connectors](https://www.adobeexchange.com/experiencecloud.html)(conhecidos formalmente como Genesis)**devem ser usados:

* Ao se envolver com um provedor de terceiros que tenha criado uma conexão compatível com o Adobe Analytics. Os Conectores de dados normalmente incorporam dados de nível de resumo ao Adobe Analytics de forma permanente e automática, de forma recorrente.

**[API da inserção de dados](https://marketing.adobe.com/developer/documentation/data-insertion/c-data-insertion-api)**deve ser usada:

* Quando você precisa fazer o upload de dados no Adobe Analytics e não pode usar o código do Adobe App Measurement ou do SDK para dispositivos móveis.

**[Atributos do cliente](/help/components/c-variables/dimensionslist/reports-customer-attributes.md)**devem ser usados:

* Se você capturar dados de clientes corporativos em um banco de dados de gerenciamento de relacionamento com o cliente (CRM) e quiser fazer upload dos dados para a Experience Cloud.
* Se você quiser usar dados do CRM para obter uma análise mais profunda no Analytics ou como critérios de definição de metas no Adobe Público alvo.

**[Análise de público-alvo](/help/integrate/c-audience-analytics/mc-audiences-aam.md)**deve ser usada:

* Se você quiser incorporar dados de audiência do Adobe Audiência Manager (AAM), como informações demográficas (por exemplo, gênero ou nível de renda), informações psicográficas (por exemplo, interesses e hobbies), dados CRM ou dados de impressão de anúncio em qualquer fluxo de trabalho do Analytics.
* Se você deseja que os dados do CRM carregados tenham por base o tempo, pois essa integração envia novas informações para o Analytics acessadas por ocorrência.

## Exportação de dados do Adobe Analytics {#section_901C06ABF2014E92B2952906723DF235}

**[Report Builder](/help/analyze/report-builder/home.md)**deve ser usado:

* Se as opções de layout personalizadas do Workspace estiverem com limitações (tudo é possível no Report Builder, dentro dos limites do Excel).
* Para vincular livremente as entradas do usuário ou as fontes de dados offline (impressões, custo) aos dados da Adobe. A solução mais permanente para vincular dados é Fontes de dados (consulte Importação de dados para o Analytics).
* Para unir dados de relatórios dimensionais diferentes (por exemplo, relatório de impressões promocionais unido ao relatório de clique para conversão promocional).
* Para visualizações entre conjuntos de relatórios.
* Se a automação por meio da programação for desejada (XLSX, XLSM, CSV, PDF, TXT, XML, MHT).

**[O Data Warehouse](/help/export/data-warehouse/data-warehouse.md)**deve ser usado:

* Para acessar as variáveis ocultas na interface do usuário - endereço IP, Experience Cloud ID, ID de visitante do Analytics, URL da página)
* Para acessar dados mais granulares do que a interface do usuário (visualização de tabela desnormalizada)
* Para baixar dados em um formato adequado para uma entrada de Tabela dinâmica
* Se o cliente quiser inserir dados da Adobe em uma ferramenta de visualização de dados de terceiros (ligeiramente resumida e não no nível de ocorrência)
* Para acessar todos os valores de dimensões únicas se estiver executando de forma &quot;Baixo tráfego&quot; no Adobe Analytics

O **[Feed de dados do Analytics](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md)**deve ser usado:

* Para utilizar o feed de dados mais granular que podemos fornecer (ID do visitante, ocorrência).
* Se o cliente quiser os dados da Adobe armazenados em um banco de dados do lado do cliente, no nível mais granular, eles poderão ser enviados.
* Se o cliente quiser desenvolver uma ferramenta de Inteligência empresarial (BI) ou inserir dados da Adobe em nível de ocorrência em uma ferramenta de terceiros.

As **[APIs de relatórios](https://marketing.adobe.com/developer/get-started/introduction/c-introduction)**devem ser usadas quando outras opções de visualização não atenderem às suas necessidades. As 3 opções de API incluem:

* **Totalmente processado**: quando quiser dados ricos em recursos (incluindo visitas, visitantes e segmentos). Esses são dados resumidos típicos da interface do usuário do Analytics, disponíveis dentro de 30 a 90 minutos. Pode ser usado por meio do Construtor de relatórios.
* **Tempo** real: quando quiser visualização algumas métricas e dimensões com segundos de latência. Esses dados são limitados, parcialmente processados e resumidos, que estão disponíveis em 30 segundos. Inclui algoritmos exclusivos dos mais populares, ganhadores e perdedores. Pode ser usado por meio do Construtor de relatórios.
* **[!UICONTROL Live Stream]**: quando quiser um fluxo de dados do Analytics de nível de ocorrência parcialmente processados em segundos de coleta. Isso são dados parcialmente processados, disponíveis dentro de 30 segundos. Disponível somente para o Analytics Premium. Requer uma maneira de visualizar os dados, normalmente por meio de um envolvimento com os Serviços de engenharia.

## Soluções personalizadas {#section_4A212F26A15947599DFB0399A0440CB6}

Os Serviços de engenharia devem ser usados quando:

* As outras ferramentas da Adobe não atenderem as suas necessidades.
* Você quer uma experiência personalizada.
* Você quer uma solução totalmente automatizada.
* Você quer alcançar muitos dispositivos.
* Você tem várias fontes de dados.
* Você possui requisitos complexos de dados ETL (Extract-Transform-Load).
* Você quer marca personalizada.
* Você quer visualizar [!UICONTROL Analytics Live Stream].
