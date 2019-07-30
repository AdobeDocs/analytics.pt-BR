---
title: Termos usados no Adobe Analytics
description: Glossário do Adobe Analytics, que define termos comuns usados.
translation-type: tm+mt
source-git-commit: 5ca51ad6b967687004d9447964ed87b29077b330

---


# Termos usados no Adobe Analytics

Use este glossário para entender o contexto de muitos termos que o Adobe Analytics usa.

* **Console de administração:** Pode se referir a:
   * Ferramentas de administração herdadas, nas quais as configurações do conjunto de relatórios no Adobe Analytics são gerenciadas. Nas versões anteriores do Adobe Analytics, as permissões do usuário também eram gerenciadas aqui. See [Admin Tools](../admin/admin/c-admin-tools.md) in the Admin user guide.
   * O admin console da Adobe, onde o acesso ao produto é provisionado e as permissões do usuário são gerenciadas. See [Admin Console](../admin/admin-console/home.md) in the Admin user guide.
* **Alocação:** Se uma variável de conversão encontrar mais de um valor durante uma visita, a configuração de alocação da variável determinará qual valor será mantido. See [Conversion variables](../admin/admin/conversion-var-admin/conversion-var-admin.md) in the Admin user guide.
* **Anomalia:** Detectado com modelagem estatística para encontrar automaticamente tendências inesperadas nos dados. O modelo analisa métricas e determina um limite inferior, um limite superior e o intervalo esperado de valores. See [Anomaly Detection](../analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) in the Analyze user guide.
* **Appmeasurement:** A biblioteca de códigos usada para coletar dados e enviá-los para a Adobe. See the [Homepage](../implement/home.md) of the Implement user guide.
* **slot ASI:** Não existe mais. Em versões anteriores do Adobe Analytics, os slots ASI forneciam um contêiner de conjunto de relatórios temporário para exibir dados segmentados. Na versão atual do Adobe Analytics, os segmentos podem ser aplicados instantaneamente a qualquer relatório.
* **Detalhamento:** Permite exibir uma dimensão no contexto de outra dimensão. See [Break down dimensions](../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) in the Analyze user guide.
* **Rejeição:** Uma visita que consiste em uma única ocorrência. See [Bounces](../components/c-variables/c-metrics/metrics-bounces.md) in the Components user guide. Consulte também Acesso único.
* **Métrica calculada:** Permite a combinação de métricas, funções estatísticas e fórmulas existentes para uso em relatórios. See [Calculated metrics](../components/c-calcmetrics/cm-overview.md) in the Components user guide.
* **Campanha:** Pode se referir a:
   * A variável Campanha, que preenche a dimensão Código de rastreamento. See [Page variables](../implement/js-implementation/c-variables/page-variables.md) in the Implement user guide.
   * Uma classificação padrão da dimensão Código de rastreamento; criado automaticamente para todos os conjuntos de relatórios.
   * Adobe Campaign, parte da Adobe Experience Cloud. More information on [Adobe.com](https://www.adobe.com/marketing/campaign.html).
* **Canal:** Pode se referir a:
   * A variável Canal, que preenche a dimensão Seções do site. See [Page variables](../implement/js-implementation/c-variables/page-variables.md) in the Implement user guide.
   * Canais de marketing, um componente que ajuda a compreender como os usuários chegam ao site. See [Marketing Channels](../components/c-marketing-channels/c-overview.md) in the Components user guide.
* **Classificação:** Um recurso no Adobe Analytics que permite o agrupamento de valores de dimensão. See [Classifications](../components/c-classifications2/c-classifications.md) in the Components user guide.
* **Feed de dados da sequência de cliques:** Consulte Feed de dados.
* **Variável de conversão:** Colloqucialmente conhecido como evars. Armazena um valor personalizado e preserva o valor da variável até que expire. See [Conversion variables](../components/c-variables/dimensionslist/reports-conversion.md) in the Components user guide.
* **Correlação:** Não é mais usado como um termo; substituído por detalhamentos de dimensão. Nas versões anteriores do Adobe Analytics, as correlações concediam a capacidade de detalhar as variáveis de tráfego. See [Break down dimensions](../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) in the Analyze user guide.
* **Dados atuais:** Uma opção em alguns relatórios que permite a inclusão dos dados coletados recentemente que ainda não foram totalmente processados. See [Current data](../analyze/reports-analytics/current-data.md) in the Analyze user guide.
* **Link personalizado:** Um tipo de hit que contém dados de exibição sem página. See the [s.tl() function](../implement/js-implementation/function-tl.md) in the Implement user guide. Consulte também Ocorrência.
* **Atributos do cliente:** Um recurso da Experience Cloud que permite o carregamento dos dados do atributo. See [Customer attributes](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/attributes.html) in the Core Services user guide.
* **Delegado de suporte ao cliente:** Um usuário designado autorizado a interagir diretamente com o Atendimento ao cliente da Adobe. See [Customer support delegates](https://helpx.adobe.com/experience-cloud/supported-users.html) in the Experience Cloud Knowledgebase.
* **Conectores de dados:** Uma solução de desenvolvimento completa que permite que terceiros automatizem o carregamento de dados no Adobe Analytics. Os clientes dessa terceiros podem usar um conector de dados para aprimorar seus dados no Adobe Analytics. A maioria dos conectores de dados usa um fluxo de trabalho semelhante usado nas Fontes de Dados. Consulte Conectores de dados no Guia do usuário Importar.
* **Feed de dados:** Uma exportação de dados brutos que lista cada ocorrência como uma linha e variáveis como colunas separadas. Mais usado para exportar dados do Adobe Analytics para um banco de dados de terceiros. See [Data feeds](../export/analytics-data-feed/c-getstarted/data-feed-overview.md) in the Export user guide.
* **Fontes de dados:** Permite que um usuário faça upload de dados de um arquivo para o Adobe Analytics. Normalmente, o arquivo é extraído de um site FTP. See [Data Sources](../import/c-data-sources/datasrc-home.md) in the Import user guide.
* **Data Warehouse:** Um recurso no Adobe Analytics que permite solicitar relatórios maiores. See [Data Warehouse](../export/data-warehouse/data-warehouse.md) in the Export user guide.
* **Dimensão:** Um tipo de componente que contém valores de variável, como texto. Os exemplos incluem Nome da página, Código de rastreamento ou Domínio de referência. Uma métrica geralmente é a sua contraparte.
* **Gerenciamento dinâmico de tags:** Solução antiga de gerenciamento de tags da Adobe. See [DTM implementation overview](../implement/c-implement-with-dtm/dtm-implementation-overview.md) in the Implement user guide. A Adobe recomenda usar o Adobe Experience Platform Launch.
* **Serialização de eventos:** O processo de implementação de medidas para impedir a coleção de eventos duplicados. See [Event serialization](../implement/js-implementation/event-serialization.md) in the Implement user guide.
* **Evar:** Consulte Variável de conversão.
* **Evento:** Consulte Evento bem-sucedido.
* **Excelclient:** Não é mais usado como um termo. O nome do antecessor do Construtor de relatórios.
* **Expiração:** No contexto de uma variável de conversão, o valor persiste no backend. Essa persistência permite que eventos associem-se aos valores de variável antes da ocorrência do evento. See [Conversion variables](../admin/admin/conversion-var-admin/conversion-var-admin.md) in the Admin user guide.
* **Fluxo:** Um tipo de visualização na Analysis Workspace que mostra quais caminhos os usuários tomaram em seu site. See [Flow visualization](../analyze/analysis-workspace/visualizations/c-flow/flow.md) in the Analyze user guide.
* **Genesis:** Não é mais usado como um termo. O nome anterior dos Conectores de dados.
* **Conjunto de relatórios global:** Um termo informal designado para um conjunto de relatórios que coleta ocorrências de vários sites.
* **Código H:** Um antecessor do appmeasurement. Em versões anteriores do Adobe Analytics, as versões de código eram medidas por "versão H", como H 24, H 23.1 etc.
* **Ocorrência:** Uma solicitação de imagem única enviada para os servidores de coleta de dados da Adobe. As exibições de página e links personalizados podem ser referenciadas como ocorrências.
* **Solicitação de imagem:** Uma imagem transparente de 1 x 1 pixels usada para se comunicar com os servidores de coleta de dados da Adobe. Um site solicita essa imagem invisível com uma longa string de consulta contendo dados; A Adobe retorna a imagem invisível e analisa a string de consulta recebida.
* **Insight:** Pode se referir a:
   * O nome anterior do Análise de big data.
   * Insight personalizado, um nome histórico para a variável de tráfego personalizada.
* **KPI:** Abreviação do indicador-chave de desempenho. Métricas que ajudam uma empresa a entender como o seu site está se saindo. Cada organização tem diferentes KPI que avaliam diferentes aspectos de seus negócios. See [Create a solution design document](../implement/prepare/solution-design.md) in the Implement user guide.
* **Latência:** O atraso entre quando os dados são coletados e quando estão disponíveis nos relatórios. A latência típica em um conjunto de relatórios é de 30a 90 minutos. See [Latency](../technotes/latency.md) in the Technotes user guide.
* **Lançamento:** Breve para o Adobe Experience Platform Launch, solução de implementação atual da Adobe. See [Overview](https://docs.adobe.com/content/help/en/launch/using/overview.html) in the Adobe Experience Platform Launch user guide.
* **List prop:** Uma configuração que converte uma variável de tráfego típica para suportar vários valores na mesma ocorrência. Qualquer variável de tráfego personalizada pode se tornar uma propriedade de lista se a configuração estiver ativada. See [Page variables](../implement/js-implementation/c-variables/page-variables.md) in the Implement user guide.
* **List var:** Uma variável distinta separada para variáveis de conversão. As vars de lista oferecem suporte para vários valores na mesma ocorrência, e os valores de variáveis são preservados em uma visita, semelhante às variáveis de conversão. Apenas três list vars estão disponíveis para uma organização. See [Page variables](../implement/js-implementation/c-variables/page-variables.md) in the Implement user guide.
* **Empresa de logon:** Uma coleção de conjuntos de relatórios usados por sua organização. Algumas organizações possuem várias empresas de logon que se aplicam a partes diferentes da organização.
* **Métrica:** Um tipo de componente que contém dados quantitativos. Normalmente, os valores de métrica contêm números, como Exibições de página, Visitas e Receita. Uma dimensão geralmente é a sua contraparte.
* **Marcação de vários relatórios:** A prática de enviar a mesma ocorrência para vários conjuntos de relatórios. Com a introdução aos conjuntos de relatórios virtuais, essa prática não é mais necessária. A maioria dos esforços de marcação de vários relatórios ajuda a acomodar um conjunto de relatórios global.
* **Normalização:** Uma maneira de organizar uma visualização que utiliza todas as métricas e as força a proporções iguais, permitindo uma comparação mais fácil das tendências.
* **Omniture:** Não é mais usado como um termo. A organização que pertence ao Adobe Analytics antes de ser adquirida pela Adobe em 2009.
* **Definição de caminho:** Consulte Fluxo.
* **Relatório classificado:** Um formato de relatório que normalmente segue uma dimensão com uma métrica. Esse tipo de relatório permite ver os itens principais, como as páginas mais visualizadas no site. Consulte também Relatório de tendência.
* **Tempo real:** Exibe variáveis configuradas assim que são coletadas com pouca latência. See [Real-time reports](../admin/admin/realtime/realtime.md) in the Admin user guide.
* **Conjunto de relatórios:** Um contêiner abrangente para o qual você envia dados. Todos os relatórios do Adobe Analytics fazem referência a um conjunto de relatórios.
* **RSID:** Abreviação da ID do conjunto de relatórios. Um conjunto de relatórios tem um nome amigável e uma ID de conjunto de relatórios.
* **Exibição de página:** Um tipo de hit que aumenta as exibições de página. See [Page views](../components/c-variables/c-metrics/metrics-page-view.md) in the Components user guide. Consulte também Ocorrência.
* **Regras de processamento:** Pode se referir a:
   * Regras de processamento, uma maneira de alterar a coleta de dados usando determinadas regras no Console de administração. See [Processing rules](../admin/admin/c-processing-rules/processing-rules.md) in the Admin user guide.
   * Regras de processamento de canal de marketing, um conjunto de regras que determina em qual canal de marketing uma ocorrência pertence. See [Marketing channel processing rules](../admin/admin/marketing-channels-admin.md) in the Admin user guide.
* **Prop:** Consulte Variável de tráfego.
* **s. t ():** O nome da função em uma biblioteca appmeasurement que envia uma solicitação de imagem de exibição de página. Some AppMeasurement libraries use `s.track()` instead. See [s.t()](../implement/js-implementation/function-t.md) in the Implement user guide.
* **s<span>.</span>tl ():** O nome da função em uma biblioteca appmeasurement que envia uma solicitação de imagem de rastreamento de link. Some AppMeasurement libraries use `s.trackLink()` instead. See [s.tl()](../implement/js-implementation/function-tl.md) in the Implement user guide.
* **Satélite:** Não é mais usado como um termo. O nome do produto anterior para o Gerenciamento dinâmico de tags.
* **Segmento:** Permite concentrar-se no subconjunto específico de seus dados. See [Segmentation](../components/c-segmentation/seg-overview.md) in the Components user guide.
* **Contêiner de segmento:** A parte de um segmento que determina quantos dados serão trazidos. Os contêineres podem se basear em exibição de página, visita ou visitante. See [Segmentation](../components/c-segmentation/seg-overview.md) in the Components user guide.
* **Serialização:** Consulte Serialização de eventos.
* **Chamada do servidor:** Nome alternativo para uma solicitação de imagem ou ocorrência, usada principalmente no contexto do faturamento.
* **Acesso único:** Uma visita em que uma dimensão tinha apenas um único valor exclusivo. A visita pode ter várias ocorrências, desde que não haja vários valores únicos. See [Single access](../components/c-variables/c-metrics/metrics-single-access.md) in the Components user guide. Consulte também Rejeição.
* **Sitecatalyst:** Não é mais usado como um termo. O nome do produto anterior para o Adobe Analytics.
* **Sub-relação:** Não é mais usado como um termo; substituído por detalhamentos de dimensão. Nas versões anteriores do Adobe Analytics, as sub-relações concediam a capacidade de detalhar as variáveis de conversão. See [Break down dimensions](../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) in the Analyze user guide.
* **Evento bem-sucedido:** Uma ação rastreada que o usuário tomou. A organização determina quais eventos devem ser rastreados e quais variáveis de evento de sucesso você usa para acompanhá-la. See [Custom events](../components/c-variables/c-metrics/metrics-custom.md) in the Components user guide.
* **Usuário suportado:** Consulte Delegado de suporte ao cliente.
* **Variável de tráfego:** Colloqucialmente conhecido como props. Armazena um valor personalizado para uma única ocorrência. As versões anteriores do Adobe Analytics emitiam um valor exclusivo, mas as melhorias na plataforma tornavam as variáveis de tráfego personalizadas amplamente desnecessárias. Na maioria dos casos, a Adobe recomenda utilizar variáveis de conversão personalizadas (evars). See [Custom traffic variables](../components/c-variables/dimensionslist/reports-custom-traffic.md) in the Components user guide.
* **Relatório de tendência:** Um formato de relatório que geralmente mostra vários intervalos de datas com uma métrica. Esse tipo de relatório permite ver como uma métrica ocorre com o tempo. Consulte também relatório classificado.
* **Visitante único**: Representa o número de indivíduos únicos que visitaram seu site. Um único visitante único pode ter várias visitas. See [Unique visitor](../components/c-variables/c-metrics/metrics-unique-visitors.md) in the Components user guide.
* **Conjunto de relatórios virtuais:** Um contêiner virtual de dados que referencia um conjunto de relatórios regular e permite o refinamento dos dados. Os dados não são enviados para um conjunto de relatórios virtual; em vez disso, os dados são enviados para um conjunto de relatórios regular e um conjunto de relatórios virtual é construído fora dos dados coletados. See [Virtual report suites](../components/vrs/vrs-about.md) in the Components user guide.
* **Visita:** Representa o número de sessões únicas que ocorreram em seu site. See [Visits](../components/c-variables/c-metrics/metrics-visit.md) in the Components user guide.
* **Regra VISTA:** Lógica personalizada criada pela Adobe na solicitação de um cliente para copiar, analisar ou filtrar o lado do servidor de dados. Normalmente, as regras VISTA resultam em custos adicionais. Consulte também Regras de processamento.
* **Web beacon:** Consulte Solicitação de imagem.
