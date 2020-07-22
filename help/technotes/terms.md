---
title: Termos usados no Adobe Analytics
description: Glossário do Adobe Analytics, que define termos comuns usados.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '2458'
ht-degree: 95%

---


# Termos usados no Adobe Analytics

Use este glossário para entender o contexto de muitos termos que o Adobe Analytics usa.

* **Activity Map:** um plug-in de navegador que mostra quais áreas do site foram mais clicadas. Consulte [Activity Map](/help/analyze/activity-map/activity-map.md) no guia do usuário Analisar.
* **Admin Console:** pode se referir a:
   * Ferramentas administrativas herdadas, onde as configurações do conjunto de relatórios no Adobe Analytics são gerenciadas. Em versões anteriores do Adobe Analytics, as permissões de usuário também eram gerenciadas aqui. Consulte [Ferramentas administrativas](/help/admin/admin/c-admin-tools.md) no guia do usuário Administração.
   * O Admin Console da Adobe, onde o acesso ao produto é provisionado e as permissões do usuário são gerenciadas. Consulte [Admin Console](/help/admin/admin-console/home.md) no guia do usuário Administração.
* **Alocação:** se uma variável de conversão encontrar mais de um valor durante uma visita, a configuração de alocação da variável determinará qual valor será mantido. Consulte [Variáveis de conversão](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) no guia do usuário Administração.
* **Anomalia:** é detectada com modelagem estatística para que encontre automaticamente tendências inesperadas em seus dados. O modelo analisa métricas e determina um limite inferior, um limite superior e o intervalo esperado de valores. Consulte [Detecção de anomalias](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) no guia do usuário Analisar.
* **AppMeasurement:** a biblioteca de códigos usada para coletar dados e enviá-los para a Adobe. Consulte a [Página inicial](/help/implement/home.md) do guia do usuário Implementar.
* **Slot ASI:** não existe mais. Em versões anteriores do Adobe Analytics, os slots ASI forneciam um contêiner temporário de conjunto de relatórios para exibir dados segmentados. Na versão atual do Adobe Analytics, os segmentos podem ser aplicados instantaneamente a qualquer relatório.
* **Detalhamento:** permite que você visualize uma dimensão dentro do contexto de outra dimensão. Consulte [Analisar dimensões](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) no guia do usuário Analisar.
* **Rejeição:** uma visita que consiste em uma única ocorrência. Consulte [Rejeições](/help/components/metrics/bounces.md) no guia do usuário Componentes. Consulte também Acesso único.
* **Métrica calculada:** permite a combinação de métricas, funções estatísticas e fórmulas existentes para uso no relatório. Consulte [Métricas calculadas](/help/components/c-calcmetrics/cm-overview.md) no guia do usuário Componentes.
* **Campanha:** pode se referir a:
   * A variável Campanha, que preenche a dimensão Código de rastreamento. Consulte [Campanha](../implement/vars/page-vars/campaign.md) no guia de usuário Implementar.
   * Uma classificação padrão da dimensão Código de rastreamento, criada automaticamente para todos os conjuntos de relatórios.
   * Adobe Campaign, parte da Adobe Experience Cloud. Mais informações em [Adobe.com](https://www.adobe.com/br/marketing/campaign.html).
* **Canal:** pode se referir a:
   * A variável Canal, que preenche a dimensão Seções do site. Consulte [Variáveis de página](/help/implement/vars/page-vars/page-variables.md) no guia do usuário Implementar.
   * Canais de marketing, um componente que ajuda a entender como os usuários chegam ao seu site. Consulte [Canais de marketing](/help/components/c-marketing-channels/c-getting-started-mchannel.md) no guia do usuário Componentes.
* **Classificação:** Um recurso no Adobe Analytics que permite o agrupamento de itens de dimensão. Consulte [Classificações](/help/components/c-classifications2/c-classifications.md) no guia do usuário Componentes.
* **Clickmap:** não é mais usado. Um plug-in de navegador herdado que mostra quais áreas do site foram mais clicadas. Esta ferramenta foi removida em favor do Activity Map.
* **Feed de sequência de cliques:** consulte Feed de dados.
* **Coorte:** um grupo de pessoas que compartilham características comuns em um determinado período. Consulte [O que é a Análise de coorte?](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) no guia do usuário Analisar.
* **Servidor de coleta:** consulte Servidor de coleta de dados.
* **Variáveis de dados de contexto:** variáveis temporárias usadas apenas nas regras de processamento. Os valores da variável de dados de contexto são perdidos permanentemente se uma regra de processamento não os copiar para uma variável de conversão ou de tráfego. Consulte [Variáveis de dados de contexto](../implement/vars/page-vars/contextdata.md) no guia do usuário Implementar.
* **Variável de conversão:** Também conhecido como eVars. Armazena um valor personalizado e preserva o valor da variável até que expire. Consulte a dimensão [eVar](/help/components/dimensions/evar.md) no guia do usuário Componentes.
* **Correlação:** não é mais usado como termo; substituído por Detalhamentos de dimensão. Em versões anteriores do Adobe Analytics, as correlações permitiam detalhar as variáveis de tráfego. Consulte [Analisar dimensões](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) no guia do usuário Analisar.
* **Dados atuais:** uma opção em alguns relatórios que permite a inclusão de dados coletados recentemente que ainda não foram totalmente processados. Consulte [Dados atuais](/help/analyze/reports-analytics/current-data.md) no guia do usuário Analisar.
* **Link personalizado:** um tipo de ocorrência que contém dados de exibição que não sejam de página. Consulte a [função s.tl()](../implement/vars/functions/tl-method.md) no guia do usuário Implementar. Consulte também Hit.
* **Atributos do cliente:** um recurso da Experience Cloud que permite o upload de dados de atributos. Consulte [Atributos do cliente](https://docs.adobe.com/content/help/pt-BR/core-services/interface/customer-attributes/attributes.html) no guia do usuário dos Serviços principais.
* **Representante de suporte ao cliente:** um usuário designado autorizado a interagir diretamente com o Atendimento ao cliente da Adobe. Consulte [Delegados de suporte ao cliente](https://helpx.adobe.com/br/experience-cloud/supported-users.html) na Base de conhecimento da Experience Cloud.
* **Servidor de coleta de dados:** servidores da Adobe que recebem e processam dados. As solicitações de imagem são enviadas aos servidores de coleta de dados da Adobe para uso nos relatórios.
* **Conectores de dados:** uma solução completa de desenvolvimento que permite a terceiros automatizar o carregamento de dados no Adobe Analytics. Os clientes desse terceiro podem usar um conector de dados para enriquecer seus dados no Adobe Analytics. A maioria dos conectores de dados usa um fluxo de trabalho semelhante usado nas Fontes de dados. Consulte Data Connectors no guia do usuário Importar.
* **Feed de dados:** uma exportação de dados brutos que lista cada hit como uma linha e variáveis como colunas separadas. Usado mais frequentemente para exportar dados do Adobe Analytics para um banco de dados de terceiros. Consulte [Feeds de dados](/help/export/analytics-data-feed/data-feed-overview.md) no guia do usuário Exportar.
* **Fontes de dados:** permite que um usuário carregue dados de um arquivo no Adobe Analytics. O arquivo normalmente é extraído de um site FTP. Consulte [Fontes de dados](/help/import/c-data-sources/datasrc-home.md) no guia do usuário Importar.
* **Data Warehouse:** um recurso no Adobe Analytics que permite solicitar relatórios maiores. Consulte [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) no guia do usuário Exportar.
* **Dimensão:** um tipo de componente que contém valores variáveis, como texto. Os exemplos incluem Nome da página, Código de rastreamento ou Domínio de referência. Normalmente, uma métrica é sua contrapartida.
* **Dynamic Tag Management:** a antiga solução de gerenciamento de tags da Adobe. Consulte [Visão geral da implementação do DTM](/help/implement/other/dtm/dtm-implementation-overview.md) no guia de usuário Implementar. A Adobe recomenda usar o Adobe Experience Platform Launch.
* **Serialização de eventos:** o processo de implementação de medidas para impedir a coleta de eventos duplicados. Consulte [Serialização de eventos](../implement/vars/page-vars/events/event-serialization.md) no guia de usuário Implementar.
* **eVar:** consulte Variável de conversão.
* **Evento:** consulte Evento bem-sucedido.
* **ExcelClient:** não é mais usado como termo. O nome do antecessor do Report Builder.
* **Expiração:** no contexto de uma variável de conversão, quanto tempo o valor persiste no back-end. Essa persistência permite que os eventos sejam associados a valores variáveis antes da ocorrência do evento. Consulte [Variáveis de conversão](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) no guia do usuário Administração.
* **Fluxo:** um tipo de visualização na Analysis Workspace que mostra os caminhos que os usuários fizeram em seu site. Consulte [Visualização de fluxo](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) no guia do usuário Analisar.
* **Genesis:** não é mais usado como termo. Nome antigo dos Data Connectors.
* **Conjunto de relatórios global:** um termo informal designado para um conjunto de relatórios que coletam ocorrências de vários sites.
* **Código H:** um antecessor do AppMeasurement. Em versões anteriores do Adobe Analytics, as versões de código eram medidas pela &quot;versão H&quot;, como H.27.5, H.26, etc.
* **Hit:** uma única solicitação de imagem enviada para os servidores de coleta de dados da Adobe. Exibições de página e links personalizados podem ser chamados de hits.
* **Solicitação de imagem:** uma imagem de pixel 1x1 transparente usada para comunicação com os servidores de coleta de dados da Adobe. Um site solicita esta imagem invisível com uma longa string de consulta contendo dados; a Adobe retorna a imagem invisível e analisa a string de consulta recebida.
* **Insight:** pode se referir a:
   * O nome anterior do Data Workbench.
   * Custom Insight, um nome histórico para variável de tráfego personalizada.
* **KPI:** abreviação do indicador principal de desempenho. Métricas que ajudam uma empresa a entender o desempenho de seu site. Cada organização tem KPIs diferentes que medem diferentes aspectos de seus negócios. Consulte [Criar um documento de design de solução](/help/implement/prepare/solution-design.md) no guia do usuário Implementar.
* **Latência:** o atraso entre quando os dados são coletados e quando estão disponíveis nos relatórios. A latência típica em um conjunto de relatórios é de 30 a 90 minutos. Consulte [Latência](/help/technotes/latency.md) no guia do usuário do Technotes.
* **Iniciar:** abreviação de Adobe Experience Platform Launch, a solução de implementação atual da Adobe. Consulte [Visão geral](https://docs.adobe.com/content/help/pt-BR/launch/using/overview.html) no guia do usuário do Adobe Experience Platform Launch.
* **Prop de lista:** uma configuração que converte uma variável de tráfego típica para suportar vários valores na mesma ocorrência. Qualquer variável de tráfego personalizada pode se tornar uma propriedade de lista se a configuração estiver ativada. Consulte [prop](../implement/vars/page-vars/prop.md) no guia de usuário Implementar.
* **Var de lista:** uma variável distinta separada para variáveis de conversão. Vars de lista suportam vários valores no mesmo hit, e os valores variáveis são preservados em uma visita, de modo semelhante às variáveis de conversão. Somente três variável de lista estão disponíveis para uma organização. Consulte [Lista](/help/implement/vars/page-vars/list.md) no guia de usuário Implementar.
* **Empresa de logon:** uma coleção de conjuntos de relatórios utilizada pela organização. Algumas organizações possuem várias empresas de logon, que se aplicam a setores diferentes da organização.
* **Canal de marketing:** um recurso no Adobe Analytics que categoriza os hits de acordo com a forma como elas chegaram ao site. A lógica usada para categorizar hits pode ser personalizada usando as regras de processamento do canal de marketing. Consulte [Introdução aos canais de marketing](/help/components/c-marketing-channels/c-getting-started-mchannel.md) no guia do usuário Componentes.
* **Métrica:** um tipo de componente que contém dados quantitativos. Os valores de métricas normalmente contêm números, como Exibições de página, Visitas e Receita. Uma dimensão é normalmente sua contrapartida.
* **Marcação de vários relatórios:** a prática de enviar a mesma ocorrência para vários conjuntos de relatórios. Com a introdução aos conjuntos de relatórios virtuais, essa prática não é mais necessária. A maioria dos esforços de marcação de vários relatórios ajuda a acomodar um conjunto de relatórios global.
* **Normalização:** uma maneira de organizar uma visualização que utiliza todas as métricas e as força a proporções iguais, permitindo uma comparação mais fácil das tendências.
* **Ocorrências:** Um tipo de métrica que mostra quantas ocorrências um item de dimensão foi definido ou persistiu. Consulte a métrica [Ocorrências](/help/components/metrics/occurrences.md) no guia do usuário Componentes.
* **Omniture:** não é mais usado como termo. Organização que era proprietária do Adobe Analytics antes de ser adquirida pela Adobe em 2009.
* **Definição de caminho:** consulte Fluxo.
* **Exibição de página:** um tipo de hit que aumenta as exibições de página. Consulte a métrica [visualizações](/help/components/metrics/page-views.md) de página no guia do usuário Componentes. Consulte também Hit.
* **Persistência:** um conceito abstrato para variáveis de conversão que permite a vinculação entre um valor variável e um evento que ocorre em hits separados. Consulte também Expiração.
* **Chamada do servidor primário:** nome alternativo para solicitação de imagem ou hit, usado principalmente no contexto de marcação e cobrança de vários conjuntos. Quando o mesmo hit é enviado para vários conjuntos de relatórios, o primeiro conjunto de relatórios é uma chamada de servidor primário enquanto o restante são chamadas de servidor secundário. Esta regra se aplica a todos os tipos de hits, incluindo exibição de página e rastreamento de link. Consulte também Chamadas de servidor secundário.
* **Regras de processamento:** pode se referir a:
   * Regras de processamento, uma forma de alterar a coleta de dados usando determinadas regras no Admin Console. Consulte [Regras de Processamento](/help/admin/admin/c-processing-rules/processing-rules.md) no guia do usuário Administração
   * Regras de processamento de canal de marketing, um conjunto de regras que determina a qual canal de marketing um hit pertence. Consulte [Regras de Processamento do canal de marketing](/help/admin/admin/marketing-channels-admin.md) no guia do usuário Administração
* **Prop:** consulte Variável de tráfego.
* **Relatório classificado:** um formato de relatório que normalmente segue uma dimensão com uma métrica. Esse tipo de relatório permite que você veja os principais itens, como as páginas mais visualizadas do site. Consulte também Relatório de tendências.
* **Tempo real:** exibe as variáveis configuradas assim que são coletadas com pouca ou nenhuma latência. Consulte [Relatórios em tempo real](/help/admin/admin/realtime/realtime.md) no guia do usuário Administração
* **Conjunto de relatórios:** um contêiner abrangente para o qual você envia dados. Todos os relatórios no Adobe Analytics fazem referência a um conjunto de relatórios.
* **Intervalo de datas em andamento:** um tipo de intervalo de datas relativo que muda conforme o tempo passa. Por exemplo, um relatório que mostra os últimos 7 dias pode ser considerado um intervalo de datas em andamento. Consulte também intervalo de datas estático.
* **RSID:** abreviação da ID do conjunto de relatórios. Um conjunto de relatórios tem um nome amigável e uma ID de conjunto de relatórios.
* **s.t():** o nome da função em uma biblioteca do AppMeasurement que envia uma solicitação de imagem de exibição de página. Algumas bibliotecas do AppMeasurement usam `s.track()`. Consulte [t](../implement/vars/functions/t-method.md) no guia de usuário Implementar.
* **s<span>.</span>tl():** o nome da função em uma biblioteca do AppMeasurement que envia uma solicitação de imagem de rastreamento de link. Algumas bibliotecas do AppMeasurement usam `s.trackLink()`. Consulte [tl](../implement/vars/functions/tl-method.md) no guia de usuário Implementar.
* **s_code.js:** o nome do arquivo JavaScript usado em versões históricas do Adobe Analytics. O nome atual do arquivo JavaScript usado é AppMeasurement.js.
* **Satellite:** não é mais usado como termo. Antigo nome de produto do Dynamic Tag Management.
* **Chamada de servidor secundário:** nome alternativo para solicitação de imagem ou hit, usado principalmente no contexto de marcação e cobrança de vários conjuntos. Quando o mesmo hit é enviado para vários conjuntos de relatórios, todos os conjuntos de relatórios depois do primeiro listado são chamadas de servidor secundário. Consulte também Chamadas de servidor primário.
* **Segmento:** permite que você se concentre em um subconjunto específico de seus dados. Consulte [Segmentação](/help/components/c-segmentation/seg-overview.md) no guia do usuário Componentes.
* **Contêiner de segmento:** a parte de um segmento que determina a quantidade de dados a serem trazidos. Os contêineres podem se basear na exibição de página, visita ou visitante. Consulte [Segmentação](/help/components/c-segmentation/seg-overview.md) no guia do usuário Componentes.
* **Serialização:** consulte Serialização de eventos.
* **Chamada de servidor:** nome alternativo para uma solicitação de imagem ou hit, usado principalmente no contexto da cobrança.
* **Acesso único:** uma visita em que uma dimensão tinha apenas um único valor exclusivo. A visita pode ter vários hits, desde que não haja vários valores únicos. Consulte a métrica de acesso [](/help/components/metrics/single-access.md) único no guia do usuário Componentes. Consulte também Rejeição.
* **SiteCatalyst:** não é mais usado como termo. Antigo nome de produto do Adobe Analytics.
* **Documento de design da solução:** também conhecido como referência de design de solução, ou SDR Um documento interno mantido por uma organização que descreve como as variáveis personalizadas são usadas e a lógica usada para preenchê-las. Consulte [Criar um documento de design de solução](/help/implement/prepare/solution-design.md) no guia do usuário Implementar.
* **Sub-relação:** não é mais usado como termo; substituído por Detalhamentos de dimensão. Em versões anteriores do Adobe Analytics, as sub-relações permitiam detalhar as variáveis de conversão. Consulte [Analisar dimensões](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) no guia do usuário Analisar.
* **Evento bem-sucedido:** uma ação rastreada feita por um usuário. Sua organização determina quais eventos rastrear e quais variáveis de evento de sucesso você usa para rastreá-los. Consulte [Eventos personalizados](/help/components/metrics/custom-events.md) no guia do usuário Componentes.
* **Usuário suportado:** consulte Delegado de suporte ao cliente.
* **Variável de tráfego:** Também conhecido como props. Armazena um valor personalizado para um único hit. As versões anteriores do Adobe Analytics davam valor exclusivo às props, mas as melhorias na plataforma tornam as variáveis de tráfego personalizadas amplamente desnecessárias. A Adobe recomenda usar variáveis de conversão personalizadas (eVars) na maioria dos casos. Consulte a dimensão [Prop](/help/components/dimensions/prop.md) no guia do usuário Componentes.
* **Relatório de tendências:** um formato de relatório que normalmente mostra vários intervalos de datas com uma métrica. Esse tipo de relatório permite que você veja como uma métrica é executada ao longo do tempo. Consulte também Relatório classificado.
* **Visitante único**: representa o número de indivíduos únicos que visitaram seu site. Um visitante único pode ter várias visitas. See the [Unique visitors](/help/components/metrics/unique-visitors.md) metric in the Components user guide.
* **Conjunto de relatórios virtuais:** um contêiner virtual de dados que faz referência a um conjunto de relatórios normal e permite o refinamento de dados. Os dados não são enviados a um conjunto de relatórios virtual; em vez disso, os dados são enviados a um conjunto de relatórios normal e um conjunto de relatórios virtual é construído a partir desses dados coletados. Consulte [Conjuntos de relatórios virtuais](/help/components/vrs/vrs-about.md) no guia do usuário Componentes.
* **Visita:** representa o número de sessões únicas que ocorreram no site. See the [Visits](/help/components/metrics/visits.md) metric in the Components user guide.
* **Regra VISTA:** Lógica personalizada criada pela Adobe a pedido de um cliente para copiar, analisar ou filtrar dados do lado do servidor. Normalmente, as regras VISTA acarretam custos adicionais. Consulte também Regras de processamento.
* **Web beacon:** consulte Solicitação de imagem.
