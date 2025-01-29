---
description: Uma visão geral de como usar modelos no Analysis Workspace.
title: Usar modelos
feature: Analysis Workspace
role: User, Admin
exl-id: 9e5d1b35-e2b3-4fa5-af12-67bb913675bc
source-git-commit: dc1744cf4816971d52364a3131a12601787d9819
workflow-type: tm+mt
source-wordcount: '18673'
ht-degree: 83%

---

# Usar modelos

Os modelos (ou modelos de empresa) no Analysis Workspace fornecem insights rápidos sobre os cenários de relatórios mais comuns. A seguir estão alguns exemplos de perguntas que você pode responder com modelos:

* Quantas pessoas visitam o seu site
* Quantos desses visitantes são visitantes únicos (contados somente uma vez)
* Como eles chegaram até o site (se os visitantes seguiram um link ou chegaram diretamente ao site)
* Quais palavras-chave os visitantes usaram para pesquisar pelo conteúdo do site
* Por quanto tempo os visitantes permaneceram em uma página específica ou no site
* Em quais links o visitante clicou e quando ele deixou o site
* Quais canais de marketing são os mais eficazes na geração de receita ou eventos de conversão
* Quanto tempo foi utilizado ao assistir a um vídeo
* Quais navegadores e dispositivos eles utilizaram para visitar seu site

As informações a seguir descrevem como acessar e usar modelos na guia [!UICONTROL Modelos] do Analysis Workspace.

## Acessar e executar um modelo

1. No Adobe Analytics, selecione a guia [!UICONTROL **Espaço de trabalho**].

   <!--update screenshot -->

   ![Guia Relatórios](assets/view-prebuilt-templates.png)

1. Na seção [!UICONTROL **Modelos**], selecione uma das guias a seguir:

   * **[!UICONTROL modelos de Adobe]**: mostra todos os modelos fornecidos pelo Adobe.

   * **[!UICONTROL _login_company_name _modelos]**: mostra todos os modelos de empresa que foram criados para sua organização.

     Somente administradores podem criar modelos de empresa. Para obter mais informações sobre como criar um modelo de empresa, consulte [Criar e gerenciar modelos](/help/analyze/analysis-workspace/reports/create-company-reports.md).

1. Use uma das opções a seguir para alterar a exibição dos modelos disponíveis:

   * Escolha se deseja exibir modelos em uma exibição de coluna ou em uma exibição de cartão selecionando o ícone exibição de coluna ![ícone de exibição de coluna](assets/column-view-icon.png) ou o ícone de exibição de cartão ![ícone de exibição de cartão](assets/card-view-icon.png).

   * Ao usar o ![ícone de exibição de cartão](assets/card-view-icon.png), escolha entre as seguintes ordens de classificação: **[!UICONTROL Mais usadas recentemente]**, **[!UICONTROL Mais populares]**, **[!UICONTROL Alfabética]**, **[!UICONTROL Categórica]**.

1. No campo de pesquisa, comece digitando o nome do template que deseja localizar, em seguida, selecione-o na lista de templates. Também é possível pesquisar a lista de modelos por propriedade, eVar e número do evento. <!-- still true? -->

   Ou

   Selecione a categoria do modelo que deseja exibir e selecione o modelo na lista de modelos.

   >[!TIP]
   >
   >Para navegar no menu utilizando as teclas de seta, pressione a tecla Barra (/) e, em seguida, pressione a tecla Seta para baixo. Pressione Enter para carregar o modelo selecionado.

   Para obter uma lista de modelos disponíveis, consulte a seção [Modelos disponíveis](#available-reports) abaixo.

## Criar um projeto com base em um modelo {#use-reports}

Um modelo pode não atender exatamente às suas necessidades, mas pode fazê-lo se aproximar. Nesses casos, você pode usar o modelo como ponto de partida e personalizá-lo para atender melhor às suas finalidades específicas.

Se você sair de um modelo depois de fazer alterações, será solicitado a salvar ou descartar as alterações. Salvar as alterações em um modelo salva o modelo como um novo projeto.

Para personalizar um modelo e salvá-lo como um projeto:

1. No Adobe Analytics, selecione a guia [!UICONTROL **Espaço de Trabalho**].

1. Selecione a guia [!UICONTROL **Modelos**].

1. Selecione o modelo que deseja exibir. Por exemplo, em [!UICONTROL **Mais popular**], selecione o modelo [!UICONTROL **Páginas**].

   ![Relatório de páginas](assets/pages-report.png)

1. O modelo Páginas, conforme exibido no Analysis Workspace, mostra duas [visualizações](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) ([Gráfico de barras](/help/analyze/analysis-workspace/visualizations/bar.md) e [Número do resumo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)) e uma [Tabela de forma livre](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md). A métrica usada é Ocorrências.
1. Siga um destes procedimentos:

   * Visualize o modelo.
   * Arraste um ou mais segmentos para a zona de destino Segmentos na parte superior. Por exemplo, arraste o segmento [!UICONTROL **Clientes móveis**] e veja os resultados.
   * Altere o intervalo de datas acessando o calendário no canto superior direito.
   * Adicione detalhamentos de dimensão, arraste outras métricas e, em geral, personalize o modelo para atender às suas necessidades.

1. (Opcional) Salve o modelo como um projeto selecionando [!UICONTROL **Projeto**] > [!UICONTROL **Salvar**].

   O modelo é salvo como um novo projeto; ele não modifica o modelo existente. Para obter mais informações sobre como salvar projetos, consulte [Salvar projetos](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md).

## Modelos disponíveis

Para acessar todos os modelos pré-criados disponíveis:

1. No Adobe Analytics, selecione a guia [!UICONTROL **Workspace**] e depois a guia [!UICONTROL **Modelos**].

   Os modelos pré-criados são organizados por categoria.

   <!--add screenshot-->

1. Selecione uma categoria para exibir os modelos contidos nela.

   As seções a seguir correspondem às categorias disponíveis e fornecem informações sobre cada modelo.

   * [[!UICONTROL ](#most-popular)

   * [[!UICONTROL ](#engagement)

### Mais popular {#most-popular}

<!--AA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--unitsOvertimeReport"
>title="Visualize o número total de unidades compradas em todos os pedidos. Os dados são mostrados durante um período e comparados com períodos anteriores."
>abstract="**Isso pode ajudar** a entender melhor como as vendas de unidades estão aumentando ou diminuindo com o tempo. Você pode aplicar um segmento para saber quais clientes ou regiões geográficas estão comprando a maior parte das unidades e quais são as tendências dessas vendas ao longo do tempo.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar a eficácia de uma campanha de marketing iniciada recentemente ao comparar as vendas de unidades antes e depois do início da campanha. É possível também comparar as vendas de unidades durante feriados a cada ano.<br/>Este modelo usa a dimensão “Dia” e a métrica “Unidades”."

<!-- markdownlint-enable MD034 -->

<!--both AA and CJA-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--training"
>title="Modelo do tutorial de treinamento"
>abstract="Saiba mais sobre a terminologia e as etapas comuns do Analysis Workspace para criar a sua primeira análise."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--pagesRankedReport"
>title="Identifique as páginas mais e menos populares."
>abstract="**Isso pode ajudar** a entender melhor o seu público-alvo e o tipo de informação em que estão mais interessados(as).<br/>**Com base no que aprender, você poderá** fazer várias coisas, como ajustar metadados para aumentar a visibilidade de páginas menos visualizadas ou aprimorar o conteúdo das suas páginas mais visualizadas.<br/>Este modelo usa a dimensão “Página” e a métrica “Exibições da página”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--pageViewsOvertimeReport"
>title="Veja o número total de exibições da página. Os dados são mostrados durante um período e comparados com períodos anteriores. "
>abstract="**Isso pode ajudar** a entender melhor como o tráfego no site pode estar aumentando ou diminuindo com o tempo.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar a eficácia de uma campanha de marketing iniciada recentemente por comparar o tráfego do site antes e depois do início da campanha. Ou você pode comparar o tráfego em feriados de ano a ano.<br/>Este modelo usa a dimensão “Dia” e a métrica “Exibições da página”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--visitsOvertimeReport"
>title="Veja o número total de visitas. Os dados são mostrados durante um período e comparados com períodos anteriores."
>abstract="**Isso pode ajudar** a entender melhor como o tráfego no site pode estar aumentando ou diminuindo com o tempo.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar a eficácia de uma campanha de marketing iniciada recentemente por comparar o tráfego do site antes e depois do início da campanha. Ou você pode comparar o tráfego em feriados de ano a ano.<br/>Este modelo usa a dimensão “Dia” e a métrica “Visitas”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--visitorsOvertimeReport"
>title="Veja o número total de visitantes únicos. Os dados são mostrados durante um período e comparados com períodos anteriores. "
>abstract="**Isso pode ajudar** a entender melhor como o alcance e o tamanho do público-alvo do seu site estão aumentando ou diminuindo com o tempo ou em comparação com um período anterior.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar se uma campanha de marketing iniciada recentemente teve êxito ao atrair novas pessoas para o site, comparando o número de visitantes únicos antes e depois do início da campanha. Ou você pode comparar o número de pessoas que visitam o site durante os feriados a cada ano.<br/>Este modelo usa a dimensão “Dia” e a métrica “Visitantes únicos”. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--keyMetricsReport"
>title="Visualize um relatório que mostra as métricas de exibições da página, visitas e visitantes únicos lado a lado. Os dados são mostrados durante um período e comparados com períodos anteriores."
>abstract="**Isso pode ajudar** a comparar essas métricas importantes para obter uma visão mais completa do número de pessoas únicas que visitam o site, o número de vezes que as páginas foram visitadas e o número de sessões.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar o número médio de páginas que cada pessoa visualizou ao visitar o site em uma determinada semana ou mês, e como isso mudou durante certos períodos do ano ou antes e depois que as campanhas de marketing foram executadas. <br/>Este modelo usa a dimensão “Dia” e as métricas “Exibições da página”, “Visitas” e “Visitantes únicos”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--siteSectionRankedReport"
>title="Veja as seções mais populares ou de maior desempenho do seu site."
>abstract="**Isso pode ajudar** a entender melhor quais seções do site são mais visitadas.<br>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar quais produtos ou serviços fornecidos geram mais interesse.<br/>Este modelo usa a dimensão “Seção do site” e a métrica “Visitas”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--next-page-report"
>title="Veja os lugares mais comuns que as pessoas acessam imediatamente após a visita de uma determinada página."
>abstract="**Isso pode ajudar** a entender melhor o comportamento dos usuários após a visita de uma determinada página.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar se o design ou layout da página pode ser otimizado para direcionar as pessoas a páginas mais desejáveis, como uma página para fazer uma compra ou deixar uma avaliação.<br/>Este modelo usa a dimensão “Página” e a métrica “Eventos”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--previous-page-report"
>title="Veja os lugares mais comuns que as pessoas acessam imediatamente antes de visitar uma determinada página."
>abstract="**Isso pode ajudar** a entender melhor quais páginas direcionam mais tráfego para uma determinada página.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar se as páginas que não estão aparecendo como páginas anteriores precisam de links mais evidentes para a página atual."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--campaignRankedReport"
>title="Veja os links que obtiveram mais êxito em gerar tráfego para o seu site."
>abstract="**Isso pode ajudar** a entender melhor quais códigos de rastreamento (e os links aos quais estão associados) foram os mais usados para acessar o seu site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como ajustar a sua estratégia para adicionar links para o seu site.<br/>Este modelo usa a dimensão “Código de rastreamento” e a métrica “Visitas”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--productsRankedReport"
>title="Veja o número de pedidos por produto. Os dados representam um determinado período."
>abstract="**Isso pode ajudar** a entender quais produtos têm a maior ou menor demanda.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como ajustar as estratégias de marketing para promover produtos de alto desempenho ou para melhorar ou descontinuar produtos de baixo desempenho. Você também pode ajustar o inventário de produtos com base na análise dos dados.<br/>Este modelo usa a dimensão “Produto” e a métrica “Pedidos”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--lastTouchChannelRankedReport"
>title="Veja os canais de marketing mais recentes utilizados por visitantes durante o período de engajamento (30 dias por padrão)."
>abstract="**Isso pode ajudar** a entender quais canais de marketing foram mais eficazes para trazer pessoas ao site que resultou em conversões.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como alocar mais recursos a canais de alto desempenho ou reduzir a alocação de recursos para canais de baixo desempenho.<br/>Este modelo usa a dimensão “Canal de último contato” e a métrica “Visitantes únicos”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--lastTouchChannelDetailRankedReport"
>title="Veja os detalhes dos canais de marketing mais recentes utilizados por visitantes durante o período de engajamento (30 dias por padrão)."
>abstract="**Isso pode ajudar** a entender quais canais de marketing foram mais eficazes para trazer pessoas ao site que resultou em conversões, bem como os detalhes desses canais de marketing. Por exemplo, se um visitante chegasse ao seu site e correspondesse ao canal de marketing &quot;Pesquisa paga&quot;, você poderia usar os detalhes do canal para ver qual mecanismo de pesquisa foi usado ou qual palavra-chave foi pesquisada.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como alocar mais recursos a canais de alto desempenho ou reduzir a alocação de recursos para canais de baixo desempenho.<br/>Este modelo usa a dimensão “Detalhes do canal de último contato” e a métrica “Visitantes únicos”. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--revenueOvertimeReport"
>title="Veja o valor monetário de todos os produtos comprados em todos os pedidos. Os dados são mostrados durante um período e comparados com períodos anteriores."
>abstract="**Isso pode ajudar** a entender como a receita está aumentando ou diminuindo com o tempo. É possível combinar essa métrica com qualquer dimensão para saber quais itens de dimensão contribuíram para a receita.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como projetar a receita futura com base nas tendências anteriores. Também é possível adicionar outra dimensão, como a dimensão “Código de rastreamento”, para saber quais campanhas estão gerando mais receita.<br/>Este modelo usa a dimensão “Dia” e a métrica “Receita”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--ordersOvertimeReport"
>title="Veja o número total de eventos de compra. Os dados são mostrados durante um período e comparados com períodos anteriores."
>abstract="**Isso pode ajudar** a entender melhor como o interesse pelos seus produtos e serviços está aumentando ou diminuindo com o tempo. Você pode aplicar um segmento para saber quais clientes ou regiões geográficas estão fazendo mais pedidos, e quais são as tendências desses pedidos ao longo do tempo.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar a eficácia de uma campanha de marketing iniciada recentemente por comparar os pedidos antes e depois do início da campanha. Ou você pode comparar os pedidos feitos durante feriados a cada ano.<br/>Este modelo usa a dimensão “Dia” e a métrica “Pedidos”."

<!-- markdownlint-enable MD034 -->

Os seguintes modelos estão disponíveis:

| Nome do modelo | Por que usar este modelo <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Tutorial de treinamento**] | Saiba mais sobre a terminologia e as etapas comuns do Analysis Workspace para criar sua primeira análise |
| [!UICONTROL **Páginas**] | <!--duplicated in Engagement section--> Identifique as páginas mais e menos populares. <p>**Isso pode ajudar** a entender melhor o seu público-alvo e o tipo de informação em que estão mais interessados(as).</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como ajustar os metadados da página para aumentar a visibilidade em páginas menos visualizadas, ou gastar tempo melhorando o conteúdo de suas páginas mais visualizadas.</p><p>Este modelo usa a [dimensão de Página](/help/components/dimensions/page.md) e a [métrica de Exibições de Página](/help/components/metrics/page-views.md).</p> |
| [!UICONTROL **Exibições de página**] | <!--duplicated in Engagement section--> Veja o número total de exibições da página. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudar** a entender melhor como o tráfego no site pode estar aumentando ou diminuindo com o tempo.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar a eficácia de uma campanha de marketing iniciada recentemente por comparar o tráfego do site antes e depois do início da campanha. Ou você pode comparar o tráfego em feriados de ano a ano.</p><p>Este modelo usa a [dimensão de Dia](/help/components/dimensions/day.md) e a [métrica de Exibições de Página](/help/components/metrics/page-views.md).</p> |
| [!UICONTROL **Visitas**] | <!--duplicated in Engagement section--> Veja o número total de visitas. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudar** a entender melhor como o tráfego no site pode estar aumentando ou diminuindo com o tempo.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar a eficácia de uma campanha de marketing iniciada recentemente por comparar o tráfego do site antes e depois do início da campanha. Ou você pode comparar o tráfego em feriados de ano a ano.</p><p>Este modelo usa a [dimensão Dia](/help/components/dimensions/day.md) e a [métrica Visitas](/help/components/metrics/visits.md).</p> |
| [!UICONTROL **Visitantes**] | <!--duplicated in Engagement section--> Veja o número total de visitantes únicos. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudar** a entender melhor como o alcance e o tamanho do público-alvo do seu site estão aumentando ou diminuindo com o tempo ou em comparação com um período anterior.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar se uma campanha de marketing iniciada recentemente teve êxito ao atrair novas pessoas para o site, comparando o número de visitantes únicos antes e depois do início da campanha. Ou você pode comparar o número de pessoas que visitam o site durante os feriados a cada ano.</p><p>Este modelo usa a [dimensão Dia](/help/components/dimensions/day.md) e a [métrica Visitantes únicos](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Métricas principais**] | <!--duplicated in Engagement section--> Visualize um relatório que mostra as métricas de exibições da página, visitas e visitantes únicos lado a lado. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudar** a comparar essas métricas importantes para obter uma visão mais completa do número de pessoas únicas que visitam o site, o número de vezes que as páginas foram visitadas e o número de sessões.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como avaliar o número médio de páginas que cada pessoa visualizou ao visitar o site em uma determinada semana ou mês e como isso mudou durante certos períodos do ano ou antes e depois que as campanhas de marketing foram executadas. </p><p>Este modelo usa a [dimensão Dia](/help/components/dimensions/day.md), a [métrica Exibições da página](/help/components/metrics/page-views.md), a [métrica Visitas](/help/components/metrics/visits.md) e a [métrica Visitantes únicos](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Seções do site**] | Veja as seções mais populares ou de maior desempenho do seu site. <p>**Isso pode ajudar** a entender melhor quais seções do site são mais visitadas.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar quais produtos ou serviços fornecidos geram mais interesse.</p> <p>Este modelo usa a [dimensão Seção do site](/help/components/dimensions/site-section.md) e a [métrica Visitas](/help/components/metrics/visits.md).</p> |
| [!UICONTROL **Código de rastreamento**] | Veja os links que obtiveram mais êxito em gerar tráfego para o seu site. <p>**Isso pode ajudar** a entender melhor quais códigos de rastreamento (e os links aos quais estão associados) foram os mais usados para acessar o seu site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como ajustar a sua estratégia para adicionar links para o seu site.</p><p>Este modelo usa a [dimensão Código de rastreamento](/help/components/dimensions/tracking-code.md) e a [métrica Visitas](/help/components/metrics/visits.md).</p> |
| [!UICONTROL **Próxima página**] | Veja os lugares mais comuns que as pessoas acessam imediatamente após a visita de uma determinada página. <p>**Isso pode ajudar** a entender melhor o comportamento dos usuários após a visita de uma determinada página.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar se o design ou layout da página pode ser otimizado para direcionar as pessoas a páginas mais desejáveis, como uma página para fazer uma compra ou deixar uma avaliação.</p> <p>Esse modelo usa a dimensão Página e a métrica Eventos.</p> |
| [!UICONTROL **Página anterior**] | Veja os lugares mais comuns que as pessoas acessam imediatamente antes de visitar uma determinada página. <p>**Isso pode ajudar** a entender melhor quais páginas direcionam mais tráfego para uma determinada página.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar se as páginas que não estão aparecendo como páginas anteriores precisam de links mais evidentes para a página atual.</p><p>Esse modelo usa a dimensão Página e a métrica Eventos.</p> |
| [!UICONTROL **Produtos**] | Veja o número de pedidos por produto. Os dados representam um determinado período. <p>**Isso pode ajudar** a entender quais produtos têm a maior ou menor demanda.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como ajustar as estratégias de marketing para promover produtos de alto desempenho ou para melhorar ou descontinuar produtos de baixo desempenho. Você também pode ajustar o inventário de produtos com base na análise dos dados.</p><p>Este modelo usa a [dimensão de Produto](/help/components/dimensions/product.md) e a [métrica Pedidos](/help/components/metrics/orders.md).</p> |
| [!UICONTROL **Canal de último contato**] | Veja os canais de marketing mais recentes utilizados por visitantes durante o período de engajamento (30 dias por padrão).<p>**Isso pode ajudar** a entender quais canais de marketing foram mais eficazes para trazer pessoas ao site que resultou em conversões.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como alocar mais recursos a canais de alto desempenho ou reduzir a alocação de recursos para canais de baixo desempenho.</p><p>Este modelo usa a [dimensão Canal de último contato](/help/components/dimensions/last-touch-channel.md) e a [métrica Visitantes únicos](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Detalhes do canal de último contato**] | Veja os detalhes dos canais de marketing mais recentes utilizados por visitantes durante o período de engajamento (30 dias por padrão).<p>**Isso pode ajudar** a entender quais canais de marketing foram mais eficazes para trazer pessoas ao site que resultou em conversões, bem como os detalhes desses canais de marketing. Por exemplo, se um visitante chegasse ao seu site e correspondesse ao canal de marketing &quot;Pesquisa paga&quot;, você poderia usar os detalhes do canal para ver qual mecanismo de pesquisa foi usado ou qual palavra-chave foi pesquisada.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como alocar mais recursos a canais de alto desempenho ou reduzir a alocação de recursos para canais de baixo desempenho.</p><p>Este modelo usa a [dimensão Detalhe do canal de último contato](/help/components/dimensions/last-touch-detail.md) e a [métrica Visitantes únicos](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Receita**] | Veja o valor monetário de todos os produtos comprados em todos os pedidos. Os dados são mostrados durante um período e comparados com períodos anteriores.<p>**Isso pode ajudar** a entender como a receita está aumentando ou diminuindo com o tempo. É possível combinar essa métrica com qualquer dimensão para saber quais itens de dimensão contribuíram para a receita.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como projetar a receita futura com base nas tendências anteriores. Também é possível adicionar outra dimensão, como a dimensão “Código de rastreamento”, para saber quais campanhas estão gerando mais receita.</p><p>Este modelo usa a [dimensão de Dia](/help/components/dimensions/day.md) e a [métrica de Receita](/help/components/metrics/revenue.md).</p> |
| [!UICONTROL **Pedidos**] | Veja o número total de eventos de compra. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudar** a entender melhor como o interesse pelos seus produtos e serviços está aumentando ou diminuindo com o tempo. Você pode aplicar um segmento para saber quais clientes ou regiões geográficas estão fazendo mais pedidos, e quais são as tendências desses pedidos ao longo do tempo.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar a eficácia de uma campanha de marketing iniciada recentemente por comparar os pedidos antes e depois do início da campanha. Ou você pode comparar os pedidos feitos durante feriados a cada ano.</p><p>Este modelo usa a [dimensão Dia](/help/components/dimensions/day.md) e a [métrica Pedidos](/help/components/metrics/orders.md).</p> |
| [!UICONTROL **Unidades**] | Visualize o número total de unidades compradas em todos os pedidos. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudar** a entender melhor como as vendas de unidades estão aumentando ou diminuindo com o tempo. Você pode aplicar um segmento para saber quais clientes ou regiões geográficas estão comprando a maior parte das unidades e quais são as tendências dessas vendas ao longo do tempo.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar a eficácia de uma campanha de marketing iniciada recentemente ao comparar as vendas de unidades antes e depois do início da campanha. É possível também comparar as vendas de unidades durante feriados a cada ano.</p><p>Este modelo usa a [dimensão de Dia](/help/components/dimensions/day.md) e a [métrica de Unidades](/help/components/metrics/units.md).</p> |

### Engajamento {#web-engagement}

<!--AA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--real-time"
>title="Visualize as dimensões e métricas que estão sendo coletadas no site."
>abstract="**Isso pode ajudar** a entender melhor as tendências do site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como responder ao desempenho do conteúdo e das campanhas de marketing atuais e gerenciá-lo ativamente."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timeSpentVisitOvertimeReport"
>title="Visualize o tempo médio que os visitantes gastam no site durante cada visita. Os dados são mostrados durante um período e comparados com períodos anteriores."
>abstract="**Isso pode ajudar** a entender melhor os níveis de engajamento dos visitantes e quanto tempo estão gastando no site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar se as alterações no site resultam em visitantes permanecendo por mais tempo.<br/>Este modelo usa a dimensão &quot;Dia&quot; e a métrica &quot;Tempo gasto por visita&quot; (segundos)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timePriorRankedReport"
>title="Visualize o tempo médio que os usuários gastam antes de um evento bem-sucedido."
>abstract="**Isso pode ajudar** a entender melhor quanto tempo leva para que os visitantes realizem uma ação desejada, como fazer uma compra.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar se as alterações no site melhoram a possibilidade dos visitantes gerarem rapidamente um evento bem-sucedido.<br/>Este modelo usa a dimensão &quot;Tempo anterior ao evento&quot; e a métrica “Visitantes únicos”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--falloutReport"
>title="Visualize onde as pessoas saem ou continuam por uma sequência predefinida de páginas."
>abstract="**Isso pode ajudar** a entender melhor de onde as pessoas estão saindo da jornada do usuário.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como analisar taxas de conversão por meio de processos específicos no site (como um processo de compra ou registro) ou analisar correlações entre eventos no site. (Por exemplo, que porcentagem das pessoas que observaram sua política de privacidade compraram um produto.) Você também pode usar esse modelo para fazer comparações lado a lado de dois segmentos diferentes no mesmo relatório.<br/>Este modelo usa a visualização de fallout."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--cross-device-analysis"
>title="Visualize quais dispositivos as pessoas usaram em todos os pontos da jornada."
>abstract="**Isso pode ajudar** a entender melhor quantas pessoas interagem com a sua marca, os tipos de dispositivos que usam e como o uso dos vários dispositivos afeta a experiência. Por exemplo, com que frequência as pessoas iniciam uma tarefa em um dispositivo móvel e depois vão para o desktop para concluí-la? Quais são os caminhos mais comuns que os usuários fazem de um dispositivo para outro? Onde eles desistem? Onde são bem-sucedidas? E assim por diante.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como otimizar certas partes da jornada do usuário para uma experiência móvel.<br/>Este modelo usa a Visualização de fluxo, a Visualização de fallout, a Análise de coorte, a métrica &quot;Pessoas&quot; e a métrica &quot;Dispositivos exclusivos&quot;."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--web-retention"
>title="Visualize quem são seus usuários fiéis e o que estão fazendo no site."
>abstract="**Isso pode ajudar** a entender melhor a quantidade de vezes que a pessoa média visita o site, a frequência com que retorna e o número de dias entre visitas recorrentes.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como analisar qual conteúdo é mais eficaz em trazer pessoas de volta ao site.<br/>Este modelo usa a métrica &quot;Visitas&quot; e a métrica &quot;Visitantes únicos&quot;."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--audio-consumption-template"
>title="Veja as tendências e as principais métricas de consumo de mídia de áudio em todos os dispositivos digitais."
>abstract="**Isso pode ajudar** a entender melhor como visitantes estão consumindo conteúdo de áudio no site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como analisar qual conteúdo é mais consumido.<br/>Este modelo usa a métrica &quot;Visitas&quot; e a métrica &quot;Visitantes únicos&quot;."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--media-recency-frequency-loyalty"
>title="Veja as tendências e as principais métricas de consumo de mídia em todos os dispositivos digitais."
>abstract="**Isso pode ajudar** a entender melhor a quantidade de vezes que a pessoa média visita o site, a frequência com que retorna e o número de dias entre visitas recorrentes.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como analisar qual conteúdo é mais eficaz em trazer pessoas de volta ao site.<br/>Este modelo usa a métrica &quot;Visitas&quot; e a métrica &quot;Visitantes únicos&quot;."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--reloadsRankedReport"
>title="Visualize o número de vezes que um item de dimensão estava presente durante um recarregamento. A atualização do navegador por um visitante é a maneira mais comum de acionar um recarregamento."
>abstract="**Isso pode ajudar** a identificar em que momento podem estar ocorrendo problemas em uma determinada página que resultariam no recarregamento desta por visitantes.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar quais páginas têm problemas que precisam ser resolvidos.<br/>Este modelo usa a métrica “Recarregamentos”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timeSpentPageRankedReport"
>title="Visualize o tempo médio que os visitantes gastam no site durante cada visita. Os dados são mostrados durante um período e comparados com períodos anteriores."
>abstract="**Isso pode ajudar** a entender melhor os níveis de engajamento dos visitantes e quanto tempo estão gastando no site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar se as alterações no site resultam em visitantes permanecendo por mais tempo.<br/>Este modelo usa a dimensão &quot;Dia&quot; e a métrica &quot;Tempo gasto por visita&quot; (segundos)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--entryPageOriginalRankedReport"
>title="Veja as principais páginas que as pessoas acessam quando visitam o site pela primeira vez durante o tempo de vida de visitante."
>abstract="**Isso pode ajudar** a saber quais páginas estão gerando mais tráfego para o site ou entender melhor as primeiras impressões que visitantes têm sobre o site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como otimizar a experiência inicial que as pessoas têm no site ou garantir que as páginas que as pessoas veem ao entrar no site sejam acolhedoras e forneçam os links necessários para outras áreas do site.<br/>Este modelo usa a métrica “Sessões”. Ele também usa a visualização de barras e a visualização de tabela de forma livre."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--singlePageVisitsRankedReport"
>title="Visualize o número de visitas que consistiram em uma única página."
>abstract="**Isso pode ajudar** a entender melhor os níveis de engajamento dos visitantes e quanto tempo estão gastando no site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar se as alterações no site resultam em visitantes permanecendo por mais tempo.<br/>Este modelo usa a dimensão &quot;Visitas de página única&quot;."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--sitePerformanceOverview"
>title="Visualizar dados de desempenho do site do Adobe Experience Manager."
>abstract="**Isso pode ajudar** a entender melhor a realização de valores do Adobe Experience Manager.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como otimizar as configurações do Experience Manager."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--formsPerformanceOverview"
>title="Visualize dados de desempenho do Adobe Experience Manager Forms."
>abstract="**Isso pode ajudar** a entender melhor a realização de valores do Adobe Experience Manager.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como otimizar as configurações do Experience Manager."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--itp-impact"
>title="Visualize e analise os efeitos da Prevenção de Rastreamento Inteligente (ITP) na coleta de dados e nos relatórios."
>abstract="**Isso pode ajudar** a entender melhor a possível perda de dados devido a restrições de cookies impostas pela ITP.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como adaptar a configuração de análise para minimizar o impacto da ITP."

<!-- markdownlint-enable MD034 -->

<!--Both AA and CJA-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template_time_spent"
>title="Veja o tempo médio que os visitantes gastam no site durante cada visita, bem como o tempo médio que os usuários gastam na visita até gerar um evento bem-sucedido. Os dados são mostrados durante um período e comparados com períodos anteriores."
>abstract="**Isso pode ajudar** a entender melhor os níveis de engajamento dos visitantes e quanto tempo levam para executar a ação desejada, como fazer uma compra.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar se as alterações no site melhoram a possibilidade dos visitantes gerarem rapidamente um evento bem-sucedido.<br/>Este modelo usa a dimensão “Dia” e a métrica “Tempo gasto por visita (segundos)”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--web-content-consumption"
>title="Veja qual conteúdo da web é mais consumido e gera mais engajamento pelos usuários."
>abstract="**Isso pode ajudar** a entender melhor o que as pessoas acessam ao entrar pela primeira vez no site, quais seções do site são mais visitadas e quais páginas tendem a afastar as pessoas do site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar quais caminhos no site direcionam as pessoas às páginas mais importantes e quais páginas têm a maior probabilidade de afastá-las do site.<br/>Este modelo usa a dimensão “Página” e as métricas “Exibições da página”, “Visitas”, “Visitantes únicos”, “Taxa de entrada”, “Taxa de rejeição”, “Taxa de saída” e “Velocidade do conteúdo”. Ele também usa visualizações de fluxo para as seções de entrada, saída e a seção superior."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--media-content-consumption"
>title="Veja qual conteúdo de mídia é mais consumido e gera mais engajamento pelos usuários."
>abstract="**Isso pode ajudar** a entender melhor o que as pessoas acessam ao entrar pela primeira vez no site, quais seções do site são mais visitadas e quais páginas tendem a afastar as pessoas do site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar quais caminhos no site direcionam as pessoas às páginas mais importantes e quais páginas têm a maior probabilidade de afastá-las do site.<br/>Este modelo usa a dimensão “Página” e as métricas “Exibições da página”, “Visitas”, “Visitantes únicos”, “Taxa de entrada”, “Taxa de rejeição”, “Taxa de saída” e “Velocidade do conteúdo”. Ele também usa visualizações de fluxo para as seções de entrada, saída e a seção superior; uma visualização do gráfico de dispersão, que mostra as exibições das páginas mais comuns; uma visualização de barras, que mostra as exibições da página por tempo classificado; e uma visualização de linhas, que mostra uma exibição das tendências do tempo médio no site."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--flowreport"
>title="Veja os lugares mais comuns que as pessoas acessam imediatamente após ou antes de visitar um determinado lugar."
>abstract="**Isso pode ajudar** a entender como o tráfego passa de uma determinada página para outras partes do site e entender os caminhos que as pessoas percorrem para chegar a uma determinada página.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar se o design ou layout da página pode ser otimizado para direcionar as pessoas a páginas mais desejáveis, como uma página para fazer uma compra ou deixar uma avaliação. Ou avaliar se as informações na página atual fornecem a orientação ou as ações que as pessoas necessitam após acessarem as páginas anteriores. Ou você pode avaliar se as páginas que não aparecem como páginas anteriores precisam de links mais evidentes para a página atual.<br/>Este modelo usa o painel “Item seguinte ou anterior”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--page-summary-report"
>title="Veja as principais informações sobre qualquer página nas suas propriedades. Mostra as exibições da página, uma linha de tendências, uma visualização de fluxo e muito mais."
>abstract="**Isso pode ajudar** a entender melhor como as pessoas interagem com uma determinada página.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como analisar o desempenho da página durante um período ou entender melhor o que gera tráfego para a página.<br/>Este modelo usa a métrica “Exibições da página”. Ele também usa as visualizações de linhas e fluxo."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--entryPageRankedReport"
>title="Veja as principais páginas que as pessoas acessam quando visitam o site pela primeira vez."
>abstract="**Isso pode ajudar** a saber quais páginas estão gerando mais tráfego para o site ou entender melhor as primeiras impressões que visitantes têm sobre o site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como otimizar a experiência inicial que as pessoas têm no site ou garantir que as páginas que as pessoas veem ao entrar no site sejam acolhedoras e forneçam os links necessários para outras áreas do site.<br/>Este modelo usa a métrica “Sessões”. Ele também usa a visualização de barras e a visualização de tabela de forma livre."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--exitPageRankedReport"
>title="Veja as principais páginas que as pessoas acessam imediatamente antes de sair do site."
>abstract="**Isso pode ajudar** a entender melhor quais páginas estão afastando as pessoas do site. <br/>**Com base no que aprender, você poderá** fazer várias coisas, como atualizar as páginas de saída comuns para otimizar a experiência que as pessoas têm antes de sair ou incluir conteúdo ou links para incentivar as pessoas a permanecerem no site.<br/>Este modelo usa a métrica “Sessões”. Ele também usa a visualização de barras e a visualização de tabela de forma livre."

<!-- markdownlint-enable MD034 -->

Os seguintes modelos estão disponíveis:

| Nome do modelo | Por que usar este modelo <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Métricas principais**] | <!--duplicated in Most popular section--> Visualize um relatório que mostra as métricas de exibições da página, visitas e visitantes únicos lado a lado. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudar** a comparar essas métricas importantes para obter uma visão mais completa do número de pessoas únicas que visitam o site, o número de vezes que as páginas foram visitadas e o número de sessões.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como avaliar o número médio de páginas que cada pessoa visualizou ao visitar o site em uma determinada semana ou mês e como isso mudou durante certos períodos do ano ou antes e depois que as campanhas de marketing foram executadas. </p><p>Este modelo usa a [dimensão Dia](/help/components/dimensions/day.md), a [métrica Exibições da página](/help/components/metrics/page-views.md), a [métrica Visitas](/help/components/metrics/visits.md) e a [métrica Visitantes únicos](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Exibições de página**] | <!--duplicated in Most popular section-->Veja o número total de exibições da página. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudar** a entender melhor como o tráfego no site pode estar aumentando ou diminuindo com o tempo.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar a eficácia de uma campanha de marketing iniciada recentemente por comparar o tráfego do site antes e depois do início da campanha. Ou você pode comparar o tráfego em feriados de ano a ano.</p><p>Este modelo usa a [dimensão de Dia](/help/components/dimensions/day.md) e a [métrica de Exibições de Página](/help/components/metrics/page-views.md).</p> |
| [!UICONTROL **Páginas**] | <!--duplicated in Most popular section-->Identifique as páginas mais e menos populares. <p>**Isso pode ajudar** a entender melhor o seu público-alvo e o tipo de informação em que estão mais interessados(as).</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como ajustar os metadados da página para aumentar a visibilidade em páginas menos visualizadas, ou gastar tempo melhorando o conteúdo de suas páginas mais visualizadas.</p><p>Este modelo usa a [dimensão de Página](/help/components/dimensions/page.md) e a [métrica de Exibições de Página](/help/components/metrics/page-views.md).</p> |
| [!UICONTROL **Visitas**] | <!--duplicated in Most popular section-->Veja o número total de visitas. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudar** a entender melhor como o tráfego no site pode estar aumentando ou diminuindo com o tempo.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar a eficácia de uma campanha de marketing iniciada recentemente por comparar o tráfego do site antes e depois do início da campanha. Ou você pode comparar o tráfego em feriados de ano a ano.</p><p>Este modelo usa a [dimensão Dia](/help/components/dimensions/day.md) e a [métrica Visitas](/help/components/metrics/visits.md).</p> |
| [!UICONTROL **Visitantes**] | <!--duplicated in Most popular section-->Veja o número total de visitantes únicos. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudar** a entender melhor como o alcance e o tamanho do público-alvo do seu site estão aumentando ou diminuindo com o tempo ou em comparação com um período anterior.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar se uma campanha de marketing iniciada recentemente teve êxito ao atrair novas pessoas para o site, comparando o número de visitantes únicos antes e depois do início da campanha. Ou você pode comparar o número de pessoas que visitam o site durante os feriados a cada ano.</p><p>Este modelo usa a [dimensão Dia](/help/components/dimensions/day.md) e a [métrica Visitantes únicos](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Tempo gasto por visita**] | Visualize o tempo médio que os visitantes gastam no site durante cada visita. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudar** a entender melhor os níveis de engajamento dos visitantes e quanto tempo estão gastando no site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar se as alterações no site resultam em visitantes permanecendo por mais tempo.</p><p>Este modelo usa a [dimensão de Dia](/help/components/dimensions/day.md) e a [métrica Tempo gasto por visita (segundos)](/help/components/metrics/time-spent-per-visit.md).</p> |
| [!UICONTROL **Tempo antes do evento**] | Visualize o tempo médio que os usuários gastam antes de um evento bem-sucedido. <p>**Isso pode ajudar** a entender melhor quanto tempo leva para que os visitantes realizem uma ação desejada, como fazer uma compra.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar se as alterações no site melhoram a possibilidade dos visitantes gerarem rapidamente um evento bem-sucedido.</p><p>Este modelo usa a [dimensão Tempo antes do evento](/help/components/dimensions/time-prior-to-event.md) e a [métrica Visitantes únicos](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Seções do site**] | <!--duplicated in Most popular section-->Veja as seções mais populares ou de maior desempenho do seu site. <p>**Isso pode ajudar** a entender melhor quais seções do site são mais visitadas.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar quais produtos ou serviços fornecidos geram mais interesse.</p> <p>Este modelo usa a [dimensão Seção do site](/help/components/dimensions/site-section.md) e a [métrica Visitas](/help/components/metrics/visits.md).</p> |
| [!UICONTROL **Tempo real**] | Visualize as dimensões e métricas que estão sendo coletadas no site. <p>**Isso pode ajudar** a entender melhor as tendências do site.</p><p>**Com base no que você aprendeu, talvez** você responda e gerencie ativamente o desempenho de suas campanhas e conteúdo de marketing atuais.</p> <p>Este modelo usa o [Relatório em tempo real](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md).</p> |
| [!UICONTROL **Consumo de conteúdo da Web**] | Veja qual conteúdo da web é mais consumido e gera mais engajamento pelos usuários.<p>**Isso pode ajudar** a entender melhor o que as pessoas acessam ao entrar pela primeira vez no site, quais seções do site são mais visitadas e quais páginas tendem a afastar as pessoas do site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar quais caminhos no site direcionam as pessoas às páginas mais importantes e quais páginas têm a maior probabilidade de afastá-las do site.</p> <p>Este modelo usa a [dimensão da Página](/help/components/dimensions/page.md) e a [métrica de Exibições da Página](/help/components/metrics/page-views.md), a [métrica de Visitas](/help/components/metrics/visits.md), a [métrica de Visitantes Únicos](/help/components/metrics/unique-visitors.md), a [métrica de Taxa de Entrada](/help/components/metrics/entries.md), a [métrica de Taxa de Devolução](/help/components/metrics/bounce-rate.md), a [métrica de Taxa de Saída](/help/components/metrics/exits.md) e a [métrica de Velocidade do Conteúdo](/help/components/metrics/content-velocity.md). Também usa [Visualizações de fluxo](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) para seções de entrada, saída e superior.</p> |
| [!UICONTROL **Consumo de conteúdo de mídia**] | Veja qual conteúdo de mídia é mais consumido e gera mais engajamento pelos usuários.<p>**Isso pode ajudar** a entender melhor o que as pessoas acessam ao entrar pela primeira vez no site, quais seções do site são mais visitadas e quais páginas tendem a afastar as pessoas do site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar quais caminhos no site direcionam as pessoas às páginas mais importantes e quais páginas têm a maior probabilidade de afastá-las do site.</p> <p>Este modelo usa a [dimensão da Página](/help/components/dimensions/page.md) e a [métrica de Exibições da Página](/help/components/metrics/page-views.md), a [métrica de Visitas](/help/components/metrics/visits.md), a [métrica de Visitantes Únicos](/help/components/metrics/unique-visitors.md), a [métrica de Taxa de Entrada](/help/components/metrics/entries.md), a [métrica de Taxa de Devolução](/help/components/metrics/bounce-rate.md), a [métrica de Taxa de Saída](/help/components/metrics/exits.md) e a [métrica de Velocidade do Conteúdo](/help/components/metrics/content-velocity.md). Ele também usa [Visualizações de fluxo](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) para seções de entrada, saída e superior; uma [Visualização de gráfico de barras](/help/analyze/analysis-workspace/visualizations/scatterplot.md) que mostra exibições de página para as páginas mais comuns; uma [Visualização de barras](/help/analyze/analysis-workspace/visualizations/bar.md) que mostra exibições de página por tempo reduzido; e uma [Visualização de linhas](/help/analyze/analysis-workspace/visualizations/line.md) que mostra uma exibição de tendência do tempo médio gasto no site.</p> |
| [!UICONTROL **Fluxo da página seguinte e anterior**] | Veja os lugares mais comuns que as pessoas visitam antes ou depois de visitar um determinado lugar.<p>**Isso pode ajudá-lo** a entender melhor onde as pessoas entram pela primeira vez no site, quais seções das pessoas estão mais visitando e quais páginas têm maior probabilidade de visitar antes de sair do site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar quais caminhos no site direcionam as pessoas às páginas mais importantes e quais páginas têm a maior probabilidade de afastá-las do site.</p> <p>Este modelo usa a [dimensão da Página](/help/components/dimensions/page.md) e a [métrica de Exibições da Página](/help/components/metrics/page-views.md), a [métrica de Visitas](/help/components/metrics/visits.md), a [métrica de Visitantes Únicos](/help/components/metrics/unique-visitors.md), a [métrica de Taxa de Entrada](/help/components/metrics/entries.md), a [métrica de Taxa de Devolução](/help/components/metrics/bounce-rate.md), a [métrica de Taxa de Saída](/help/components/metrics/exits.md) e a [métrica de Velocidade do Conteúdo](/help/components/metrics/content-velocity.md). Ele também usa [Visualizações de fluxo](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) para seções de entrada, saída e superior; uma [Visualização de gráfico de dispersão](/help/analyze/analysis-workspace/visualizations/scatterplot.md) que mostra exibições de página para as páginas mais comuns; uma [Visualização de barra](/help/analyze/analysis-workspace/visualizations/bar.md) que mostra exibições de página por tempo reduzido; e uma [Visualização de linha](/help/analyze/analysis-workspace/visualizations/line.md) que mostra uma exibição de tendência do tempo médio gasto no site.</p> |
| [!UICONTROL **Fallout**] | Visualize onde as pessoas saem ou continuam por uma sequência predefinida de páginas.<p>**Isso pode ajudar** a entender melhor de onde as pessoas estão saindo da jornada do usuário.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como analisar taxas de conversão por meio de processos específicos no site (como um processo de compra ou registro) ou analisar correlações entre eventos no site. (Por exemplo, que porcentagem das pessoas que observaram sua política de privacidade compraram um produto.) Você também pode usar esse modelo para fazer comparações lado a lado de dois segmentos diferentes no mesmo relatório.</p> <p>Este modelo usa a [Visualização de fallout](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md).</p> |
| [!UICONTROL **Análise entre dispositivos**] | Visualize quais dispositivos as pessoas usaram em todos os pontos da jornada.<p>**Isso pode ajudar** a entender melhor quantas pessoas interagem com a sua marca, os tipos de dispositivos que usam e como o uso dos vários dispositivos afeta a experiência. Por exemplo, com que frequência as pessoas iniciam uma tarefa em um dispositivo móvel e depois vão para o desktop para concluí-la? Quais são os caminhos mais comuns que os usuários fazem de um dispositivo para outro? Onde eles desistem? Onde são bem-sucedidas? E assim por diante.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como otimizar certas partes da jornada do usuário para uma experiência móvel.</p> <p>Este modelo usa a [Visualização de fluxo](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md), [Visualização de fallout](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md), [Análise de coorte](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md), [a métrica de Pessoas](/help/components/metrics/people.md) e [a métrica Dispositivos exclusivos](/help/components/metrics/unique-devices.md).</p> |
| [!UICONTROL **Retenção da Web**] | Visualize quem são seus usuários fiéis e o que estão fazendo no site.<p>**Isso pode ajudar** a entender melhor a quantidade de vezes que a pessoa média visita o site, a frequência com que retorna e o número de dias entre visitas recorrentes.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como analisar qual conteúdo é mais eficaz em trazer pessoas de volta ao site.<p>Este modelo usa a [métrica Visitas](/help/components/metrics/visits.md) e a [métrica Visitantes únicos](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Consumo de streaming de mídia**] | Veja as tendências e as principais métricas de consumo de mídia de áudio em todos os dispositivos digitais.<p>**Isso pode ajudar** a entender melhor como visitantes estão consumindo conteúdo de áudio no site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como analisar qual conteúdo é mais consumido.<p>Este modelo usa a [métrica Visitas](/help/components/metrics/visits.md) e a [métrica Visitantes únicos](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Recenticidade, frequência, fidelidade de mídia**] | Veja as tendências e as principais métricas de consumo de mídia em todos os dispositivos digitais.<p>**Isso pode ajudar** a entender melhor a quantidade de vezes que a pessoa média visita o site, a frequência com que retorna e o número de dias entre visitas recorrentes.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como analisar qual conteúdo é mais eficaz em trazer pessoas de volta ao site.<p>Este modelo usa a [métrica Visitas](/help/components/metrics/visits.md) e a [métrica Visitantes únicos](/help/components/metrics/unique-visitors.md).</p> |
| **[!UICONTROL Análise de página]** > [!UICONTROL **Resumo da página**] | Visualize o tempo médio que os visitantes gastam no site durante cada visita. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudar** a entender melhor os níveis de engajamento dos visitantes e quanto tempo estão gastando no site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar se as alterações no site resultam em visitantes permanecendo por mais tempo.</p><p>Este modelo usa a [dimensão de Dia](/help/components/dimensions/day.md) e a [métrica Tempo gasto por visita (segundos)](/help/components/metrics/time-spent-per-visit.md).</p> |
| **[!UICONTROL Análise de página]** > [!UICONTROL **Recargas**] | Visualize o número de vezes que um item de dimensão estava presente durante um recarregamento. A atualização do navegador por um visitante é a maneira mais comum de acionar um recarregamento. <p>**Isso pode ajudar** a identificar em que momento podem estar ocorrendo problemas em uma determinada página que resultariam no recarregamento desta por visitantes.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar quais páginas têm problemas que precisam ser resolvidos.</p><p>Este modelo usa a [métrica Recargas](https://experienceleague.adobe.com/en/docs/analytics/components/metrics/reloads).</p> |
| **[!UICONTROL Análise de página]** > [!UICONTROL **Tempo gasto na página**] | Visualize o tempo médio que os visitantes gastam no site durante cada visita. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudar** a entender melhor os níveis de engajamento dos visitantes e quanto tempo estão gastando no site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar se as alterações no site resultam em visitantes permanecendo por mais tempo.</p><p>Este modelo usa a [dimensão de Dia](/help/components/dimensions/day.md) e a [métrica Tempo gasto por visita (segundos)](/help/components/metrics/time-spent-per-visit.md).</p> |
| **[!UICONTROL Entradas e saídas]** > [!UICONTROL **Páginas de entrada**] | Visualize as principais páginas que as pessoas acessam quando visitam o site pela primeira vez em uma determinada sessão. <p>**Isso pode ajudar** a saber quais páginas estão gerando mais tráfego para o site ou entender melhor as primeiras impressões que visitantes têm sobre o site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como otimizar a experiência inicial que as pessoas têm no site ou garantir que as páginas que as pessoas veem ao entrar no site sejam acolhedoras e forneçam os links necessários para outras áreas do site.</p><p>Este modelo usa a métrica Sessões. Ele também usa a visualização de barras e a visualização de tabela de forma livre.</p> |
| **[!UICONTROL Entradas e saídas]** > [!UICONTROL **Páginas de entrada originais**] | Veja as principais páginas que as pessoas acessam quando visitam o site pela primeira vez durante o tempo de vida de visitante. <p>**Isso pode ajudar** a saber quais páginas estão gerando mais tráfego para o site ou entender melhor as primeiras impressões que visitantes têm sobre o site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como otimizar a experiência inicial que as pessoas têm no site ou garantir que as páginas que as pessoas veem ao entrar no site sejam acolhedoras e forneçam os links necessários para outras áreas do site.</p><p>Este modelo usa a métrica Sessões. Ele também usa a visualização de barras e a visualização de tabela de forma livre.</p> |
| **[!UICONTROL Entradas e saídas]** > [!UICONTROL **Visitas em única página**] | Visualize o número de visitas que consistiram em uma única página. <p>**Isso pode ajudar** a entender melhor os níveis de engajamento dos visitantes e quanto tempo estão gastando no site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar se as alterações no site resultam em visitantes permanecendo por mais tempo.</p><p>Este modelo usa a [dimensão Visitas em única página](https://experienceleague.adobe.com/en/docs/analytics/components/dimensions/single-page-visits).</p> |
| **[!UICONTROL Entradas e saídas]** > [!UICONTROL **Páginas de saída**] | Veja as principais páginas que as pessoas acessam imediatamente antes de sair do site.<p>**Isso pode ajudá-lo** a entender melhor quais páginas estão afastando as pessoas do site. </p><p>**Com base no que aprender, você poderá** fazer várias coisas, como atualizar as páginas de saída comuns para otimizar a experiência que as pessoas têm antes de sair ou incluir conteúdo ou links para incentivar as pessoas a permanecerem no site.</p><p>Este modelo usa a métrica Sessões. Ele também usa a visualização de barras e a visualização de tabela de forma livre.</p> |
| [!UICONTROL **Adobe Experience Manager**] > [!UICONTROL **Visão geral do desempenho do site**] > [!UICONTROL **AEM desempenho do site**] | Visualizar dados de desempenho do site do Adobe Experience Manager.  <p>**Isso pode ajudar** a entender melhor a realização de valores do Adobe Experience Manager.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como otimizar as configurações do Experience Manager.</p> |
| [!UICONTROL **Adobe Experience Manager**] > [!UICONTROL **Visão geral do desempenho do formulário**] > [!UICONTROL **desempenho do formulário AEM**] | Visualize dados de desempenho do Adobe Experience Manager Forms.  <p>**Isso pode ajudar** a entender melhor a realização de valores do Adobe Experience Manager.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como otimizar as configurações do Experience Manager.</p> |
| [!UICONTROL **Impacto da ITP**] | Visualize e analise os efeitos da Prevenção de Rastreamento Inteligente (ITP) na coleta de dados e nos relatórios. <p>**Isso pode ajudar** a entender melhor a possível perda de dados devido a restrições de cookies impostas pela ITP.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como adaptar a configuração de análise para minimizar o impacto da ITP.</p> |

### Conversão {#web-conversion}

<!--AA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--categoryRankedReport"
>title="Veja o número de visitas associado a cada categoria de produto no site. Isso é útil para implementações que usam a variável produtos e que desejam visualizar métricas sobre a categoria do produto. A dimensão que preenche este modelo pode ficar em branco se não houver produtos no site."
>abstract="**Isso pode ajudar** a entender melhor os produtos mais vendidos ou os mais vistos. &lt;/br/>**Com base no que aprender, você poderá** fazer várias coisas, como medir a eficácia de uma campanha de marketing para um determinado produto.<br/>Este modelo usa a dimensão “Categoria” e a métrica “Visitas”. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--commerce-and-marketing-management"
>title="Visualize insights pré-criados para varejistas em suas atividades comerciais para ajudar a melhorar as vendas. Isto é direcionado a usuários do Adobe Commerce, mas pode ser aproveitado por qualquer varejista online."
>abstract="**Isso pode ajudar** a entender melhor como suas atividades comerciais estão contribuindo para os números de vendas.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como ajustar orçamentos para atividades que estão obtendo o maior ROI."

<!-- markdownlint-enable MD034 -->

<!--Both AA and CJA-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--productConversionReport"
>title="Visualize a conversão de produtos em uma visualização de funil que mostra carrinhos, check-outs e pedidos. É possível ver também porcentagens de conversão, médias de receita, médias de unidade e médias de pedido."
>abstract="**Isso pode ajudar** a entender melhor como as pessoas progridem e abandonam durante o processo de conversão.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como aprimorar o site para facilitar um processo de check-out mais fluido."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--retail-products-template"
>title="Veja quais produtos têm o melhor desempenho."
>abstract="**Isso pode ajudar** a entender melhor quais produtos são mais bem-sucedidos.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar os fundos destinados a produtos bem-sucedidos e diminuir os de produtos de menor sucesso.<br/>Este modelo usa as métricas “Exibições do produto”, “Adições ao carrinho”, “Pedidos”, “Receita” e “Unidades”. Ele também usa a dimensão “Produto”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cartConversionReport"
>title="Veja o número de vezes que as pessoas executam eventos importantes de check-out, como adicionar itens ao carrinho, visualizar o carrinho, remover itens do carrinho e concluir o pagamento."
>abstract="**Isso pode ajudar** a entender melhor quais partes do funil do processo de finalização levam à conversão e quais são mais propensos a abandono de carrinho.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como reduzir o atrito em determinadas etapas do processo de finalização.<br/>Este modelo usa"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cartsOvertimeReport"
>title="Veja o número de pessoas que adicionaram um produto ao carrinho."
>abstract="**Isso pode ajudar** a entender melhor o número de pessoas que adicionam um produto ao carrinho, em vez do número geral de produtos adicionados a um carrinho.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como medir a eficácia das páginas dos seus produtos.<br/>Este modelo usa a métrica “Carrinhos”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cartViewsOvertimeReport"
>title="Veja o número de vezes que as pessoas visualizaram seus carrinhos de compras."
>abstract="**Isso pode ajudar** a entender melhor a experiência de check-out na tentativa de reduzir as taxas de abandono de carrinho ou analisar o tempo entre as adições ao carrinho e os check-outs de diferentes produtos.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como oferecer promoções para produtos que permanecem mais tempo no carrinho e têm um risco maior de abandono.<br/>Este modelo usa a métrica “Exibições do carrinho”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cartAdditionsOvertimeReport"
>title="Veja o número de vezes que as pessoas adicionaram algo ao carrinho."
>abstract="**Isso pode ajudar** a entender melhor a parte do funil de conversão na qual o interesse de clientes em um produto é alto o suficiente para que o adicionem ao carrinho.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como melhorar as recomendações de produto para clientes. Isso pode ser feito pela análise de quais produtos são adicionados com frequência aos mesmos carrinhos e pela sugestão de produtos relacionados com base em itens já presentes no carrinho."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cartRemovalsOvertimeReport"
>title="Veja o número de vezes que as pessoas removeram algo do carrinho."
>abstract="**Isso pode ajudar** a entender melhor a parte do funil de conversão na qual clientes perdem o interesse no produto ou onde possam existir problemas no processo de finalização.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como remover possíveis barreiras que possam existir no processo de finalização, como uma experiência de usuário complicada.<br/>Este modelo usa a métrica “Remoções do carrinho”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--purchaseConversionReport"
>title="Visualize a conversão de compras em uma visualização de funil que mostra sessões, carrinhos e pedidos. É possível ver também porcentagens de conversão, médias de receita, médias de unidade e médias de pedido."
>abstract="**Isso pode ajudar** a entender melhor como as pessoas progridem e abandonam durante o processo de conversão.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como aprimorar o site para facilitar um processo de check-out mais fluido."

<!-- markdownlint-enable MD034 -->

Os seguintes modelos estão disponíveis:

| Nome do modelo | Por que usar este modelo <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Funil de conversão de produto**] | Visualize a conversão de produtos em uma visualização de funil que mostra carrinhos, check-outs e pedidos. É possível ver também porcentagens de conversão, médias de receita, médias de unidade e médias de pedido.<p>**Isso pode ajudar** a entender melhor como as pessoas progridem e abandonam durante o processo de conversão.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aprimorar o site para facilitar um processo de check-out mais fluido.</p> |
| **Produtos** | Veja quais produtos estão impulsionando as métricas principais, como os mais vendidos ou os mais vistos. <p>**Isso pode ajudar** a entender melhor quais produtos são mais bem-sucedidos.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar os fundos destinados a produtos bem-sucedidos e diminuir os de produtos de menor sucesso.</p><p>Esse modelo usa a métrica Pedidos e a dimensão Produto. |
| **Desempenho do produto** | Veja quais produtos têm o melhor desempenho.<p>**Isso pode ajudar** a entender melhor quais produtos são mais bem-sucedidos.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar os fundos destinados a produtos bem-sucedidos e diminuir os de produtos de menor sucesso.</p><p>Esse modelo usa as métricas Exibições do produto, Adições ao carrinho, Pedidos, Receita e Unidades. Ele também usa a dimensão “Produto”. |
| **Categorias** | Veja o número de visitas associado a cada categoria de produto no site. Isso é útil para implementações que usam a variável produtos e que desejam visualizar métricas sobre a categoria do produto. A dimensão que preenche este modelo pode ficar em branco se não houver produtos no site.<p>**Isso pode ajudá-lo** a entender melhor os produtos mais vendidos ou os mais vistos. </p><p>**Com base no que você aprendeu, é possível** realizar várias ações, como medir a eficácia de uma campanha de marketing para um determinado produto.</p><p>Esse modelo usa a dimensão Categoria e a métrica Visitas. |
| **Funis de conversão de carrinho** | Veja o número de vezes que as pessoas executam eventos importantes de check-out, como adicionar itens ao carrinho, visualizar o carrinho, remover itens do carrinho e concluir o pagamento. <p>**Isso pode ajudar** a entender melhor quais partes do funil do processo de finalização levam à conversão e quais são mais propensos a abandono de carrinho.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como reduzir o atrito em determinadas etapas do processo de finalização.</p><p>Este modelo usa o |
| **Carrinhos** | Veja o número de pessoas que adicionaram um produto ao carrinho.<p>**Isso pode ajudar** a entender melhor o número de pessoas que adicionam um produto ao carrinho, em vez do número geral de produtos adicionados a um carrinho.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como medir a eficácia das páginas dos seus produtos.</p><p>Esse modelo usa a métrica Carrinhos. |
| **Visualizações do carrinho** | Veja o número de vezes que as pessoas visualizaram seus carrinhos de compras. <p>**Isso pode ajudar** a entender melhor a experiência de check-out na tentativa de reduzir as taxas de abandono de carrinho ou analisar o tempo entre as adições ao carrinho e os check-outs de diferentes produtos.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como oferecer promoções para produtos que permanecem mais tempo no carrinho e têm um risco maior de abandono.</p><p>Esse modelo usa a métrica Exibições do carrinho. |
| **Adições ao carrinho** | Veja o número de vezes que as pessoas adicionaram algo ao carrinho. <p>**Isso pode ajudar** a entender melhor a parte do funil de conversão na qual o interesse de clientes em um produto é alto o suficiente para que o adicionem ao carrinho.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como melhorar as recomendações de produto para clientes. Para isso, é possível analisar quais produtos são adicionados com frequência aos mesmos carrinhos e sugerir produtos relacionados com base em itens já presentes no carrinho. |
| **Remoções do carrinho** | Veja o número de vezes que as pessoas removeram algo do carrinho.<p>**Isso pode ajudar** a entender melhor a parte do funil de conversão na qual clientes perdem o interesse no produto ou onde possam existir problemas no processo de finalização.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como remover possíveis barreiras que possam existir no processo de finalização, como uma experiência de usuário complicada.</p><p>Este modelo usa a métrica Remoções do carrinho. |
| **Funil de conversão de compra** | Visualize a conversão de compras em uma visualização de funil que mostra sessões, carrinhos e pedidos. É possível ver também porcentagens de conversão, médias de receita, médias de unidade e médias de pedido.<p>**Isso pode ajudar** a entender melhor como as pessoas progridem e abandonam durante o processo de conversão.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aprimorar o site para facilitar um processo de check-out mais fluido.</p> |
| **Receita** | <!--duplicated in Most popular section-->Exibir a quantidade monetária de produtos comprados em todos os pedidos.<p>**Isso pode ajudá-lo** a entender melhor quais itens de dimensão contribuíram para a receita, combinando a métrica Receita com qualquer dimensão. Por exemplo, você pode ver as campanhas principais (usando a dimensão Código de rastreamento ) que contribuíram para a receita. </p><p>**Com base no que você aprendeu, é possível** executar várias ações, como ajustar campanhas que não estão atingindo as metas de receita que você esperaria.</p><p>Este modelo usa a métrica Receita. |
| **Pedidos** | <!--duplicated in Most popular section-->Visualize o número total de eventos de compra feitos em seu site. <p>**Isso pode ajudá-lo** a entender melhor quais itens de dimensão contribuíram para um pedido, combinando a métrica Pedidos com qualquer dimensão. Por exemplo, você pode ver as campanhas principais (usando a dimensão Código de rastreamento ) que contribuíram com as compras.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como ajustar campanhas que não estão atingindo os objetivos de compra esperados. </p><p>Esse modelo usa a métrica Pedidos. |
| [!UICONTROL **Unidades**] | Visualize o número total de unidades compradas em todos os pedidos. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudar** a entender melhor como as vendas de unidades estão aumentando ou diminuindo com o tempo. Você pode aplicar um segmento para saber quais clientes ou regiões geográficas estão comprando a maior parte das unidades e quais são as tendências dessas vendas ao longo do tempo.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar a eficácia de uma campanha de marketing iniciada recentemente ao comparar as vendas de unidades antes e depois do início da campanha. É possível também comparar as vendas de unidades durante feriados a cada ano.</p><p>Este modelo usa a [dimensão de Dia](/help/components/dimensions/day.md) e a [métrica de Unidades](/help/components/metrics/units.md).</p> |
| [!UICONTROL **Magento: marketing e comércio**] | Visualize insights pré-criados para varejistas em suas atividades comerciais para ajudar a melhorar as vendas. Isto é direcionado a usuários do Adobe Commerce, mas pode ser aproveitado por qualquer varejista online. <p>**Isso pode ajudar** a entender melhor como suas atividades comerciais estão contribuindo para os números de vendas.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como ajustar orçamentos para atividades que estão obtendo o maior ROI.</p> |

### Público-alvo {#web-audience}

<!--AA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--people"
>title="Veja o número de pessoas que estão interagindo com a sua marca."
>abstract="**Isso pode ajudar** a entender melhor as tendências de uso do site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como medir a eficácia dos esforços recentes de marketing em gerar novos visitantes para o site."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--bots"
>title="Veja as visualizações de página e as tendências sobre o tráfego de bots no site."
>abstract="**Isso pode ajudar** a entender melhor o quanto do tráfego de bots está sendo filtrado nos relatórios, de acordo com as regras de bot configuradas.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como continuar a monitorar atividades de bots para identificar novos padrões."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--firstvsrepeatvisitors"
>title="Veja uma comparação entre novos visitantes e visitantes recorrentes."
>abstract="**Isso pode ajudar** a entender melhor a eficácia do site na retenção da fidelidade do cliente ou a taxa com que você está adquirindo novos clientes.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como oferecer incentivos para compras futuras a visitantes novos, incentivando o seu retorno."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--personid"
>title="Visualize o comportamento individual de usuários em vários canais."
>abstract="**Isso pode ajudar** a entender melhor a jornada completa do cliente e as interações em vários pontos de contato.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como personalizar as campanhas de marketing para direcionar melhor as preferências dos usuários."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timeZoneRankedReport"
>title="Visualize os principais fusos horários dos visitantes que acessam o site."
>abstract="**Isso pode ajudar** a entender melhor em quais fusos horários estão os seus visitantes.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como ajustar a manutenção do site para momentos em que um número menor de pessoas serão afetadas."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--location"
>title="Visualize uma visão geral da localização do visitante em uma visualização de mapa."
>abstract="**Isso pode ajudar** a entender melhor onde visitantes que estão visitando o site estão localizados. <br/>**Com base no que aprender, você poderá** fazer várias coisas, como concentrar os recursos de marketing nos locais em que observar maior interesse e oportunidades."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--domainRankedReport"
>title="Visualize os principais domínios dos visitantes acessando o site."
>abstract="**Isso pode ajudar** a entender melhor de quais organizações seus visitantes vêm.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como direcionar o conteúdo aos seus maiores clientes."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--topLevelDomainRankedReport"
>title="Visualize os principais domínios dos visitantes acessando o site."
>abstract="**Isso pode ajudar** a entender melhor de quais organizações seus visitantes vêm.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como direcionar o conteúdo aos seus maiores clientes."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--browserWidthRankedReport"
>title="Visualize as principais larguras de navegador que as pessoas usam para acessar o site."
>abstract="**Isso pode ajudar** a entender melhor como o conteúdo é exibido para os visitantes.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como melhorar a qualidade do site ao testar novas versões dele usando as larguras de navegador mais comuns. Isso pode maximizar os resultados do controle de qualidade.<br/>Este modelo usa a dimensão “Navegador”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--browserHeightRankedReport"
>title="Visualize as principais alturas de navegador que as pessoas usam para acessar o site."
>abstract="**Isso pode ajudar** a entender melhor como o conteúdo é exibido para os visitantes.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como melhorar a qualidade do site ao testar novas versões dele usando as alturas de navegador mais comuns. Isso pode maximizar os resultados do controle de qualidade.<br/>Este modelo usa a dimensão “Navegador”. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--operatingSystemRankedReport"
>title="Visualize o nome dos sistemas operacionais e a versão que as pessoas usam para acessar o site."
>abstract="**Isso pode ajudar** a entender melhor os sistemas operacionais mais comuns e as versões que visitantes usam.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como melhorar a qualidade do site ao testar novas versões dele usando os principais sistemas operacionais e versões. Isso pode maximizar os resultados do controle de qualidade."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--operatingSystemTypeRankedReport"
>title="Visualize o nome dos sistemas operacionais que as pessoas usam para acessar o site."
>abstract="**Isso pode ajudar** a entender melhor os sistemas operacionais mais comuns que visitantes usam.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como melhorar a qualidade do site ao testar novas versões dele usando os principais sistemas operacionais. Isso pode maximizar os resultados do controle de qualidade."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--returnFrequencyRankedReport"
>title="Veja a empresa de telecomunicação que fornece conectividade de rede celular aos dispositivos móveis que as pessoas usam para acessar o seu site."
>abstract="**Isso pode ajudar** a entender melhor quais operadoras de celular são mais usadas pela sua base de usuários.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como adaptar a entrega de conteúdo com base nos recursos de rede de diferentes operadoras para garantir uma experiência de usuário fluida.<br/>Este modelo usa a dimensão “Operadora de celular”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--returnVisitorsOvertimeReport"
>title="Veja a empresa de telecomunicação que fornece conectividade de rede celular aos dispositivos móveis que as pessoas usam para acessar o seu site."
>abstract="**Isso pode ajudar** a entender melhor quais operadoras de celular são mais usadas pela sua base de usuários.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como adaptar a entrega de conteúdo com base nos recursos de rede de diferentes operadoras para garantir uma experiência de usuário fluida.<br/>Este modelo usa a dimensão “Operadora de celular”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--visitNumberRankedReport"
>title="Visualize quantas vezes um visitante visitou o site."
>abstract="**Isso pode ajudar** a entender melhor como os visitantes estão engajados ao retornar ao site. Ela se aplica ao tempo de vida do visitante, independentemente do intervalo de datas do projeto.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como ajustar as campanhas de marketing para visitantes frequentes.<br/>Este modelo usa a dimensão &quot;Número da visita&quot;."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--customerLoyaltyRankedReport"
>title="Visualize o número de visitantes do site que fizeram 0 compras anteriores, 1 compra anterior, 2 compras anteriores ou 3+ compras anteriores."
>abstract="**Isso pode ajudar** a entender melhor como o site afeta o comportamento de compra.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como concentrar-se nos visitantes que retornam para fazer uma compra, para que possa incentivar comportamentos semelhantes em novos visitantes.<br/>Este modelo usa a dimensão &quot;Fidelização do cliente&quot;."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--daysBeforeFirstPurchaseRankedReport"
>title="Visualize o número de dias que se passaram entre a primeira vez que um visitante chega ao site e o momento em que realiza uma compra. Por exemplo, se um visitante efetua uma compra um dia após a primeira visita, qualquer visita ou evento subsequente pertence ao item de dimensão “1 dia”."
>abstract="**Isso pode ajudar** a entender melhor quanto tempo os visitantes levam para fazer uma compra.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como atualizar o site para incentivar aquisições mais rápidas.<br/>Este modelo usa a dimensão &quot;Dias antes da primeira compra&quot;."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--daysSinceLastPurchaseRankedReport"
>title="Visualize a quantidade de tempo decorrido entre a ocorrência atual do visitante e sua compra mais recente no momento."
>abstract="**Isso pode ajudar** a entender melhor o comportamento do visitante após comprar algo no site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como atualizar o site para incentivar compras subsequentes.<br/>Este modelo usa a dimensão &quot;Dias desde a última compra&quot;."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileScreenSizeRankedReport"
>title="Visualize os principais tamanhos de tela de dispositivos móveis que as pessoas usam para acessar o site."
>abstract="**Isso pode ajudar** a entender melhor como o conteúdo é exibido para visitantes.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como melhorar a qualidade do site ao testar novas versões dele usando os tamanhos de tela de dispositivos móveis mais comuns. Isso pode maximizar os resultados do controle de qualidade."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileScreenHeightRankedReport"
>title="Visualize as principais alturas de tela de dispositivos móveis que as pessoas usam para acessar o site."
>abstract="**Isso pode ajudar** a entender melhor como o conteúdo é exibido para visitantes.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como melhorar a qualidade do site ao testar novas versões dele usando as alturas de tela de dispositivos móveis mais comuns. Isso pode maximizar os resultados do controle de qualidade."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileScreenWidthRankedReport"
>title="Visualize as principais larguras de tela de dispositivos móveis que as pessoas usam para acessar o site."
>abstract="**Isso pode ajudar** a entender melhor como o conteúdo é exibido para visitantes.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como melhorar a qualidade do site ao testar novas versões dele usando as larguras de tela de dispositivos móveis mais comuns. Isso pode maximizar os resultados do controle de qualidade."

<!-- markdownlint-enable MD034 -->

<!--Both AA and CJA-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--countryGeoReport"
>title="Veja o país de origem das pessoas que visitam o site."
>abstract="**Isso pode ajudar** a entender melhor quais são os principais países de origem de visitantes do site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como usar os dados para aumentar o foco das campanhas de marketing nesses países ou garantir que a experiência do site seja ideal em países com diferentes idiomas nativos.<br/>Este modelo usa a dimensão “Países”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--stateGeoReport"
>title="Veja o estado (nos Estados Unidos) de origem das pessoas que visitaram o site. Ele é semelhante ao modelo “Regiões geográficas”, exceto pelo fato de ser específico para os Estados Unidos."
>abstract="**Isso pode ajudar** a entender melhor os principais estados de origem dos usuários dos Estados Unidos que visitam o seu site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como usar os dados para aumentar o foco das campanhas de marketing nesses estados.<br/>Este modelo utiliza a dimensão “Estados dos EUA”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--regionGeoReport"
>title="Veja a região geográfica de origem de visitantes do site. Uma região é uma área geográfica menor que um país, mas maior que uma cidade. Em alguns países, uma região é um estado, província ou distrito. Em outras áreas, é um país constituinte, departamento ou região metropolitana. "
>abstract="**Isso pode ajudar** a entender melhor as regiões de origem principais de visitantes do seu site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como usar os dados para aumentar o foco das campanhas de marketing nessas regiões ou verificar se a experiência do site é ideal em regiões com diferentes idiomas nativos. <br/>Este modelo usa as dimensões “ID (variáveis/país geográfico)” e “Regiões”. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cityGeoReport"
>title="Veja a cidade de origem de visitantes do site."
>abstract="**Isso pode ajudar** a entender melhor as cidades de origem principais de visitantes do seu site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como usar os dados para aumentar o foco das campanhas de marketing nessas cidades. <br/>Este modelo usa a dimensão “Cidades”"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--dmaGeoReport"
>title="Veja as áreas de marketing designadas (DMAs) de origem de visitantes do site nos Estados Unidos."
>abstract="**Isso pode ajudar** a entender melhor as regiões de origem principais de visitantes do seu site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como usar os dados para aumentar o foco das campanhas de marketing nas regiões mais bem-sucedidas. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--languageRankedReport"
>title="Veja os principais idiomas nos quais visitantes preferem visualizar o conteúdo."
>abstract="**Isso pode ajudar** a entender melhor os idiomas preferidos de visitantes.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das atividades de localização ou campanhas de marketing nos idiomas mais populares.<br/>Este modelo usa a dimensão “Idioma”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--web-technology-template"
>title="Veja as informações relacionadas à tecnologia que as pessoas usam para acessar o seu site, como sistemas operacionais, navegadores e dispositivos."
>abstract="**Isso pode ajudar** a entender melhor quais tecnologias são usadas com mais frequência no acesso ao site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como otimizar o site para as tecnologias que estão sendo usadas."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--browserRankedReport"
>title="Veja o nome e a versão dos principais navegadores que as pessoas usam para acessar o seu site."
>abstract="**Isso pode ajudar** a entender melhor os navegadores mais comuns que visitantes usam.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como melhorar a qualidade do site por testar novas versões dele nos principais navegadores. Isso pode maximizar os resultados do controle de qualidade.<br/>Este modelo usa a dimensão “Navegador”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--browserTypeRankedReport"
>title="Veja os nomes das organizações que criaram os principais navegadores que as pessoas usam para acessar o seu site. Ele é diferente do modelo “Navegador”, pois não lista diferentes versões do mesmo navegador como itens de dimensão separados."
>abstract="**Isso pode ajudar** a entender melhor os navegadores mais comuns que visitantes usam <br/>**Com base no que aprender, você poderá** fazer várias coisas, como melhorar a qualidade do site por testar novas versões dele nos principais navegadores. Isso pode maximizar os resultados do controle de qualidade. <br/>Esse modelo utiliza a dimensão “Tipo de navegador”. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileappscreens"
>title="Visualize o número de eventos, sessões e pessoas associados a cada tela no aplicativo móvel."
>abstract="**Isso pode ajudar** a entender melhor quais telas do site são as mais visitadas.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como aprimorar o conteúdo nas telas mais populares."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileappactions"
>title="Veja as ações que as pessoas estão realizando no aplicativo móvel."
>abstract="**Isso pode ajudar** a entender melhor como as pessoas estão usando o seu aplicativo e o valor que estão obtendo com ele.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como desenvolver recursos que complementem ou aprimorem as mais populares."

<!-- markdownlint-enable MD034 -->

<!--CJA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-lifecycle-metrics-app-usage-template"
>title="Visualize o número de usuários, inicializações e primeiras inicializações no aplicativo, bem como a duração média das sessões."
>abstract="**Isso pode ajudar** a entender melhor o quanto o aplicativo está sendo usado. <br/>**Com base no que aprender, poderá** fazer várias coisas, como melhorar o desempenho do aplicativo para que possa haver o dimensionamento de acordo com a quantidade de uso."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-app-journeys"
>title="Visualize os principais padrões de uso do seu aplicativo móvel."
>abstract="**Isso pode ajudar** a entender melhor como as pessoas estão usando o aplicativo. <br/>**Com base no que aprender, você poderá** fazer várias coisas, como melhorar a forma como as pessoas podem passar de uma tela à outra para direcionar os fluxos de trabalho mais comuns."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-app-key-metrics"
>title="Visualize algumas das métricas mais comuns do aplicativo móvel."
>abstract="**Isso pode ajudar** a entender melhor o desempenho básico do aplicativo móvel.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar a integridade e o desempenho geral do aplicativo."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-app-messaging"
>title="Visualize dados de desempenho de mensagens no aplicativo e por push."
>abstract="**Isso pode ajudar** a entender melhor como as pessoas estão usando os recursos de mensagens no aplicativo, bem como a eficiência com que as notificações por push estão direcionando o tráfego para o aplicativo.<br/>**Com base no que aprender, poderá** fazer várias coisas, como melhorar a experiência de notificações por push e mensagens no aplicativo."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-app-performance-template"
>title="Visualize o desempenho do aplicativo e onde os usuários estão com problemas."
>abstract="**Isso pode ajudar** a entender se as pessoas que usam o aplicativo estão encontrando lentidão ou desempenho degradado. <br/>**Com base no que aprender, poderá** fazer várias coisas, como corrigir problemas existentes ou melhorar o desempenho do aplicativo antes que eles ocorram."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-app-retention"
>title="Veja quais são os usuários mais fiéis do aplicativo e o que fazem nele."
>abstract="**Isso pode ajudar** a entender melhor como os usuários mais fiéis estão usando o aplicativo.<br/>**Com base no que aprender, poderá** fazer várias coisas, como melhorar os esforços de marketing para os recursos que seus usuários mais fiéis estão usando."

<!-- markdownlint-enable MD034 -->

Os seguintes modelos estão disponíveis:

| Nome do modelo | Por que usar este modelo <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Métrica de pessoas**] | Veja o número de pessoas que estão interagindo com a sua marca. <p>**Isso pode ajudar** a entender melhor as tendências de uso do site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como medir a eficácia dos esforços recentes de marketing em gerar novos visitantes para o site.</p> |
| **Perfil do visitante** > **Visão geral da localização** | Visualize uma visão geral da localização do visitante em uma visualização de mapa.<p>**Isso pode ajudá-lo** a entender melhor onde estão os visitantes que estão visitando seu site. </p><p>**Com base no que aprender, você poderá** fazer várias coisas, como concentrar os recursos de marketing nos locais em que observar maior interesse e oportunidades.</p><!-- This template uses the --> |
| **Perfil do visitante** > **Segmentação geográfica** > **Países geográficos** | Veja o país de origem das pessoas que visitam o site.<p>**Isso pode ajudar** a entender melhor quais são os principais países de origem de visitantes do site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como usar os dados para aumentar o foco das campanhas de marketing nesses países ou garantir que a experiência do site seja ideal em países com diferentes idiomas nativos.</p><p>Este modelo usa a dimensão Países. </p> |
| **Perfil do visitante** > **Segmentação geográfica** > **Estados geográficos dos EUA** | Veja o estado (nos Estados Unidos) de origem das pessoas que visitaram o site. Ele é semelhante ao modelo “Regiões geográficas”, exceto pelo fato de ser específico para os Estados Unidos.<p>**Isso pode ajudar** a entender melhor os principais estados de origem dos usuários dos Estados Unidos que visitam o seu site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como usar os dados para aumentar o foco das campanhas de marketing nesses estados.</p><p>Esse modelo usa a dimensão Estados dos EUA. </p> |
| **Perfil do visitante** > **Segmentação geográfica** > **Regiões geográficas** | Veja a região geográfica de origem de visitantes do site. Uma região é uma área geográfica menor que um país, mas maior que uma cidade. Em alguns países, uma região é um estado, província ou distrito. Em outras áreas, é um país constituinte, departamento ou região metropolitana. <p>**Isso pode ajudar** a entender melhor as regiões de origem principais de visitantes do seu site.</p><p>**Com base no que você aprendeu, é possível** realizar várias ações, como usar os dados para se concentrar nos esforços de marketing nessas regiões ou verificar se a experiência do site é ideal em regiões com idiomas principais diferentes. </p><p>Esse modelo usa as dimensões ID(variáveis/país_geográfico) e Regiões. </p> |
| **Perfil do visitante** > **Segmentação geográfica** > **Cidades geográficas** | Veja a cidade de origem de visitantes do site. <p>**Isso pode ajudar** a entender melhor as cidades de origem principais de visitantes do seu site.</p><p>**Com base no que você aprendeu, você pode** fazer várias coisas, como usar os dados para se concentrar nos esforços de marketing nessas cidades. </p><p>Esse modelo usa a dimensão Cidades. </p> |
| **Perfil do visitante** > **Segmentação geográfica** > **DMA Geográfico dos EUA** | Veja as áreas de marketing designadas (DMAs) de origem de visitantes do site nos Estados Unidos.<p>**Isso pode ajudar** a entender melhor as regiões de origem principais de visitantes do seu site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como usar os dados para aumentar o foco das campanhas de marketing nas regiões mais bem-sucedidas. </p><!-- This template uses the --> |
| **Perfil do visitante** > **Idiomas** | Veja os principais idiomas nos quais visitantes preferem visualizar o conteúdo. <p>**Isso pode ajudar** a entender melhor os idiomas preferidos de visitantes.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das atividades de localização ou campanhas de marketing nos idiomas mais populares.</p><p>Esse modelo usa a dimensão Idioma.</p> |
| **Perfil do visitante** > **Fusos horários** | Visualize os principais fusos horários dos visitantes que acessam o site. <p>**Isso pode ajudar** a entender melhor em quais fusos horários estão os seus visitantes.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como ajustar a manutenção do site para momentos em que um número menor de pessoas serão afetadas.</p> |
| **Perfil do visitante** > **Domínios** | Visualize os principais domínios dos visitantes acessando o site. <p>**Isso pode ajudar** a entender melhor de quais organizações seus visitantes vêm.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como direcionar o conteúdo aos seus maiores clientes.</p> |
| **Perfil do visitante** > **Domínios de nível superior** | Exibir os domínios de nível superior dos visitantes que acessam o site. <p>**Isso pode ajudar** a entender melhor de quais organizações seus visitantes vêm.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como direcionar o conteúdo aos seus maiores clientes.</p> |
| **Perfil do visitante** > **Tecnologia** > **Visão geral da tecnologia** | Exibir informações relacionadas à tecnologia que as pessoas usam para acessar seu site, como sistemas operacionais, navegadores e dispositivos. <p>**Isso pode ajudar** a entender melhor quais tecnologias são usadas com mais frequência no acesso ao site.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como otimizar o site para as tecnologias usadas.</p> |
| **Perfil do visitante** > **Tecnologia** > **Navegadores** | Veja o nome e a versão dos principais navegadores que as pessoas usam para acessar o seu site.<p>**Isso pode ajudar** a entender melhor os navegadores mais comuns que visitantes usam.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como melhorar a qualidade do site por testar novas versões dele nos principais navegadores. Isso pode maximizar os resultados do controle de qualidade.</p><p>Esse modelo usa a dimensão Navegador. </p> |
| **Perfil do visitante** > **Tecnologia** > **Tipos de navegador** | Veja os nomes das organizações que criaram os principais navegadores que as pessoas usam para acessar o seu site. Ele é diferente do modelo “Navegador”, pois não lista diferentes versões do mesmo navegador como itens de dimensão separados.<p>**Isso pode ajudá-lo** a entender melhor os navegadores mais comuns que os visitantes usam</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como melhorar a qualidade do site por testar novas versões dele nos principais navegadores. Isso pode maximizar os resultados do controle de qualidade. </p><p>Esse modelo usa a dimensão Tipo de navegador. </p> |
| **Perfil do visitante** > **Tecnologia** > **Largura do navegador** | Visualize as principais larguras de navegador que as pessoas usam para acessar o site.<p>**Isso pode ajudar** a entender melhor como o conteúdo é exibido para os visitantes.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como melhorar a qualidade do site ao testar novas versões dele usando as larguras de navegador mais comuns. Isso pode maximizar os resultados do controle de qualidade.</p><p>Esse modelo usa a dimensão Navegador. </p> |
| **Perfil do visitante** > **Tecnologia** > **Altura do navegador** | Visualize as principais alturas do navegador que as pessoas usam para acessar seu site.<p>**Isso pode ajudar** a entender melhor como o conteúdo é exibido para os visitantes.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como melhorar a qualidade do site ao testar novas versões dele usando as alturas de navegador mais comuns. Isso pode maximizar os resultados do controle de qualidade.</p><p>Esse modelo usa a dimensão Navegador. </p> |
| **Perfil do visitante** > **Tecnologia** > **Sistema operacional** | Visualize o nome dos sistemas operacionais e a versão que as pessoas usam para acessar o site.<p>**Isso pode ajudar** a entender melhor os sistemas operacionais mais comuns e as versões que visitantes usam.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como melhorar a qualidade do site ao testar novas versões dele usando os principais sistemas operacionais e versões. Isso pode maximizar os resultados do controle de qualidade.</p> |
| **Perfil do visitante** > **Tecnologia** > **Tipos de sistema operacional** | Visualize o nome dos sistemas operacionais que as pessoas usam para acessar o site.<p>**Isso pode ajudar** a entender melhor os sistemas operacionais mais comuns que visitantes usam.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como melhorar a qualidade do site ao testar novas versões dele usando os principais sistemas operacionais. Isso pode maximizar os resultados do controle de qualidade.</p> |
| **Perfil de visitante** > **Tecnologia** > [!UICONTROL **Operadora de celular**] | Veja a empresa de telecomunicação que fornece conectividade de rede celular aos dispositivos móveis que as pessoas usam para acessar o seu site.<p>**Isso pode ajudar** a entender melhor quais operadoras de celular são mais usadas pela sua base de usuários.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como adaptar a entrega de conteúdo com base nos recursos de rede de diferentes operadoras para garantir uma experiência de usuário fluida.</p><p>Esse modelo usa a dimensão Operadora de celular.</p> |
| **Retenção de visitante** > **Frequência de retorno** | Veja a empresa de telecomunicação que fornece conectividade de rede celular aos dispositivos móveis que as pessoas usam para acessar o seu site.<p>**Isso pode ajudar** a entender melhor quais operadoras de celular são mais usadas pela sua base de usuários.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como adaptar a entrega de conteúdo com base nos recursos de rede de diferentes operadoras para garantir uma experiência de usuário fluida.</p><p>Esse modelo usa a dimensão Operadora de celular.</p> |
| **Retenção de visitante** > **Visitas de retorno** | Veja a empresa de telecomunicação que fornece conectividade de rede celular aos dispositivos móveis que as pessoas usam para acessar o seu site.<p>**Isso pode ajudar** a entender melhor quais operadoras de celular são mais usadas pela sua base de usuários.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como adaptar a entrega de conteúdo com base nos recursos de rede de diferentes operadoras para garantir uma experiência de usuário fluida.</p><p>Esse modelo usa a dimensão Operadora de celular.</p> |
| **Retenção de visitante** > **Número da visita** | Visualize quantas vezes um visitante visitou o site.<p>**Isso pode ajudar** a entender melhor como os visitantes estão engajados ao retornar ao site. Ela se aplica ao tempo de vida do visitante, independentemente do intervalo de datas do projeto.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como ajustar as campanhas de marketing para visitantes frequentes.</p><p>Esse modelo usa a dimensão Número de visitas.</p> |
| **Retenção de visitante** > **Ciclo de vendas** > **Fidelização do cliente** | Visualize o número de visitantes do site que fizeram 0 compras anteriores, 1 compra anterior, 2 compras anteriores ou 3+ compras anteriores. <p>**Isso pode ajudar** a entender melhor como o site afeta o comportamento de compra.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como concentrar-se nos visitantes que retornam para fazer uma compra, para que possa incentivar comportamentos semelhantes em novos visitantes.</p><p>Esse modelo usa a dimensão Fidelização do cliente.</p> |
| **Retenção de visitante** > **Ciclo de vendas** > **Dias antes da primeira compra** | Visualize o número de dias que se passaram entre a primeira vez que um visitante chega ao site e o momento em que realiza uma compra. Por exemplo, se um visitante efetua uma compra um dia após a primeira visita, qualquer visita ou evento subsequente pertence ao item de dimensão “1 dia”.<p>**Isso pode ajudar** a entender melhor quanto tempo os visitantes levam para fazer uma compra.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como atualizar o site para incentivar aquisições mais rápidas.</p><p>Esse modelo usa a dimensão Dias antes da primeira compra.</p> |
| **Retenção de visitante** > **Ciclo de vendas** > **Dias desde a última compra** | Visualize a quantidade de tempo decorrido entre a ocorrência atual do visitante e sua compra mais recente no momento.<p>**Isso pode ajudar** a entender melhor o comportamento do visitante após comprar algo no site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como atualizar o site para incentivar compras subsequentes.</p><p>Esse modelo usa a dimensão Dias desde a última compra.</p> |
| **Dispositivos móveis** > **Dispositivos** | Veja a marca e o modelo dos dispositivos móveis que as pessoas usam para acessar o seu site.<p>**Isso pode ajudar** a entender melhor quais dispositivos móveis são mais usados pela sua base de usuários.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como otimizar a renderização do site para os dispositivos móveis mais comuns.</p><p>Esse modelo usa a dimensão Nome do dispositivo móvel.</p> |
| **Celular** > **Tipo de dispositivo** | Veja os tipos de dispositivo móvel que as pessoas usam para acessar o seu site, como telefones e tablets.<p>**Isso pode ajudá-lo** a entender melhor os vários tipos de dispositivos móveis usados para acessar seu site.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como otimizar o site para os tipos de dispositivos móveis mais usados.</p><p>Esse modelo usa a dimensão Tipo de dispositivo móvel.</p> |
| **Celular** > **Fabricante** | Veja quais fabricantes produzem os dispositivos móveis que as pessoas usam para acessar o seu site, como Apple e Samsung.<p>**Isso pode ajudar** a entender melhor quais fabricantes são mais usados pela sua base de usuários.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como adaptar a entrega de conteúdo com base nos recursos de diferentes fabricantes para garantir uma experiência de usuário fluida.</p><p>Esse modelo usa a dimensão Fabricante do dispositivo móvel.</p> |
| **Celular** > **Tamanho da tela** | Visualize os principais tamanhos de tela de dispositivos móveis que as pessoas usam para acessar o site.<p>**Isso pode ajudar** a entender melhor como o conteúdo é exibido para visitantes.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como melhorar a qualidade do site ao testar novas versões dele usando os tamanhos de tela de dispositivos móveis mais comuns. Isso pode maximizar os resultados do controle de qualidade.</p> |
| **Dispositivo móvel** > **Altura da tela** | Visualize as principais alturas de tela de dispositivos móveis que as pessoas usam para acessar o site.<p>**Isso pode ajudar** a entender melhor como o conteúdo é exibido para visitantes.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como melhorar a qualidade do site ao testar novas versões dele usando as alturas de tela de dispositivos móveis mais comuns. Isso pode maximizar os resultados do controle de qualidade.</p> |
| **Dispositivo móvel** > **Largura da tela** | Visualize as principais larguras de tela de dispositivos móveis que as pessoas usam para acessar o site.<p>**Isso pode ajudar** a entender melhor como o conteúdo é exibido para visitantes.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como melhorar a qualidade do site ao testar novas versões dele usando as larguras de tela de dispositivos móveis mais comuns. Isso pode maximizar os resultados do controle de qualidade.</p> |
| **Dispositivo móvel** > **Uso do aplicativo móvel** | Visualize o número de usuários, inicializações e primeiras inicializações no aplicativo, bem como a duração média das sessões.<p>**Isso pode ajudá-lo** a entender melhor quanto seu aplicativo está sendo usado. </p><p>**Com base no que aprender, poderá** fazer várias coisas, como melhorar o desempenho do aplicativo para que possa haver o dimensionamento de acordo com a quantidade de uso.</p><!-- This template uses the --> |
| **Dispositivo móvel** > **jornadas de aplicativo móvel** | Visualize os principais padrões de uso do seu aplicativo móvel. <p>**Isso pode ajudá-lo** a entender melhor como as pessoas estão usando seu aplicativo. </p><p>**Com base no que aprender, você poderá** fazer várias coisas, como melhorar a forma como as pessoas podem passar de uma tela à outra para direcionar os fluxos de trabalho mais comuns. </p><!-- This template uses the --> |
| **Dispositivo móvel** > **Métricas do aplicativo móvel** | Visualize algumas das métricas mais comuns do aplicativo móvel. <p>**Isso pode ajudar** a entender melhor o desempenho básico do aplicativo móvel.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar a integridade e o desempenho geral do aplicativo.</p><!-- This template uses the --> |
| **Dispositivo móvel** > **Mensagens de aplicativo móvel** | Visualize dados de desempenho de mensagens no aplicativo e por push.<p>**Isso pode ajudar** a entender melhor como as pessoas estão usando os recursos de mensagens no aplicativo, bem como a eficiência com que as notificações por push estão direcionando o tráfego para o aplicativo.</p><p>**Com base no que aprender, poderá** fazer várias coisas, como melhorar a experiência de notificações por push e mensagens no aplicativo.</p><!-- This template uses the --> |
| **Dispositivo móvel** > **Desempenho do aplicativo móvel** | Visualize o desempenho do aplicativo e onde os usuários estão com problemas. <p>**Isso pode ajudá-lo** a entender melhor se as pessoas que usam seu aplicativo estão encontrando lentidão ou desempenho degradado. </p><p>**Com base no que aprender, poderá** fazer várias coisas, como corrigir problemas existentes ou melhorar o desempenho do aplicativo antes que eles ocorram.</p><!-- This template uses the --> |
| **Dispositivo móvel** > **Retenção de aplicativo móvel** | Veja quais são os usuários mais fiéis do aplicativo e o que fazem nele. <p>**Isso pode ajudar** a entender melhor como os usuários mais fiéis estão usando o aplicativo.</p><p>**Com base no que aprender, poderá** fazer várias coisas, como melhorar os esforços de marketing para os recursos que seus usuários mais fiéis estão usando.</p><!-- This template uses the --> |
| **Bots** | Veja as visualizações de página e as tendências sobre o tráfego de bots no site. <p>**Isso pode ajudar** a entender melhor o quanto do tráfego de bots está sendo filtrado nos relatórios, de acordo com as regras de bot configuradas.</p><p>**Com base no que você aprende, é possível** executar várias ações, como continuar a monitorar a atividade dos bots para identificar novos padrões.</p><!-- This template uses the --> |

### Aquisição {#web-acquisition}

<!--AA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobile-app-acquisition-template"
>title="Visualize como o site obtém visitantes em dispositivos móveis."
>abstract="**Isso pode ajudar** a entender melhor os vários fatores que levam à aquisição, como palavras-chave de pesquisa, domínio de referência e assim por diante.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das campanhas de marketing nos canais mais eficientes.<br/>Este modelo usa as métricas “Taxa de rejeição” e “Rejeições”. Ele também usa as dimensões “Mecanismo de pesquisa”, “Palavra-chave de pesquisa”, “Página de entrada”, “Domínio de referência”, “Código de rastreamento” e “Referenciador”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--advertisingAnalyticsPaidSearch"
>title="Visualize todos os dados de pesquisa paga do Google e do Bing lado a lado."
>abstract="**Isso pode ajudar** a entender melhor a quantidade de tráfego que está sendo enviada para o site e se os clientes estão convertendo.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como estimar o custo/benefício de uma campanha publicitária."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--searchEngineRankRankedReport"
>title="Visualize em qual página dos resultados de pesquisa um visitante clicou para chegar ao seu site. Por exemplo, se o site for exibido na segunda página dos resultados de pesquisa de um mecanismo de pesquisa, o item de dimensão para essa variável será Página de pesquisa 2."
>abstract="**Isso pode ajudar** a entender melhor a classificação das suas páginas em resultados de pesquisa.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como melhorar sua estratégia de SEO para garantir que o conteúdo apareça na primeira página dos resultados de pesquisa."

<!-- markdownlint-enable MD034 -->

<!--Both AA and CJA-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--marketing-channel-overview-template"
>title="Por meio da atribuição personalizada, este modelo mostra como visitantes chegam ao seu site."
>abstract="**Isso pode ajudar** a entender melhor quais dos seus canais de marketing são mais eficazes.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o investimento em canais de marketing eficazes e livrar-se de canais de marketing menos eficazes.<br/>Este modelo usa a dimensão “ID (variáveis/canal de marketing)” e a métrica “Receita”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--firstouchChannelRankedReport"
>title="Veja o primeiro canal de marketing com o qual um visitante corresponde durante seu período de engajamento (30 dias, por padrão)."
>abstract="**Isso pode ajudar** a entender melhor quais canais de marketing geram o tráfego inicial para o seu site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das campanhas de marketing em áreas mais eficazes.<br/>Este modelo usa a dimensão “Canal de primeiro contato”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--firstouchChannelDetailRankedReport"
>title="Veja os detalhes do primeiro canal de marketing que um(a) visitante utiliza durante o seu período de engajamento (30 dias por padrão)."
>abstract="**Isso pode ajudar** a entender melhor o que contribuiu para que a visita ocorresse por meio daquele canal de marketing. Por exemplo, se um visitante chegasse ao seu site e correspondesse ao canal de marketing &quot;Pesquisa paga&quot;, você poderia usar os detalhes do canal para ver qual mecanismo de pesquisa foi usado ou qual palavra-chave foi pesquisada.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das campanhas de marketing em áreas mais eficazes.<br/>Este modelo usa a dimensão “Detalhes do canal de primeiro contato”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--campaignConversionReport"
>title="Veja o número de cliques e check-outs das suas campanhas."
>abstract="**Isso pode ajudar** a entender melhor como as campanhas de marketing estão impulsionando a conversão.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como determinar quais campanhas de marketing estão gerando maior ROI."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--retail-campaign-performance-template"
>title="Veja os detalhes do desempenho das suas campanhas de marketing."
>abstract="**Isso pode ajudar** a entender melhor os vários indicadores de sucesso associados às campanhas, como receita, exibições de produtos, pedidos e assim por diante.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das campanhas de marketing nas maiores fontes de receita. <br/>Este modelo usa as métricas “Receita”, “Exibições do produto”, “Adições ao carrinho”, “Pedidos” e “Unidades”. Ele também usa as dimensões “Código de rastreamento” e “Domínio de referência”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--web-acquisition-template"
>title="Veja como o seu site obtém visitantes."
>abstract="**Isso pode ajudar** a entender melhor os vários fatores que levam à aquisição, como palavras-chave de pesquisa, domínio de referência e assim por diante.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das campanhas de marketing nos canais mais eficientes.<br/>Este modelo usa as métricas “Taxa de rejeição” e “Rejeições”. Ele também usa as dimensões “Mecanismo de pesquisa”, “Palavra-chave de pesquisa”, “Página de entrada”, “Domínio de referência”, “Código de rastreamento” e “Referenciador”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchKeywordRankedReport"
>title="Veja as palavras-chave de pesquisa que visitantes usam para acessar o seu site, sejam elas pagas ou naturais."
>abstract="**Isso pode ajudar** a entender melhor as palavras-chave que as pessoas usam em pesquisas que resultam no tráfego do site. <br/>**Com base no que aprender, você poderá** fazer várias coisas, como identificar e preencher lacunas de SEO entre as palavras-chave usadas e as que estão gerando tráfego para o site.<br/>Este modelo usa a dimensão “Palavra-chave de pesquisa”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchPaidKeywordRankedReport"
>title="Veja as palavras-chave de pesquisa que visitantes usam para acessar o seu site que correspondem à detecção de pesquisa paga."
>abstract="**Isso pode ajudar** a entender melhor as palavras-chave que as pessoas usam em pesquisas que geram tráfego para o site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como identificar e preencher lacunas de SEO entre as palavras-chave usadas e as que estão gerando tráfego para o site. <br/>Este modelo usa a dimensão “Palavra-chave de pesquisa paga”. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchNaturalKeywordRankedReport"
>title="Veja as palavras-chave de pesquisa que visitantes usam para acessar o seu site e que não correspondem à detecção de pesquisa paga."
>abstract="**Isso pode ajudar** a entender melhor as palavras-chave que as pessoas usam em pesquisas que geram tráfego para o site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como identificar e preencher lacunas de SEO entre as palavras-chave usadas e as que estão gerando tráfego para o site.<br/>Este modelo usa a dimensão “Palavra-chave de pesquisa natural”. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchRankedReport"
>title="Veja os mecanismos de pesquisa que visitantes usam para acessar o seu site, sejam elas pagas ou naturais."
>abstract="**Isso pode ajudar** a entender melhor os mecanismos de pesquisa usados pelas pessoas que resultam em tráfego para o site. <br/>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco de SEO nos mecanismos de pesquisa que geram mais tráfego para o site.<br/>Este modelo usa a dimensão “Mecanismo de pesquisa”. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchPaidRankedReport"
>title="Veja os mecanismos de pesquisa que visitantes usam para acessar o seu site e que correspondem à detecção de pesquisa paga."
>abstract="**Isso pode ajudar** a entender melhor os mecanismos de pesquisa usados pelas pessoas que resultam em tráfego para o site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco de SEO nos mecanismos de pesquisa que geram mais tráfego para o site. <br/>Este modelo usa a dimensão “Mecanismo de pesquisa paga”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchNaturalRankedReport"
>title="Veja as palavras-chave de pesquisa que visitantes usam para acessar o seu site e que não correspondem à detecção de pesquisa paga."
>abstract="**Isso pode ajudar** a entender melhor os mecanismos de pesquisa usados pelas pessoas que resultam em tráfego para o site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco de SEO nos mecanismos de pesquisa que geram mais tráfego para o site.<br/>Este modelo usa a dimensão “Mecanismo de pesquisa natural”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--referringDomainRankedReport"
>title="Veja em quais domínios as pessoas clicam para acessar o seu site."
>abstract="**Isso pode ajudar** a entender quais sites de terceiros geram mais tráfego para o seu site. (Deve haver um link no site externo e o(a) visitante precisa clicar nele para que o item de dimensão seja exibido.)<br/>**Com base no que aprender, você poderá** fazer várias coisas, como criar ou ajustar o conteúdo para melhor se alinhar aos interesses de visitantes provenientes dos principais domínios referenciadores. <br/>Este modelo usa a dimensão “Domínio referenciador”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--referringDomainOriginalRankedReport"
>title="Veja o primeiro domínio referenciador no qual as pessoas clicam para acessar o seu site. (Depois de definido, ele mantém o mesmo valor por toda a vida útil da ID do(a) visitante em questão.)"
>abstract="**Isso pode ajudar** a entender melhor quais sites de terceiros originalmente geram tráfego para o seu site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como criar ou ajustar o conteúdo para melhor se alinhar aos interesses de visitantes provenientes dos principais domínios referenciadores originais. <br/>Este modelo usa a dimensão “Domínio referenciador original”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--referrerRankedReport"
>title="Veja em quais URLs os(as) visitantes estavam quando clicaram para acessar o seu site. (Deve haver um link no URL externo e o(a) visitante precisa clicar nele para que o item de dimensão seja exibido.)"
>abstract="**Isso pode ajudar** a entender quais URLs específicos geram mais tráfego para o seu site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como criar ou ajustar o conteúdo para melhor se alinhar aos interesses de visitantes provenientes dos principais URLs. <br/>Este modelo usa a dimensão “Domínio referenciador”.</p>"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--referrerTypeRankedReport"
>title="Veja em quais canais genéricos os(as) visitantes clicaram para acessar o seu site. A Adobe mantém as regras de cada canal. Os possíveis canais incluem mecanismos de pesquisa, redes sociais, outros sites, disco rígido ou email."
>abstract="**Isso pode ajudar** a entender melhor qual tipo de referenciador gera mais tráfego para o site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como criar ou ajustar o conteúdo para melhor se alinhar aos interesses de visitantes provenientes de um determinado canal.<br/>Este modelo usa a dimensão “Tipo de referenciador”."

<!-- markdownlint-enable MD034 -->

Os seguintes modelos estão disponíveis:

| Nome do modelo | Por que usar este modelo <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Canais de marketing**] > [!UICONTROL **Relatório de visão geral do canal**] | Por meio da atribuição personalizada, este modelo mostra como visitantes chegam ao seu site.<p>**Isso pode ajudar** a entender melhor quais dos seus canais de marketing são mais eficazes.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o investimento em canais de marketing eficazes e livrar-se de canais de marketing menos eficazes.</p><p>Esse modelo usa a dimensão ID(variables/marketingchannel) e a métrica Receita.</p> |
| [!UICONTROL **Canais de marketing**] > [!UICONTROL **Canal de primeiro contato**] | Veja o primeiro canal de marketing com o qual um visitante corresponde durante seu período de engajamento (30 dias, por padrão). <p>**Isso pode ajudar** a entender melhor quais canais de marketing geram o tráfego inicial para o seu site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das campanhas de marketing em áreas mais eficazes.</p><p>Esse modelo usa a dimensão Canal de primeiro contato.</p> |
| [!UICONTROL **Canais de marketing**] > [!UICONTROL **Detalhes do canal de primeiro contato**] | Veja os detalhes do primeiro canal de marketing que um(a) visitante utiliza durante o seu período de engajamento (30 dias por padrão).<p>**Isso pode ajudar** a entender melhor o que contribuiu para que a visita ocorresse por meio daquele canal de marketing. Por exemplo, se um visitante chegasse ao seu site e correspondesse ao canal de marketing &quot;Pesquisa paga&quot;, você poderia usar os detalhes do canal para ver qual mecanismo de pesquisa foi usado ou qual palavra-chave foi pesquisada.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das campanhas de marketing em áreas mais eficazes.</p><p>Esse modelo usa a dimensão Detalhes do canal de primeiro contato.</p> |
| [!UICONTROL **Canais de marketing**] > [!UICONTROL **Canal de último contato**] | Visualize o canal de marketing mais recente com o qual um visitante corresponde durante o período de envolvimento do visitante (30 dias por padrão).<p>**Isso pode ajudá-lo** a entender melhor quais canais de marketing direcionam o tráfego para o seu site que resulta em conversões.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das campanhas de marketing em áreas mais eficazes.</p><p>Esse modelo usa a dimensão Canal de último contato.  </p> |
| [!UICONTROL **Canais de marketing**] > [!UICONTROL **Detalhes do canal de último contato**] | Exibir detalhes sobre o canal de marketing mais recente com o qual um visitante corresponde durante o período de engajamento do visitante (30 dias por padrão)<p>**Isso pode ajudar** a entender melhor o que contribuiu para que a visita ocorresse por meio daquele canal de marketing. Por exemplo, se um visitante chegasse ao seu site e correspondesse ao canal de marketing &quot;Pesquisa paga&quot;, você poderia usar os detalhes do canal para ver qual mecanismo de pesquisa foi usado ou qual palavra-chave foi pesquisada.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das campanhas de marketing em áreas mais eficazes. </p><p>Esse modelo usa a dimensão Detalhe do canal de último contato. </p> |
| [!UICONTROL **Campanhas**] > [!UICONTROL **Funil de conversão de campanha**] | Veja o número de cliques e check-outs das suas campanhas. <p>**Isso pode ajudar** a entender melhor como as campanhas de marketing estão impulsionando a conversão.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como determinar quais campanhas de marketing estão gerando maior ROI.</p> |
| [!UICONTROL **Campanhas**] > [!UICONTROL **Desempenho da campanha**] | Veja os detalhes do desempenho das suas campanhas de marketing.<p>**Isso pode ajudar** a entender melhor os vários indicadores de sucesso associados às campanhas, como receita, exibições de produtos, pedidos e assim por diante.</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como concentrar esforços de marketing nas campanhas que geram mais receita. </p><p>Esse modelo usa a métrica Receita, Exibições do produto, Adições ao carrinho, Pedidos e Unidades. Ele também usa as dimensões “Código de rastreamento” e “Domínio de referência”. </p> |
| [!UICONTROL **Campanhas**] > [!UICONTROL **Código de rastreamento**] | Exiba os nomes dos códigos de rastreamento no site. Você pode colocar links com diferentes valores de parâmetro de sequência de consulta em diferentes lugares na Internet.<p>**Isso pode ajudá-lo** a entender melhor quais links foram os mais bem-sucedidos ao direcionar tráfego para o site. Anexar sequências de consulta de código de rastreamento é comum em emails, anúncios, publicações em redes sociais e outros esforços de marketing que sua organização usa</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como concentrar esforços de marketing nas campanhas que geram mais receita.</p><p>Esse modelo usa a dimensão Código de rastreamento. </p> |
| **Aquisição na web** | Veja como o seu site obtém visitantes.<p>**Isso pode ajudar** a entender melhor os vários fatores que levam à aquisição, como palavras-chave de pesquisa, domínio de referência e assim por diante.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das campanhas de marketing nos canais mais eficientes.</p><p>Esse modelo usa as métricas Taxa de rejeição e Rejeições. Ele também usa as dimensões “Mecanismo de pesquisa”, “Palavra-chave de pesquisa”, “Página de entrada”, “Domínio de referência”, “Código de rastreamento” e “Referenciador”.  </p> |
| **Aquisição por dispositivo móvel** | Veja como seu site obtém visitantes em dispositivos móveis.<p>**Isso pode ajudar** a entender melhor os vários fatores que levam à aquisição, como palavras-chave de pesquisa, domínio de referência e assim por diante.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das campanhas de marketing nos canais mais eficientes.</p><p>Esse modelo usa as métricas Taxa de rejeição e Rejeições. Ele também usa as dimensões “Mecanismo de pesquisa”, “Palavra-chave de pesquisa”, “Página de entrada”, “Domínio de referência”, “Código de rastreamento” e “Referenciador”.  </p> |
| **Advertising Analytics: pesquisa paga** | Visualize todos os dados de pesquisa paga do Google e do Bing lado a lado. <p>**Isso pode ajudar** a entender melhor a quantidade de tráfego que está sendo enviada para o site e se os clientes estão convertendo.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como estimar o custo/benefício de uma campanha publicitária.</p> |
| **Palavras-chave de pesquisa - todas** | Veja as palavras-chave de pesquisa que visitantes usam para acessar o seu site, sejam elas pagas ou naturais. <p>**Isso pode ajudar** a entender melhor as palavras-chave que as pessoas usam em pesquisas que geram tráfego para o site. </p><p>**Com base no que você aprende, é possível** fazer várias coisas, como identificar e preencher lacunas de SEO entre palavras-chave usadas e aquelas que direcionam o tráfego do site.</p><p>Esse modelo usa a dimensão Palavra-chave de pesquisa. </p> |
| **Palavras-chave de pesquisa - pagas** | Veja as palavras-chave de pesquisa que visitantes usam para acessar o seu site que correspondem à detecção de pesquisa paga.<p>**Isso pode ajudar** a entender melhor as palavras-chave que as pessoas usam em pesquisas que geram tráfego para o site.</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como identificar e preencher lacunas de SEO entre palavras-chave usadas e aquelas que direcionam o tráfego do site. </p><p>Esse modelo usa a dimensão Palavra-chave de pesquisa - Paga. </p> |
| **Palavras-chave de pesquisa - naturais** | Veja as palavras-chave de pesquisa que visitantes usam para acessar o seu site e que não correspondem à detecção de pesquisa paga.<p>**Isso pode ajudar** a entender melhor as palavras-chave que as pessoas usam em pesquisas que geram tráfego para o site.</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como identificar e preencher lacunas de SEO entre palavras-chave usadas e aquelas que direcionam o tráfego do site.</p><p>Esse modelo usa a dimensão Palavra-chave de pesquisa - Natural. </p> |
| **Mecanismos de pesquisa - todos** | Veja os mecanismos de pesquisa que visitantes usam para acessar o seu site, sejam elas pagas ou naturais. <p>**Isso pode ajudar** a entender melhor os mecanismos de pesquisa usados pelas pessoas que resultam em tráfego para o site. </p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco de SEO nos mecanismos de pesquisa que geram mais tráfego para o site.</p><p>Esse modelo usa a dimensão Mecanismo de pesquisa. </p> |
| **Mecanismos de pesquisa - pagos** | Veja os mecanismos de pesquisa que visitantes usam para acessar o seu site e que correspondem à detecção de pesquisa paga.<p>**Isso pode ajudar** a entender melhor os mecanismos de pesquisa usados pelas pessoas que resultam em tráfego para o site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco de SEO nos mecanismos de pesquisa que geram mais tráfego para o site. </p><p>Esse modelo usa a dimensão Mecanismo de pesquisa - Pago. </p> |
| **Mecanismos de pesquisa - naturais** | Veja as palavras-chave de pesquisa que visitantes usam para acessar o seu site e que não correspondem à detecção de pesquisa paga.<p>**Isso pode ajudar** a entender melhor os mecanismos de pesquisa usados pelas pessoas que resultam em tráfego para o site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco de SEO nos mecanismos de pesquisa que geram mais tráfego para o site.</p><p>Esse modelo usa a dimensão Mecanismo de pesquisa - Natural. </p> |
| **Toda a classificação da página de pesquisa** | Visualize em qual página dos resultados de pesquisa um visitante clicou para chegar ao seu site. Por exemplo, se o site for exibido na segunda página dos resultados de pesquisa de um mecanismo de pesquisa, o item de dimensão para essa variável será “Página de pesquisa 2”.<p>**Isso pode ajudar** a entender melhor a classificação das suas páginas em resultados de pesquisa.</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como melhorar sua estratégia de SEO para garantir que o conteúdo seja exibido na primeira página dos resultados da pesquisa. </p> |
| **Domínios de referência** | Veja em quais domínios as pessoas clicam para acessar o seu site.<p>**Isso pode ajudar** a entender quais sites de terceiros geram mais tráfego para o seu site. (Deve haver um link no site externo e o(a) visitante precisa clicar nele para que o item de dimensão seja exibido.)</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como criar ou ajustar o conteúdo para alinhar-se mais aos interesses dos visitantes provenientes dos principais domínios de referência. </p><p>Esse modelo usa a dimensão Domínio de referência. </p> |
| **Domínios de referência originais** | Veja o primeiro domínio referenciador no qual as pessoas clicam para acessar o seu site. (Depois de definido, ele mantém o mesmo valor por toda a vida útil da ID do(a) visitante em questão.)<p>**Isso pode ajudar** a entender melhor quais sites de terceiros originalmente geram tráfego para o seu site.</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como criar ou ajustar o conteúdo para alinhar-se mais aos interesses dos visitantes provenientes dos principais domínios de referência originais. </p><p>Esse modelo usa a dimensão Domínio de referência original. </p> |
| **Referenciadores** | Veja em quais URLs os(as) visitantes estavam quando clicaram para acessar o seu site. (Deve haver um link no URL externo e o(a) visitante precisa clicar nele para que o item de dimensão seja exibido.)  <p>**Isso pode ajudar** a entender quais URLs específicos geram mais tráfego para o seu site.</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como criar ou ajustar o conteúdo para alinhar-se mais aos interesses dos visitantes provenientes das principais URLs. </p><p>Este modelo usa a dimensão Domínio de referência </p><p>Esse modelo usa a dimensão Referenciador. </p> |
| **Tipos de referenciador** | Veja em quais canais genéricos os(as) visitantes clicaram para acessar o seu site. A Adobe mantém as regras de cada canal. Os possíveis canais incluem mecanismos de pesquisa, redes sociais, outros sites, disco rígido ou email.<p>**Isso pode ajudar** a entender melhor qual tipo de referenciador gera mais tráfego para o site.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como criar ou ajustar o conteúdo para alinhá-lo mais aos interesses dos visitantes que vêm de determinado canal.</p><p>Esse modelo usa a dimensão Tipo de referenciador.</p> |

## Modelos para dispositivos móveis

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileCarrierRankedReport"
>title="Veja a empresa de telecomunicação que fornece conectividade de rede celular aos dispositivos móveis que as pessoas usam para acessar o seu site."
>abstract="**Isso pode ajudar** a entender melhor quais operadoras de celular são mais usadas pela sua base de usuários.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como adaptar a entrega de conteúdo com base nos recursos de rede de diferentes operadoras para garantir uma experiência de usuário fluida.<br/>Este modelo usa a dimensão “Operadora de celular”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileDeviceNameRankedReport"
>title="Veja a marca e o modelo dos dispositivos móveis que as pessoas usam para acessar o seu site."
>abstract="**Isso pode ajudar** a entender melhor quais dispositivos móveis são mais usados pela sua base de usuários.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como otimizar a renderização do site para os dispositivos móveis mais comuns.<br/>Este modelo usa a dimensão “Nome do dispositivo móvel”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileDeviceTypeRankedReport"
>title="Veja os tipos de dispositivo móvel que as pessoas usam para acessar o seu site, como telefones e tablets."
>abstract="**Isso pode ajudar** a entender melhor os vários tipos de dispositivo móvel usados para acessar o seu site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como otimizar o site para os tipos de dispositivo móvel mais usados.<br/>Este modelo usa a dimensão “Tipo de dispositivo móvel”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileManufacturerRankedReport"
>title="Veja quais fabricantes produzem os dispositivos móveis que as pessoas usam para acessar o seu site, como Apple e Samsung."
>abstract="**Isso pode ajudar** a entender melhor quais fabricantes são mais usados pela sua base de usuários.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como adaptar a entrega de conteúdo com base nos recursos de diferentes fabricantes para garantir uma experiência de usuário fluida.<br/>Este modelo usa a dimensão “Fabricante do dispositivo móvel”."

<!-- markdownlint-enable MD034 -->

Os seguintes modelos estão disponíveis:

| Nome do modelo | Por que usar este modelo <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Operadora de celular**] | Veja a empresa de telecomunicação que fornece conectividade de rede celular aos dispositivos móveis que as pessoas usam para acessar o seu site.<p>**Isso pode ajudar** a entender melhor quais operadoras de celular são mais usadas pela sua base de usuários.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como adaptar a entrega de conteúdo com base nos recursos de rede de diferentes operadoras para garantir uma experiência de usuário fluida.</p><p>Esse modelo usa a dimensão Operadora de celular.</p> |
| **Dispositivos** | Veja a marca e o modelo dos dispositivos móveis que as pessoas usam para acessar o seu site.<p>**Isso pode ajudar** a entender melhor quais dispositivos móveis são mais usados pela sua base de usuários.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como otimizar a renderização do site para os dispositivos móveis mais comuns.</p><p>Esse modelo usa a dimensão Nome do dispositivo móvel.</p> |
| **Tipo de dispositivo** | Veja os tipos de dispositivo móvel que as pessoas usam para acessar o seu site, como telefones e tablets.<p>**Isso pode ajudar** a entender melhor os vários tipos de dispositivo móvel usados para acessar o seu site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como otimizar o site para os tipos de dispositivo móvel mais usados.</p><p>Esse modelo usa a dimensão Tipo de dispositivo móvel.</p> |
| **Fabricante** | Veja quais fabricantes produzem os dispositivos móveis que as pessoas usam para acessar o seu site, como Apple e Samsung.<p>**Isso pode ajudar** a entender melhor quais fabricantes são mais usados pela sua base de usuários.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como adaptar a entrega de conteúdo com base nos recursos de diferentes fabricantes para garantir uma experiência de usuário fluida.</p><p>Esse modelo usa a dimensão Fabricante do dispositivo móvel.</p> |
