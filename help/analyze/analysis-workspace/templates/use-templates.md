---
description: Uma visão geral de como usar modelos no Analysis Workspace.
title: Usar modelos
feature: Analysis Workspace
role: User, Admin
hide: true
hidefromtoc: true
source-git-commit: e98458a96e9950ffab40876b80a9e799a9182e6a
workflow-type: tm+mt
source-wordcount: '18051'
ht-degree: 58%

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

   ![Guia Relatórios](assets/view-prebuilt-reports.png)

1. Na seção [!UICONTROL **Modelos**], selecione uma das guias a seguir:

   * **[!UICONTROL modelos de Adobe]**: mostra todos os modelos fornecidos pelo Adobe.

   * **[!UICONTROL _login_company_name _modelos]**: mostra todos os modelos de empresa que foram criados para a em sua organização.

     Os modelos de empresa só podem ser criados por um administrador. Para obter mais informações sobre como criar um modelo de empresa, consulte [Criar e gerenciar modelos](/help/analyze/analysis-workspace/reports/create-company-reports.md).

1. Escolha se deseja exibir modelos em uma exibição de coluna ou em uma exibição de cartão selecionando o ícone exibição de coluna ![ícone de exibição de coluna](assets/column-view-icon.png) ou o ícone de exibição de cartão ![ícone de exibição de cartão](assets/card-view-icon.png).

1. No campo de pesquisa, comece digitando o nome do template que deseja localizar, em seguida, selecione-o na lista de templates. Também é possível pesquisar a lista de modelos por propriedade, eVar e número do evento. <!-- still true? -->

   Ou

   Selecione a categoria do modelo que deseja exibir e selecione o modelo na lista de modelos.

   >[!TIP]
   >
   >Para navegar no menu utilizando as teclas de seta, pressione a tecla Barra (/) e, em seguida, pressione a tecla Seta para baixo. Pressione Enter para carregar o modelo selecionado.

   Para obter uma lista de modelos disponíveis, consulte a seção [Modelos disponíveis](#available-reports) abaixo.

1. (Opcional) Visualize e use modelos que contêm componentes que não estão disponíveis em seu conjunto de relatórios. (Por padrão, os únicos modelos mostrados são aqueles que usam componentes disponíveis no conjunto de relatórios.) <!--does this apply to AA? -->

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

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--training"
>title="Modelo do tutorial de treinamento"
>abstract="Saiba mais sobre a terminologia e as etapas comuns do Analysis Workspace para criar a sua primeira análise."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--pagesRankedReport"
>title="Identifique as páginas mais e menos populares."
>abstract="**Isso pode ajudar** a entender melhor o seu público-alvo e o tipo de informação em que estão mais interessados(as).<br/>**Com base no que aprender, você poderá** fazer várias coisas, como ajustar metadados para aumentar a visibilidade de páginas menos visualizadas ou aprimorar o conteúdo das suas páginas mais visualizadas.<br/>Este modelo usa a dimensão “Página” e a métrica “Exibições da página”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--pageViewsOvertimeReport"
>title="Veja o número total de exibições da página. Os dados são mostrados durante um período e comparados com períodos anteriores. "
>abstract="**Isso pode ajudar** a entender melhor como o tráfego no site pode estar aumentando ou diminuindo com o tempo.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar a eficácia de uma campanha de marketing iniciada recentemente por comparar o tráfego do site antes e depois do início da campanha. Ou você pode comparar o tráfego em feriados de ano a ano.<br/>Este modelo usa a dimensão “Dia” e a métrica “Exibições da página”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--visitsOvertimeReport"
>title="Veja o número total de visitas. Os dados são mostrados durante um período e comparados com períodos anteriores."
>abstract="**Isso pode ajudar** a entender melhor como o tráfego no site pode estar aumentando ou diminuindo com o tempo.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar a eficácia de uma campanha de marketing iniciada recentemente por comparar o tráfego do site antes e depois do início da campanha. Ou você pode comparar o tráfego em feriados de ano a ano.<br/>Este modelo usa a dimensão “Dia” e a métrica “Visitas”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--visitorsOvertimeReport"
>title="Veja o número total de visitantes únicos. Os dados são mostrados durante um período e comparados com períodos anteriores. "
>abstract="**Isso pode ajudar** a entender melhor como o alcance e o tamanho do público-alvo do seu site estão aumentando ou diminuindo com o tempo ou em comparação com um período anterior.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar se uma campanha de marketing iniciada recentemente teve êxito ao atrair novas pessoas para o site, comparando o número de visitantes únicos antes e depois do início da campanha. Ou você pode comparar o número de pessoas que visitam o site durante os feriados a cada ano.<br/>Este modelo usa a dimensão “Dia” e a métrica “Visitantes únicos”. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--keyMetricsReport"
>title="Visualize um relatório que mostra as métricas de exibições da página, visitas e visitantes únicos lado a lado. Os dados são mostrados durante um período e comparados com períodos anteriores."
>abstract="**Isso pode ajudar** a comparar essas métricas importantes para obter uma visão mais completa do número de pessoas únicas que visitam o site, o número de vezes que as páginas foram visitadas e o número de sessões.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar o número médio de páginas que cada pessoa visualizou ao visitar o site em uma determinada semana ou mês, e como isso mudou durante certos períodos do ano ou antes e depois que as campanhas de marketing foram executadas. <br/>Este modelo usa a dimensão “Dia” e as métricas “Exibições da página”, “Visitas” e “Visitantes únicos”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--siteSectionRankedReport"
>title="Veja as seções mais populares ou de maior desempenho do seu site."
>abstract="**Isso pode ajudar** a entender melhor quais seções do site são mais visitadas.<br>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar quais produtos ou serviços fornecidos geram mais interesse.<br/>Este modelo usa a dimensão “Seção do site” e a métrica “Visitas”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--next-page-report"
>title="Veja os lugares mais comuns que as pessoas acessam imediatamente após ou antes de visitar um determinado lugar."
>abstract="**Isso pode ajudar** a entender como o tráfego passa de uma determinada página para outras partes do site e entender os caminhos que as pessoas percorrem para chegar a uma determinada página.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar se o design ou layout da página pode ser otimizado para direcionar as pessoas a páginas mais desejáveis, como uma página para fazer uma compra ou deixar uma avaliação. Ou avaliar se as informações na página atual fornecem a orientação ou as ações que as pessoas necessitam após acessarem as páginas anteriores. Ou você pode avaliar se as páginas que não aparecem como páginas anteriores precisam de links mais evidentes para a página atual.<br/>Este modelo usa o painel “Item seguinte ou anterior”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--campaignRankedReport"
>title="Veja os links que obtiveram mais êxito em gerar tráfego para o seu site."
>abstract="**Isso pode ajudar** a entender melhor quais códigos de rastreamento (e os links aos quais estão associados) foram os mais usados para acessar o seu site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como ajustar a sua estratégia para adicionar links para o seu site.<br/>Este modelo usa a dimensão “Código de rastreamento” e a métrica “Visitas”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--productsRankedReport"
>title="Veja o número de pedidos por produto. Os dados representam um determinado período."
>abstract="**Isso pode ajudar** a entender quais produtos têm a maior ou menor demanda.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como ajustar as estratégias de marketing para promover produtos de alto desempenho ou para melhorar ou descontinuar produtos de baixo desempenho. Você também pode ajustar o inventário de produtos com base na análise dos dados.<br/>Este modelo usa a dimensão “Produto” e a métrica “Pedidos”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--lastTouchChannelRankedReport"
>title="Veja os canais de marketing mais recentes utilizados por visitantes durante o período de engajamento (30 dias por padrão)."
>abstract="**Isso pode ajudar** a entender quais canais de marketing foram mais eficazes para trazer pessoas ao site que resultou em conversões.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como alocar mais recursos a canais de alto desempenho ou reduzir a alocação de recursos para canais de baixo desempenho.<br/>Este modelo usa a dimensão “Canal de último contato” e a métrica “Visitantes únicos”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--lastTouchChannelDetailRankedReport"
>title="Veja os detalhes dos canais de marketing mais recentes utilizados por visitantes durante o período de engajamento (30 dias por padrão)."
>abstract="**Isso pode ajudar** a entender quais canais de marketing foram mais eficazes para trazer pessoas ao site que resultou em conversões, bem como os detalhes desses canais de marketing. Por exemplo, se um visitante chegasse ao seu site e correspondesse ao canal de marketing &quot;Pesquisa paga&quot;, você poderia usar os detalhes do canal para ver qual mecanismo de pesquisa foi usado ou qual palavra-chave foi pesquisada.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como alocar mais recursos a canais de alto desempenho ou reduzir a alocação de recursos para canais de baixo desempenho.<br/>Este modelo usa a dimensão “Detalhes do canal de último contato” e a métrica “Visitantes únicos”. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--revenueOvertimeReport"
>title="Veja o valor monetário dos produtos comprados em todos os pedidos. Os dados são mostrados durante um período e comparados com períodos anteriores."
>abstract="**Isso pode ajudar** a entender como a receita está aumentando ou diminuindo com o tempo. É possível combinar essa métrica com qualquer dimensão para saber quais itens de dimensão contribuíram para a receita.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como projetar a receita futura com base nas tendências anteriores. Também é possível adicionar outra dimensão, como a dimensão “Código de rastreamento”, para saber quais campanhas estão gerando mais receita.<br/>Este modelo usa a dimensão “Dia” e a métrica “Receita”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--ordersOvertimeReport"
>title="Veja o número total de eventos de compra. Os dados são mostrados durante um período e comparados com períodos anteriores."
>abstract="**Isso pode ajudar** a entender melhor como o interesse pelos seus produtos e serviços está aumentando ou diminuindo com o tempo. Você pode aplicar um segmento para saber quais clientes ou regiões geográficas estão fazendo mais pedidos, e quais são as tendências desses pedidos ao longo do tempo.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar a eficácia de uma campanha de marketing iniciada recentemente por comparar os pedidos antes e depois do início da campanha. Ou você pode comparar os pedidos feitos durante feriados a cada ano.<br/>Este modelo usa a dimensão “Dia” e a métrica “Pedidos”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--unitsOvertimeReport"
>title="Exibir o número total de unidades compradas em todas as ordens. Os dados são mostrados durante um período e comparados com períodos anteriores."
>abstract="**Isso pode ajudá-lo** a entender melhor como as vendas de unidades estão aumentando ou diminuindo com o tempo. Você poderia aplicar um segmento para saber quais clientes ou regiões geográficas estão comprando mais unidades e como essas vendas de unidades estão em tendência ao longo do tempo.<br/>**Com base no que você aprendeu, é possível** executar várias ações, como avaliar a eficácia de uma campanha de marketing iniciada recentemente comparando as vendas de unidade antes e depois do lançamento da campanha. Ou você pode comparar as vendas de unidades ano a ano durante os feriados.<br/>Este modelo usa a dimensão Dia e a métrica Unidades."

<!-- markdownlint-enable MD034 -->

Os seguintes modelos estão disponíveis:

| Nome do modelo | Por que usar este modelo <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Tutorial de treinamento**] | Saiba mais sobre a terminologia e as etapas comuns do Analysis Workspace para criar sua primeira análise |
| [!UICONTROL **Páginas**] | <!--duplicated in Engagement section--> Identifique as páginas mais e menos populares. <p>**Isso pode ajudar** a entender melhor o seu público-alvo e o tipo de informação em que estão mais interessados(as).</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como ajustar metadados para aumentar a visibilidade de páginas menos visualizadas ou aprimorar o conteúdo das suas páginas mais visualizadas.</p><p>Este modelo usa a [dimensão de Página](/help/components/dimensions/page.md) e a [métrica de Exibições de Página](/help/components/metrics/page-views.md).</p> |
| [!UICONTROL **Exibições de página**] | <!--duplicated in Engagement section--> Veja o número total de exibições da página. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudar** a entender melhor como o tráfego no site pode estar aumentando ou diminuindo com o tempo.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar a eficácia de uma campanha de marketing iniciada recentemente por comparar o tráfego do site antes e depois do início da campanha. Ou você pode comparar o tráfego em feriados de ano a ano.</p><p>Este modelo usa a [dimensão de Dia](/help/components/dimensions/day.md) e a [métrica de Exibições de Página](/help/components/metrics/page-views.md).</p> |
| [!UICONTROL **Visitas**] | <!--duplicated in Engagement section--> Veja o número total de visitas. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudar** a entender melhor como o tráfego no site pode estar aumentando ou diminuindo com o tempo.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar a eficácia de uma campanha de marketing iniciada recentemente por comparar o tráfego do site antes e depois do início da campanha. Ou você pode comparar o tráfego em feriados de ano a ano.</p><p>Este modelo usa a [dimensão Dia](/help/components/dimensions/day.md) e a [métrica Visitas](/help/components/metrics/visits.md).</p> |
| [!UICONTROL **Visitantes**] | <!--duplicated in Engagement section--> Veja o número total de visitantes únicos. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudar** a entender melhor como o alcance e o tamanho do público-alvo do seu site estão aumentando ou diminuindo com o tempo ou em comparação com um período anterior.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar se uma campanha de marketing iniciada recentemente teve êxito ao atrair novas pessoas para o site, comparando o número de visitantes únicos antes e depois do início da campanha. Ou você pode comparar o número de pessoas que visitam o site durante os feriados a cada ano.</p><p>Este modelo usa a [dimensão Dia](/help/components/dimensions/day.md) e a [métrica Visitantes únicos](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Métricas principais**] | <!--duplicated in Engagement section--> Visualize um relatório que mostra as métricas de exibições da página, visitas e visitantes únicos lado a lado. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudar** a comparar essas métricas importantes para obter uma visão mais completa do número de pessoas únicas que visitam o site, o número de vezes que as páginas foram visitadas e o número de sessões.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como avaliar o número médio de páginas que cada pessoa visualizou ao visitar o site em uma determinada semana ou mês e como isso mudou durante certos períodos do ano ou antes e depois que as campanhas de marketing foram executadas. </p><p>Este modelo usa a [dimensão Dia](/help/components/dimensions/day.md), a [métrica Exibições da página](/help/components/metrics/page-views.md), a [métrica Visitas](/help/components/metrics/visits.md) e a [métrica Visitantes únicos](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Seções do site**] | Veja as seções mais populares ou de maior desempenho do seu site. <p>**Isso pode ajudar** a entender melhor quais seções do site são mais visitadas.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar quais produtos ou serviços fornecidos geram mais interesse.</p> <p>Este modelo usa a [dimensão Seção do site](/help/components/dimensions/site-section.md) e a [métrica Visitas](/help/components/metrics/visits.md).</p> |
| [!UICONTROL **Próxima Página e Página Anterior**] | Veja os lugares mais comuns que as pessoas acessam imediatamente após ou antes de visitar um determinado lugar. <p>**Isso pode ajudar** a entender como o tráfego passa de uma determinada página para outras partes do site e entender os caminhos que as pessoas percorrem para chegar a uma determinada página.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar se o design ou layout da página pode ser otimizado para direcionar as pessoas a páginas mais desejáveis, como uma página para fazer uma compra ou deixar uma avaliação. Ou avaliar se as informações na página atual fornecem a orientação ou as ações que as pessoas necessitam após acessarem as páginas anteriores. Ou você pode avaliar se as páginas que não aparecem como páginas anteriores precisam de links mais evidentes para a página atual.</p><p>Este modelo usa o [painel do item seguinte ou anterior](/help/analyze/analysis-workspace/c-panels/next-previous.md).</p> |
| [!UICONTROL **Campanhas (Código de rastreamento)**] | Veja os links que obtiveram mais êxito em gerar tráfego para o seu site. <p>**Isso pode ajudar** a entender melhor quais códigos de rastreamento (e os links aos quais estão associados) foram os mais usados para acessar o seu site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como ajustar a sua estratégia para adicionar links para o seu site.</p><p>Este modelo usa a [dimensão Código de rastreamento](/help/components/dimensions/tracking-code.md) e a [métrica Visitas](/help/components/metrics/visits.md).</p> |
| [!UICONTROL **Produtos**] | Veja o número de pedidos por produto. Os dados representam um determinado período. <p>**Isso pode ajudar** a entender quais produtos têm a maior ou menor demanda.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como ajustar as estratégias de marketing para promover produtos de alto desempenho ou para melhorar ou descontinuar produtos de baixo desempenho. Você também pode ajustar o inventário de produtos com base na análise dos dados.</p><p>Este modelo usa a [dimensão de Produto](/help/components/dimensions/product.md) e a [métrica Pedidos](/help/components/metrics/orders.md).</p> |
| [!UICONTROL **Canal de último contato**] | Veja os canais de marketing mais recentes utilizados por visitantes durante o período de engajamento (30 dias por padrão).<p>**Isso pode ajudar** a entender quais canais de marketing foram mais eficazes para trazer pessoas ao site que resultou em conversões.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como alocar mais recursos a canais de alto desempenho ou reduzir a alocação de recursos para canais de baixo desempenho.</p><p>Este modelo usa a [dimensão Canal de último contato](/help/components/dimensions/last-touch-channel.md) e a [métrica Visitantes únicos](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Detalhes do canal de último contato**] | Veja os detalhes dos canais de marketing mais recentes utilizados por visitantes durante o período de engajamento (30 dias por padrão).<p>**Isso pode ajudar** a entender quais canais de marketing foram mais eficazes para trazer pessoas ao site que resultou em conversões, bem como os detalhes desses canais de marketing. Por exemplo, se um visitante chegasse ao seu site e correspondesse ao canal de marketing &quot;Pesquisa paga&quot;, você poderia usar os detalhes do canal para ver qual mecanismo de pesquisa foi usado ou qual palavra-chave foi pesquisada.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como alocar mais recursos a canais de alto desempenho ou reduzir a alocação de recursos para canais de baixo desempenho.</p><p>Este modelo usa a [dimensão Detalhe do canal de último contato](/help/components/dimensions/last-touch-detail.md) e a [métrica Visitantes únicos](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Receita**] | Veja o valor monetário dos produtos comprados em todos os pedidos. Os dados são mostrados durante um período e comparados com períodos anteriores.<p>**Isso pode ajudar** a entender como a receita está aumentando ou diminuindo com o tempo. É possível combinar essa métrica com qualquer dimensão para saber quais itens de dimensão contribuíram para a receita.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como projetar a receita futura com base nas tendências anteriores. Também é possível adicionar outra dimensão, como a dimensão “Código de rastreamento”, para saber quais campanhas estão gerando mais receita.</p><p>Este modelo usa a [dimensão de Dia](/help/components/dimensions/day.md) e a [métrica de Receita](/help/components/metrics/revenue.md).</p> |
| [!UICONTROL **Pedidos**] | Veja o número total de eventos de compra. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudar** a entender melhor como o interesse pelos seus produtos e serviços está aumentando ou diminuindo com o tempo. Você pode aplicar um segmento para saber quais clientes ou regiões geográficas estão fazendo mais pedidos, e quais são as tendências desses pedidos ao longo do tempo.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar a eficácia de uma campanha de marketing iniciada recentemente por comparar os pedidos antes e depois do início da campanha. Ou você pode comparar os pedidos feitos durante feriados a cada ano.</p><p>Este modelo usa a [dimensão Dia](/help/components/dimensions/day.md) e a [métrica Pedidos](/help/components/metrics/orders.md).</p> |
| [!UICONTROL **Unidades**] | Exibir o número total de unidades compradas em todas as ordens. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudá-lo** a entender melhor como as vendas de unidades estão aumentando ou diminuindo com o tempo. Você poderia aplicar um segmento para saber quais clientes ou regiões geográficas estão comprando mais unidades e como essas vendas de unidades estão em tendência ao longo do tempo.</p><p>**Com base no que você aprendeu, é possível** executar várias ações, como avaliar a eficácia de uma campanha de marketing iniciada recentemente comparando as vendas de unidade antes e depois do lançamento da campanha. Ou você pode comparar as vendas de unidades ano a ano durante os feriados.</p><p>Este modelo usa a [dimensão de Dia](/help/components/dimensions/day.md) e a [métrica de Unidades](/help/components/metrics/units.md).</p> |

### Engajamento {#web-engagement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timeSpentVisitOvertimeReport"
>title="Visualize o tempo médio que os visitantes gastam no site durante cada visita. Os dados são mostrados durante um período e comparados com períodos anteriores."
>abstract="**Isso pode ajudá-lo** a entender melhor os níveis de envolvimento do visitante e quanto tempo os visitantes estão gastando no site.<br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como avaliar se as alterações no site resultam em visitantes que passam mais tempo no site.<br/>Este modelo usa a dimensão Dia e a métrica Tempo gasto por visita (segundos)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timePriorRankedReport"
>title="Visualize o tempo médio que os usuários gastam antes de um evento bem-sucedido."
>abstract="**Isso pode ajudá-lo** a entender melhor quanto tempo os visitantes levam para executar uma ação desejada, como fazer uma compra.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar se as alterações no site melhoram a possibilidade dos visitantes gerarem rapidamente um evento bem-sucedido.<br/>Este modelo usa a dimensão Tempo antes do evento e a métrica Visitantes únicos."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--web-content-consumption"
>title="Veja qual conteúdo da web é mais consumido e gera mais engajamento pelos usuários."
>abstract="**Isso pode ajudar** a entender melhor o que as pessoas acessam ao entrar pela primeira vez no site, quais seções do site são mais visitadas e quais páginas tendem a afastar as pessoas do site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar quais caminhos no site direcionam as pessoas às páginas mais importantes e quais páginas têm a maior probabilidade de afastá-las do site.<br/>Este modelo usa a dimensão “Página” e as métricas “Exibições da página”, “Visitas”, “Visitantes únicos”, “Taxa de entrada”, “Taxa de rejeição”, “Taxa de saída” e “Velocidade do conteúdo”. Ele também usa visualizações de fluxo para as seções de entrada, saída e a seção superior."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--media-content-consumption"
>title="Veja qual conteúdo de mídia é mais consumido e gera mais engajamento pelos usuários."
>abstract="**Isso pode ajudar** a entender melhor o que as pessoas acessam ao entrar pela primeira vez no site, quais seções do site são mais visitadas e quais páginas tendem a afastar as pessoas do site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar quais caminhos no site direcionam as pessoas às páginas mais importantes e quais páginas têm a maior probabilidade de afastá-las do site.<br/>Este modelo usa a dimensão “Página” e as métricas “Exibições da página”, “Visitas”, “Visitantes únicos”, “Taxa de entrada”, “Taxa de rejeição”, “Taxa de saída” e “Velocidade do conteúdo”. Ele também usa visualizações de fluxo para as seções de entrada, saída e a seção superior; uma visualização do gráfico de dispersão, que mostra as exibições das páginas mais comuns; uma visualização de barras, que mostra as exibições da página por tempo classificado; e uma visualização de linhas, que mostra uma exibição das tendências do tempo médio no site."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--falloutReport"
>title="Visualização de onde as pessoas saem ou continuam por meio de uma sequência predefinida de páginas."
>abstract="**Isso pode ajudá-lo** a entender melhor de onde as pessoas estão saindo da jornada do usuário.<br/>**Com base no que você aprendeu, é possível** executar várias ações, como analisar taxas de conversão por meio de processos específicos no site (como um processo de compra ou registro) ou analisar correlações entre eventos no site. (Por exemplo, que porcentagem das pessoas que observaram sua política de privacidade compraram um produto.) Você também pode usar esse template para fazer comparações lado a lado de dois segmentos diferentes no mesmo relatório.<br/>Este modelo usa a visualização de Fallout."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--cross-device-analysis"
>title="Visualize quais dispositivos as pessoas usaram em todos os pontos da jornada."
>abstract="**Isso pode ajudá-lo** a entender melhor quantas pessoas interagem com a sua marca, os tipos de dispositivos que usam e como o uso de vários dispositivos afeta sua experiência. Por exemplo, com que frequência as pessoas iniciam uma tarefa em um dispositivo móvel e depois movem para um desktop para concluir uma tarefa? Quais são os caminhos mais comuns que os usuários fazem de um dispositivo para outro? Onde eles desistem? Onde eles têm sucesso? E assim por diante.<br/>**Com base no que você aprendeu, você pode** fazer várias coisas, como otimizar determinadas partes da jornada do usuário para uma experiência móvel.<br/>Este modelo usa a Visualização de fluxo, a Visualização de fallout, a Análise de coorte, a métrica de Pessoas e a métrica Dispositivos exclusivos."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--web-retention"
>title="Visualize quem são seus usuários fiéis e o que eles estão fazendo em seu site."
>abstract="**Isso pode ajudá-lo** a entender melhor o número de vezes que a pessoa média visita seu site, a frequência com que as pessoas retornam ao site e o número de dias entre visitas recorrentes.<br/>**Com base no que você aprendeu, é possível** executar várias ações, como analisar qual conteúdo é mais eficiente para trazer pessoas de volta ao site.<br/>Este modelo usa as métricas Visitas e Visitantes únicos."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--audio-consumption-template"
>title="Veja as tendências e as principais métricas de consumo de áudio de mídia em todos os dispositivos digitais."
>abstract="**Isso pode ajudá-lo** a entender melhor como os visitantes estão consumindo conteúdo de áudio no site.<br/>**Com base no que você aprendeu, é possível** executar várias ações, como analisar qual conteúdo está sendo mais consumido.<br/>Este modelo usa as métricas Visitas e Visitantes únicos."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--media-recency-frequency-loyalty"
>title="Veja as tendências e as principais métricas de consumo de mídia em todos os dispositivos digitais."
>abstract="**Isso pode ajudá-lo** a entender melhor o número de vezes que a pessoa média visita seu site, a frequência com que as pessoas retornam ao site e o número de dias entre visitas recorrentes.<br/>**Com base no que você aprendeu, é possível** executar várias ações, como analisar qual conteúdo é mais eficiente para trazer pessoas de volta ao site.<br/>Este modelo usa as métricas Visitas e Visitantes únicos."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--page-summary-report"
>title="Visualize o tempo médio que os visitantes gastam no site durante cada visita. Os dados são mostrados durante um período e comparados com períodos anteriores."
>abstract="**Isso pode ajudá-lo** a entender melhor os níveis de envolvimento do visitante e quanto tempo os visitantes estão gastando no site.<br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como avaliar se as alterações no site resultam em visitantes que passam mais tempo no site.<br/>Este modelo usa a dimensão Dia e a métrica Tempo gasto por visita (segundos)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--reloadsRankedReport"
>title="Visualize o número de vezes que um item de dimensão foi apresentado durante um recarregamento. A atualização do navegador por um visitante é a maneira mais comum de acionar um recarregamento."
>abstract="**Isso pode ajudá-lo** a identificar quando podem estar ocorrendo problemas em uma determinada página que poderia solicitar que um visitante recarregasse a página.<br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como avaliar quais páginas têm problemas que precisam ser resolvidos.<br/>Este modelo usa a métrica Recarregamentos."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timeSpentPageRankedReport"
>title="Visualize o tempo médio que os visitantes gastam no site durante cada visita. Os dados são mostrados durante um período e comparados com períodos anteriores."
>abstract="**Isso pode ajudá-lo** a entender melhor os níveis de envolvimento do visitante e quanto tempo os visitantes estão gastando no site.<br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como avaliar se as alterações no site resultam em visitantes que passam mais tempo no site.<br/>Este modelo usa a dimensão Dia e a métrica Tempo gasto por visita (segundos)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--entryPageRankedReport"
>title="Veja as principais páginas que as pessoas acessam quando visitam o site pela primeira vez."
>abstract="**Isso pode ajudar** a saber quais páginas estão gerando mais tráfego para o site ou entender melhor as primeiras impressões que visitantes têm sobre o site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como otimizar a experiência inicial que as pessoas têm no site ou garantir que as páginas que as pessoas veem ao entrar no site sejam acolhedoras e forneçam os links necessários para outras áreas do site.<br/>Este modelo usa a métrica “Sessões”. Ele também usa a visualização de barras e a visualização de tabela de forma livre."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--entryPageOriginalRankedReport"
>title="Visualize as principais páginas que as pessoas acessam quando visitam o site pela primeira vez durante a vida útil de um visitante."
>abstract="**Isso pode ajudar** a saber quais páginas estão gerando mais tráfego para o site ou entender melhor as primeiras impressões que visitantes têm sobre o site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como otimizar a experiência inicial que as pessoas têm no site ou garantir que as páginas que as pessoas veem ao entrar no site sejam acolhedoras e forneçam os links necessários para outras áreas do site.<br/>Este modelo usa a métrica “Sessões”. Ele também usa a visualização de barras e a visualização de tabela de forma livre."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--singlePageVisitsRankedReport"
>title="Visualize o número de visitas que consistiam de uma única página única."
>abstract="**Isso pode ajudá-lo** a entender melhor os níveis de envolvimento do visitante e quanto tempo os visitantes estão gastando no site.<br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como avaliar se as alterações no site resultam em visitantes que passam mais tempo no site.<br/>Este modelo usa a dimensão Visitas em única página."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--exitPageRankedReport"
>title="Veja as principais páginas que as pessoas acessam imediatamente antes de sair do site."
>abstract="**Isso pode ajudar** a entender melhor quais páginas estão afastando as pessoas do site. <br/>**Com base no que aprender, você poderá** fazer várias coisas, como atualizar as páginas de saída comuns para otimizar a experiência que as pessoas têm antes de sair ou incluir conteúdo ou links para incentivar as pessoas a permanecerem no site.<br/>Este modelo usa a métrica “Sessões”. Ele também usa a visualização de barras e a visualização de tabela de forma livre."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--sitePerformanceOverview"
>title="Exibir dados de desempenho do site do Adobe Experience Manager."
>abstract="**Isso pode ajudá-lo** a entender melhor a realização de valores da Adobe Experience Manager.<br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como otimizar as configurações de Experience Manager."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--itp-impact"
>title="Visualize e analise os efeitos da Prevenção de Rastreamento Inteligente (ITP) na coleta de dados e nos relatórios."
>abstract="**Isso pode ajudá-lo** a entender melhor a possível perda de dados devido a restrições de cookies impostas pela ITP.<br/>**Com base no que você aprende, é possível** executar várias ações, como adaptar a configuração de análise para minimizar o impacto da ITP."

<!-- markdownlint-enable MD034 -->

Os seguintes modelos estão disponíveis:

| Nome do modelo | Por que usar este modelo <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Métricas principais**] | <!--duplicated in Most popular section--> Visualize um relatório que mostra as métricas de exibições da página, visitas e visitantes únicos lado a lado. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudar** a comparar essas métricas importantes para obter uma visão mais completa do número de pessoas únicas que visitam o site, o número de vezes que as páginas foram visitadas e o número de sessões.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como avaliar o número médio de páginas que cada pessoa visualizou ao visitar o site em uma determinada semana ou mês e como isso mudou durante certos períodos do ano ou antes e depois que as campanhas de marketing foram executadas. </p><p>Este modelo usa a [dimensão Dia](/help/components/dimensions/day.md), a [métrica Exibições da página](/help/components/metrics/page-views.md), a [métrica Visitas](/help/components/metrics/visits.md) e a [métrica Visitantes únicos](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Exibições de página**] | <!--duplicated in Most popular section-->Veja o número total de exibições da página. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudar** a entender melhor como o tráfego no site pode estar aumentando ou diminuindo com o tempo.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar a eficácia de uma campanha de marketing iniciada recentemente por comparar o tráfego do site antes e depois do início da campanha. Ou você pode comparar o tráfego em feriados de ano a ano.</p><p>Este modelo usa a [dimensão de Dia](/help/components/dimensions/day.md) e a [métrica de Exibições de Página](/help/components/metrics/page-views.md).</p> |
| [!UICONTROL **Páginas**] | <!--duplicated in Most popular section-->Identifique as páginas mais e menos populares. <p>**Isso pode ajudar** a entender melhor o seu público-alvo e o tipo de informação em que estão mais interessados(as).</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como ajustar metadados para aumentar a visibilidade de páginas menos visualizadas ou aprimorar o conteúdo das suas páginas mais visualizadas.</p><p>Este modelo usa a [dimensão de Página](/help/components/dimensions/page.md) e a [métrica de Exibições de Página](/help/components/metrics/page-views.md).</p> |
| [!UICONTROL **Visitas**] | <!--duplicated in Most popular section-->Veja o número total de visitas. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudar** a entender melhor como o tráfego no site pode estar aumentando ou diminuindo com o tempo.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar a eficácia de uma campanha de marketing iniciada recentemente por comparar o tráfego do site antes e depois do início da campanha. Ou você pode comparar o tráfego em feriados de ano a ano.</p><p>Este modelo usa a [dimensão Dia](/help/components/dimensions/day.md) e a [métrica Visitas](/help/components/metrics/visits.md).</p> |
| [!UICONTROL **Visitantes**] | <!--duplicated in Most popular section-->Veja o número total de visitantes únicos. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudar** a entender melhor como o alcance e o tamanho do público-alvo do seu site estão aumentando ou diminuindo com o tempo ou em comparação com um período anterior.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar se uma campanha de marketing iniciada recentemente teve êxito ao atrair novas pessoas para o site, comparando o número de visitantes únicos antes e depois do início da campanha. Ou você pode comparar o número de pessoas que visitam o site durante os feriados a cada ano.</p><p>Este modelo usa a [dimensão Dia](/help/components/dimensions/day.md) e a [métrica Visitantes únicos](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Tempo gasto por visita**] | Visualize o tempo médio que os visitantes gastam no site durante cada visita. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudá-lo** a entender melhor os níveis de envolvimento do visitante e quanto tempo os visitantes estão gastando no site.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como avaliar se as alterações no site resultam em visitantes que passam mais tempo no site.</p><p>Este modelo usa a [dimensão de Dia](/help/components/dimensions/day.md) e a [métrica Tempo gasto por visita (segundos)](/help/components/metrics/time-spent-per-visit.md).</p> |
| [!UICONTROL **Tempo antes do evento**] | Visualize o tempo médio que os usuários gastam antes de um evento bem-sucedido. <p>**Isso pode ajudá-lo** a entender melhor quanto tempo os visitantes levam para executar uma ação desejada, como fazer uma compra.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar se as alterações no site melhoram a possibilidade dos visitantes gerarem rapidamente um evento bem-sucedido.</p><p>Este modelo usa a [dimensão Tempo antes do evento](/help/components/dimensions/time-prior-to-event.md) e a [métrica Visitantes únicos](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Seções do site**] | <!--duplicated in Most popular section-->Veja as seções mais populares ou de maior desempenho do seu site. <p>**Isso pode ajudar** a entender melhor quais seções do site são mais visitadas.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar quais produtos ou serviços fornecidos geram mais interesse.</p> <p>Este modelo usa a [dimensão Seção do site](/help/components/dimensions/site-section.md) e a [métrica Visitas](/help/components/metrics/visits.md).</p> |
| [!UICONTROL **Tempo real**] | Visualize as dimensões e métricas que estão sendo coletadas no site. <p>**Isso pode ajudá-lo** a entender melhor as tendências do seu site.</p><p>**Com base no que você aprendeu, talvez** você responda e gerencie ativamente o desempenho de suas campanhas e conteúdo de marketing atuais.</p> <p>Este modelo usa o [Relatório em tempo real](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md).</p> |
| [!UICONTROL **Consumo de conteúdo da Web**] | Veja qual conteúdo da web é mais consumido e gera mais engajamento pelos usuários.<p>**Isso pode ajudar** a entender melhor o que as pessoas acessam ao entrar pela primeira vez no site, quais seções do site são mais visitadas e quais páginas tendem a afastar as pessoas do site.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como avaliar quais caminhos no site direcionam as pessoas para as páginas mais importantes e quais páginas têm maior probabilidade de afastar as pessoas do site <!-- not sure about these takeaways... -->.</p> <p>Este modelo usa a [dimensão da Página](/help/components/dimensions/page.md) e a [métrica de Exibições da Página](/help/components/metrics/page-views.md), a [métrica de Visitas](/help/components/metrics/visits.md), a [métrica de Visitantes Únicos](/help/components/metrics/unique-visitors.md), a [métrica de Taxa de Entrada](/help/components/metrics/entries.md), a [métrica de Taxa de Devolução](/help/components/metrics/bounce-rate.md), a [métrica de Taxa de Saída](/help/components/metrics/exits.md) e a [métrica de Velocidade do Conteúdo](/help/components/metrics/content-velocity.md). Também usa [Visualizações de fluxo](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) para seções de entrada, saída e superior.</p> |
| [!UICONTROL **Consumo de conteúdo de mídia**] | Veja qual conteúdo de mídia é mais consumido e gera mais engajamento pelos usuários.<p>**Isso pode ajudar** a entender melhor o que as pessoas acessam ao entrar pela primeira vez no site, quais seções do site são mais visitadas e quais páginas tendem a afastar as pessoas do site.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como avaliar quais caminhos no site direcionam as pessoas para as páginas mais importantes e quais páginas têm maior probabilidade de afastar as pessoas do site <!-- not sure about these takeaways... -->.</p> <p>Este modelo usa a [dimensão da Página](/help/components/dimensions/page.md) e a [métrica de Exibições da Página](/help/components/metrics/page-views.md), a [métrica de Visitas](/help/components/metrics/visits.md), a [métrica de Visitantes Únicos](/help/components/metrics/unique-visitors.md), a [métrica de Taxa de Entrada](/help/components/metrics/entries.md), a [métrica de Taxa de Devolução](/help/components/metrics/bounce-rate.md), a [métrica de Taxa de Saída](/help/components/metrics/exits.md) e a [métrica de Velocidade do Conteúdo](/help/components/metrics/content-velocity.md). Ele também usa [Visualizações de fluxo](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) para seções de entrada, saída e superior; uma [Visualização de gráfico de barras](/help/analyze/analysis-workspace/visualizations/scatterplot.md) que mostra exibições de página para as páginas mais comuns; uma [Visualização de barras](/help/analyze/analysis-workspace/visualizations/bar.md) que mostra exibições de página por tempo reduzido; e uma [Visualização de linhas](/help/analyze/analysis-workspace/visualizations/line.md) que mostra uma exibição de tendência do tempo médio gasto no site.</p> |
| [!UICONTROL **Fluxo da página seguinte e anterior**] | Veja os lugares mais comuns que as pessoas visitam antes ou depois de visitar um determinado lugar.<p>**Isso pode ajudá-lo** a entender melhor onde as pessoas entram pela primeira vez no site, quais seções das pessoas estão mais visitando e quais páginas têm maior probabilidade de visitar antes de sair do site.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como avaliar quais caminhos no site direcionam as pessoas para as páginas mais importantes e quais páginas têm maior probabilidade de afastar as pessoas do site <!-- not sure about these takeaways... -->.</p> <p>Este modelo usa a [dimensão da Página](/help/components/dimensions/page.md) e a [métrica de Exibições da Página](/help/components/metrics/page-views.md), a [métrica de Visitas](/help/components/metrics/visits.md), a [métrica de Visitantes Únicos](/help/components/metrics/unique-visitors.md), a [métrica de Taxa de Entrada](/help/components/metrics/entries.md), a [métrica de Taxa de Devolução](/help/components/metrics/bounce-rate.md), a [métrica de Taxa de Saída](/help/components/metrics/exits.md) e a [métrica de Velocidade do Conteúdo](/help/components/metrics/content-velocity.md). Ele também usa [Visualizações de fluxo](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) para seções de entrada, saída e superior; uma [Visualização de gráfico de dispersão](/help/analyze/analysis-workspace/visualizations/scatterplot.md) que mostra exibições de página para as páginas mais comuns; uma [Visualização de barra](/help/analyze/analysis-workspace/visualizations/bar.md) que mostra exibições de página por tempo reduzido; e uma [Visualização de linha](/help/analyze/analysis-workspace/visualizations/line.md) que mostra uma exibição de tendência do tempo médio gasto no site.</p> |
| [!UICONTROL **Fallout**] | Visualização de onde as pessoas saem ou continuam por meio de uma sequência predefinida de páginas.<p>**Isso pode ajudá-lo** a entender melhor de onde as pessoas estão saindo da jornada do usuário.</p><p>**Com base no que você aprendeu, é possível** executar várias ações, como analisar taxas de conversão por meio de processos específicos no site (como um processo de compra ou registro) ou analisar correlações entre eventos no site. (Por exemplo, que porcentagem das pessoas que observaram sua política de privacidade compraram um produto.) Você também pode usar esse template para fazer comparações lado a lado de dois segmentos diferentes no mesmo relatório.</p> <p>Este modelo usa a [Visualização de fallout](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md).</p> |
| [!UICONTROL **Análise entre dispositivos**] | Visualize quais dispositivos as pessoas usaram em todos os pontos da jornada.<p>**Isso pode ajudá-lo** a entender melhor quantas pessoas interagem com a sua marca, os tipos de dispositivos que usam e como o uso de vários dispositivos afeta sua experiência. Por exemplo, com que frequência as pessoas iniciam uma tarefa em um dispositivo móvel e depois movem para um desktop para concluir uma tarefa? Quais são os caminhos mais comuns que os usuários fazem de um dispositivo para outro? Onde eles desistem? Onde eles têm sucesso? E assim por diante.</p><p>**Com base no que você aprendeu, você pode** fazer várias coisas, como otimizar determinadas partes da jornada do usuário para uma experiência móvel.</p> <p>Este modelo usa a [Visualização de fluxo](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md), [Visualização de fallout](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md), [Análise de coorte](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md), [a métrica de Pessoas](/help/components/metrics/people.md) e [a métrica Dispositivos exclusivos](/help/components/metrics/unique-devices.md).</p> |
| [!UICONTROL **Retenção da Web**] | Visualize quem são seus usuários fiéis e o que eles estão fazendo em seu site.<p>**Isso pode ajudá-lo** a entender melhor o número de vezes que a pessoa média visita seu site, a frequência com que as pessoas retornam ao site e o número de dias entre visitas recorrentes.</p><p>**Com base no que você aprendeu, é possível** executar várias ações, como analisar qual conteúdo é mais eficiente para trazer pessoas de volta ao site.<p>Este modelo usa a [métrica Visitas](/help/components/metrics/visits.md) e a [métrica Visitantes únicos](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Consumo de Áudio de Mídia**] | Veja as tendências e as principais métricas de consumo de áudio de mídia em todos os dispositivos digitais.<p>**Isso pode ajudá-lo** a entender melhor como os visitantes estão consumindo conteúdo de áudio no site.</p><p>**Com base no que você aprendeu, é possível** executar várias ações, como analisar qual conteúdo está sendo mais consumido.<p>Este modelo usa a [métrica Visitas](/help/components/metrics/visits.md) e a [métrica Visitantes únicos](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Recenticidade, Frequência, Fidelidade de Mídia**] | Veja as tendências e as principais métricas de consumo de mídia em todos os dispositivos digitais.<p>**Isso pode ajudá-lo** a entender melhor o número de vezes que a pessoa média visita seu site, a frequência com que as pessoas retornam ao site e o número de dias entre visitas recorrentes.</p><p>**Com base no que você aprendeu, é possível** executar várias ações, como analisar qual conteúdo é mais eficiente para trazer pessoas de volta ao site.<p>Este modelo usa a [métrica Visitas](/help/components/metrics/visits.md) e a [métrica Visitantes únicos](/help/components/metrics/unique-visitors.md).</p> |
| **[!UICONTROL Análise de Página]** > [!UICONTROL **Resumo da Página**] | Visualize o tempo médio que os visitantes gastam no site durante cada visita. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudá-lo** a entender melhor os níveis de envolvimento do visitante e quanto tempo os visitantes estão gastando no site.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como avaliar se as alterações no site resultam em visitantes que passam mais tempo no site.</p><p>Este modelo usa a [dimensão de Dia](/help/components/dimensions/day.md) e a [métrica Tempo gasto por visita (segundos)](/help/components/metrics/time-spent-per-visit.md).</p> |
| **[!UICONTROL Análise de Página]** > [!UICONTROL **Recargas**] | Visualize o número de vezes que um item de dimensão foi apresentado durante um recarregamento. A atualização do navegador por um visitante é a maneira mais comum de acionar um recarregamento. <p>**Isso pode ajudá-lo** a identificar quando podem estar ocorrendo problemas em uma determinada página que poderia solicitar que um visitante recarregasse a página.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como avaliar quais páginas têm problemas que precisam ser resolvidos.</p><p>Este modelo usa a [métrica Recargas](https://experienceleague.adobe.com/en/docs/analytics/components/metrics/reloads).</p> |
| **[!UICONTROL Análise de Página]** > [!UICONTROL **Tempo gasto na página**] | Visualize o tempo médio que os visitantes gastam no site durante cada visita. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudá-lo** a entender melhor os níveis de envolvimento do visitante e quanto tempo os visitantes estão gastando no site.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como avaliar se as alterações no site resultam em visitantes que passam mais tempo no site.</p><p>Este modelo usa a [dimensão de Dia](/help/components/dimensions/day.md) e a [métrica Tempo gasto por visita (segundos)](/help/components/metrics/time-spent-per-visit.md).</p> |
| **[!UICONTROL Entradas e Saídas]** > [!UICONTROL **Páginas de Entrada**] | Visualize as principais páginas que as pessoas acessam quando visitam o site pela primeira vez em uma determinada sessão. <p>**Isso pode ajudar** a saber quais páginas estão gerando mais tráfego para o site ou entender melhor as primeiras impressões que visitantes têm sobre o site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como otimizar a experiência inicial que as pessoas têm no site ou garantir que as páginas que as pessoas veem ao entrar no site sejam acolhedoras e forneçam os links necessários para outras áreas do site.</p><p>Este modelo usa a métrica Sessões. Ele também usa a visualização de barras e a visualização de tabela de forma livre.</p> |
| **[!UICONTROL Entradas e Saídas]** > [!UICONTROL **Páginas de Entrada Originais**] | Visualize as principais páginas que as pessoas acessam quando visitam o site pela primeira vez durante a vida útil de um visitante. <p>**Isso pode ajudar** a saber quais páginas estão gerando mais tráfego para o site ou entender melhor as primeiras impressões que visitantes têm sobre o site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como otimizar a experiência inicial que as pessoas têm no site ou garantir que as páginas que as pessoas veem ao entrar no site sejam acolhedoras e forneçam os links necessários para outras áreas do site.</p><p>Este modelo usa a métrica Sessões. Ele também usa a visualização de barras e a visualização de tabela de forma livre.</p> |
| **[!UICONTROL Entradas e Saídas]** > [!UICONTROL **Visitas em Única Página**] | Visualize o número de visitas que consistiam de uma única página única. <p>**Isso pode ajudá-lo** a entender melhor os níveis de envolvimento do visitante e quanto tempo os visitantes estão gastando no site.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como avaliar se as alterações no site resultam em visitantes que passam mais tempo no site.</p><p>Este modelo usa a [dimensão Visitas em única página](https://experienceleague.adobe.com/en/docs/analytics/components/dimensions/single-page-visits).</p> |
| **[!UICONTROL Entradas e Saídas]** > [!UICONTROL **Páginas de Saída**] | Veja as principais páginas que as pessoas acessam imediatamente antes de sair do site.<p>**Isso pode ajudá-lo** a entender melhor quais páginas estão afastando as pessoas do site. </p><p>**Com base no que aprender, você poderá** fazer várias coisas, como atualizar as páginas de saída comuns para otimizar a experiência que as pessoas têm antes de sair ou incluir conteúdo ou links para incentivar as pessoas a permanecerem no site.</p><p>Este modelo usa a métrica Sessões. Ele também usa a visualização de barras e a visualização de tabela de forma livre.</p> |
| [!UICONTROL **AEM**] > [!UICONTROL **Desempenho do Site**] > [!UICONTROL **Desempenho do Site AEM**] | Exibir dados de desempenho do site do Adobe Experience Manager.  <p>**Isso pode ajudá-lo** a entender melhor a realização de valores da Adobe Experience Manager.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como otimizar as configurações de Experience Manager.</p> |
| [!UICONTROL **Impacto da ITP**] | Visualize e analise os efeitos da Prevenção de Rastreamento Inteligente (ITP) na coleta de dados e nos relatórios. <p>**Isso pode ajudá-lo** a entender melhor a possível perda de dados devido a restrições de cookies impostas pela ITP.</p><p>**Com base no que você aprende, é possível** executar várias ações, como adaptar a configuração de análise para minimizar o impacto da ITP.</p> |




Ignorar abaixo deste

| Item de menu | Relatórios neste item de menu |
| --- | --- | 
| **[!UICONTROL Mais populares]** | <ul><li>Tutorial de treinamento (modelo do Workspace pré-existente)</li><li>Páginas (quais são minhas páginas principais?)</li><li>Visualizações de página (quantas visualizações de página estou gerando?)</li><li>Visitas (quantas visitas estou recebendo?)</li><li>Visitantes (quantos visitantes estou recebendo?)</li><li>Métricas principais (qual é o desempenho das minhas métricas mais importantes?)</li><li>Seções do site (quais seções do meu site geraram mais visualizações de página?)</li><li>Tempo real (quais são as tendências no meu site e por quê?)</li><li>Próxima página (quais são as próximas páginas que meus visitantes acessam?)</li><li>Página anterior (quais são as páginas anteriores que meus visitantes acessaram?)</li><li>Campanhas (que campanhas estão gerando minhas métricas principais?)</li><li>Produtos (que produtos estão acionando minhas métricas principais?)</li><li>Canal de último contato (qual canal de último contato tem melhor desempenho?</li><li>Detalhe do canal de último contato (qual canal de último contato específico está superando outros?)</li><li>Receita (como está o desempenho da minha receita?)</li><li>Pedidos (como está o desempenho dos meus pedidos?)</li><li>Unidades (quantas unidades estou vendendo?)</li></ul> |
| **[!UICONTROL Engajamento]** | <ul><li>Métricas principais (qual é o desempenho das minhas métricas mais importantes?)</li><li>Visualizações de página (quantas visualizações de página estou gerando?)</li><li>Páginas (quais são minhas páginas principais?)</li><li>Visitas (quantas visitas estou recebendo?)</li><li>Visitantes (quantos visitantes estou recebendo?)</li><li>Tempo gasto por visita (quanto tempo meus usuários gastam por visita?)</li><li>Tempo antes do evento (quanto tempo meus usuários gastam antes de um evento bem-sucedido?)</li><li>Seções do site (quais seções do meu site geraram mais visualizações de página?)</li><li>Consumo de conteúdo da Web (qual conteúdo é mais consumido e envolve os usuários?)</li><li>Consumo de conteúdo de mídia (qual conteúdo é mais consumido e envolve os usuários?)</li><li>Fluxo da página seguinte e anterior (quais são/foram os caminhos anteriores/seguintes que meus visitantes tomaram?)</li><li>Fallout (onde estou vendo fallout em minhas propriedades digitais?)</li><li>Análise entre dispositivos (usando análise entre dispositivos no Analysis Workspace)</li><li>Retenção da Web (quem são meus usuários fiéis e o que eles fazem?)</li><li>Consumo de áudio de mídia (quais são as tendências e as métricas principais do consumo de áudio?)</li><li>Recenticidade de mídia, frequência, fidelidade (quem são meus leitores fiéis?)</li><li>Análise de página > Recarregamentos (quais páginas geram mais recarregamentos?)</li><li>Análise de página > Tempo gasto na página (quanto tempo meus usuários gastam nas páginas?)</li><li>Entradas &amp; saídas > Páginas de entrada (quais são minhas páginas de entrada principais?)</li><li>Entradas &amp; saídas > Páginas de entrada originais (de qual página meu visitante veio originalmente?)</li><li>Entradas &amp; saídas > Visitas em única página (quais páginas geraram mais visitas em única página?)</li><li>Entradas &amp; saídas > Páginas de saída (quais são minhas páginas de saída principais?)</li><li>Análise da página > Resumo da página</li></ul> |
| **[!UICONTROL Conversão]** | <ul><li>Produtos > Produtos (quais produtos estão impulsionando minhas métricas principais?)</li><li>Produtos > Desempenho do produto (quais produtos estão tendo o melhor desempenho?)</li><li>Produtos > Categorias (quais são minhas categorias de produtos com melhor desempenho?)</li><li>Carrinho de compras > Carrinhos (quantos usuários adicionaram um produto ao carrinho?)</li><li>Carrinho de compras > Visualizações do carrinho (quantas vezes meus visitantes visualizaram os carrinhos?)</li><li>Carrinho de compras > Adições ao carrinho (com que frequência os usuários adicionam um produto ao carrinho?)</li><li>Carrinho de compras > Remoções do carrinho (com que frequência os usuários removem um produto do carrinho?)</li><li>Compras > Receita (como minha receita está funcionando?)</li><li>Compras > Pedidos (como meus pedidos estão se saindo?)</li><li>Compras > Unidades (quantas unidades estou vendendo?)</li><li>[Magento: marketing e comércio](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=pt-BR#commerce)</li></ul> |
| **[!UICONTROL Público-alvo]** | <ul><li>Métrica de pessoas (quantas pessoas interagem com minha marca?)</li><li>Perfil do visitante > Visão geral de localização (quais locais estão promovendo mais uso entre os usuários)</li><li>Perfil do visitante > Geosegmentação > Geo Counties, Geo US States, Geo Regions, Geo Cities, Geo US DMA (quais regiões meus usuários estão visitando?)</li><li>Perfil do visitante > Idiomas (qual idioma meus usuários preferem?)</li><li>Perfil do visitante > Fusos horários (em quais fusos horários meus usuários estão visitando?)</li><li>Perfil do visitante > Domínios (quais ISPs meus visitantes estão usando para acessar meu site?)</li><li>Perfil do visitante > Domínios de nível superior (quais domínios estão direcionando o tráfego para meu site?)</li><li>Perfil do visitante > Tecnologia > Visão geral da tecnologia (que tecnologias as pessoas estão usando para acessar meu site?)</li><li>Perfil do visitante > Tecnologia > Navegadores, tipo de navegador, largura do navegador, altura do navegador (qual navegador da empresa, versão do navegador e sua largura e altura as pessoas estão usando para acessar meu site?)</li><li>Perfil do visitante > Tecnologia > Sistema operacional, Tipos de sistema operacional (qual SO e qual versão dele meus visitantes usam?)</li><li>Perfil do visitante > Tecnologia > Operadora de celular (quais operadoras de celular meus visitantes usam para acessar meu site?)</li><li>Retenção de visitante > Frequência de retorno (quanto tempo passa entre a visita atual do usuário e as visitas anteriores?)</li><li>Retenção de visitante > Visitas de retorno (quantas de minhas visitas são usuários recorrentes?)</li><li>Retenção de visitante > Número da visita (que contém o número da visita que direciona a maioria das minhas métricas principais)</li><li>Retenção de visitante > Ciclo de vendas > Fidelidade do cliente (a qual segmento de fidelidade meus usuários pertencem?)</li><li>Retenção de visitante > Ciclo de vendas > Dias antes da primeira compra (quantos dias se passaram entre a primeira visita de meus usuários e a primeira compra?)</li><li>Retenção de visitante > Ciclo de vendas > Dias desde a última compra (quantos dias se passaram entre a visita atual de meus usuários e a última compra? )</li><li>Retenção de visitante > Dispositivo móvel > Dispositivos e tipos de dispositivo (quais dispositivos e tipos de dispositivo meus visitantes estão usando?)</li><li>Retenção de visitante > Dispositivo móvel > Fabricante (qual fabricante de dispositivo móvel meus visitantes usam?)</li><li>Retenção de visitante > Dispositivo móvel > Tamanho da tela, Altura da tela, Largura da tela (que tamanho/altura/largura da tela móvel meus visitantes têm?)</li><li>Retenção de visitante > Dispositivo móvel > [Uso de aplicativo móvel](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=pt-BR#mobile)</li><li>Retenção de visitante > Dispositivo móvel > [Jornadas de aplicativo móvel](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=pt-BR#mobile)</li><li>Retenção de visitante > Dispositivo móvel > [Métricas de aplicativo móvel](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=pt-BR#mobile)</li><li>Retenção de visitante > Dispositivo móvel > [Mensagens de aplicativo móvel](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=pt-BR#mobile)</li><li>Retenção de visitante > Dispositivo móvel > [Desempenho do aplicativo móvel](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=pt-BR#mobile)</li><li>Retenção de visitante > Dispositivo móvel > [Retenção de aplicativo móvel](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=pt-BR#mobile)</li></ul> |
| **[!UICONTROL Aquisição]** | <ul><li>Canais de marketing > Canal de primeiro contato, Detalhes do canal de primeiro contato (qual canal de primeiro contato e qual canal de primeiro contato específico está tendo o melhor desempenho?)</li><li>Canais de marketing > Primeiro último canal, Detalhes do primeiro último canal (qual canal de último contato e qual canal de último contato específico está tendo o melhor desempenho?)</li><li>Campanhas > Campanhas (quais campanhas estão impulsionando minhas principais métricas?)</li><li>Campanhas > Desempenho da campanha (que campanhas estão gerando mais receita?)</li><li>Campanhas > Código de rastreamento (quais códigos de rastreamento de campanha têm o melhor desempenho?)</li><li>[Aquisição na web](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=pt-BR#web)</li><li>[Aquisição por dispositivo móvel](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=pt-BR#mobile)</li><li>[Advertising Analytics: pesquisa paga](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=pt-BR#advertising)</li><li>Palavras-chave de pesquisa — todas, pagas, naturais (quais palavras-chave de pesquisa e palavras-chave de pesquisa pagas/naturais direcionam minhas métricas principais da melhor maneira?)</li><li>Mecanismos de pesquisa — todos, pagos, naturais (quais mecanismos de pesquisa e mecanismos de pesquisa pagos/naturais direcionam minhas métricas principais da melhor maneira?)</li><li>Toda a classificação da página de pesquisa (de qual página de pesquisa meus usuários chegam?)</li><li>Domínios de referência (quais domínios estão direcionando tráfego para meu site?)</li><li>Domínios de referência originais (quais foram os primeiros usuários de domínio antes de visitar meu site?)</li><li>Referenciadores (em quais URLs meus usuários estavam antes de clicar no meu site?)</li><li>Tipos de referenciadores (a qual categoria meus URLs de referência pertencem?)</li></ul> |

### Conversão {#web-conversion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--productConversionReport"
>title="Modelo de funil de conversão de produtos"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--retail-products-template"
>title="Veja quais produtos têm o melhor desempenho."
>abstract="**Isso pode ajudar** a entender melhor quais produtos são mais bem-sucedidos.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar os fundos destinados a produtos bem-sucedidos e diminuir os de produtos de menor sucesso.<br/>Este modelo usa as métricas “Exibições do produto”, “Adições ao carrinho”, “Pedidos”, “Receita” e “Unidades”. Ele também usa a dimensão “Produto”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--categoryRankedReport"
>title="."
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--cartConversionReport"
>title="Veja o número de vezes que as pessoas executam eventos importantes de check-out, como adicionar itens ao carrinho, visualizar o carrinho, remover itens do carrinho e concluir o pagamento."
>abstract="**Isso pode ajudar** a entender melhor quais partes do funil do processo de finalização levam à conversão e quais são mais propensos a abandono de carrinho.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como reduzir o atrito em determinadas etapas do processo de finalização.<br/>Este modelo usa"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--cartsOvertimeReport"
>title="Veja o número de pessoas que adicionaram um produto ao carrinho."
>abstract="**Isso pode ajudar** a entender melhor o número de pessoas que adicionam um produto ao carrinho, em vez do número geral de produtos adicionados a um carrinho.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como medir a eficácia das páginas dos seus produtos.<br/>Este modelo usa a métrica “Carrinhos”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--cartViewsOvertimeReport"
>title="Veja o número de vezes que as pessoas visualizaram seus carrinhos de compras."
>abstract="**Isso pode ajudar** a entender melhor a experiência de check-out na tentativa de reduzir as taxas de abandono de carrinho ou analisar o tempo entre as adições ao carrinho e os check-outs de diferentes produtos.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como oferecer promoções para produtos que permanecem mais tempo no carrinho e têm um risco maior de abandono.<br/>Este modelo usa a métrica “Exibições do carrinho”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--cartAdditionsOvertimeReport"
>title="Veja o número de vezes que as pessoas adicionaram algo ao carrinho."
>abstract="**Isso pode ajudar** a entender melhor a parte do funil de conversão na qual o interesse de clientes em um produto é alto o suficiente para que o adicionem ao carrinho.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como melhorar as recomendações de produto para clientes. Para isso, é possível analisar quais produtos são adicionados com frequência aos mesmos carrinhos e sugerir produtos relacionados com base em itens já presentes no carrinho."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--cartRemovalsOvertimeReport"
>title="Veja o número de vezes que as pessoas removeram algo do carrinho."
>abstract="**Isso pode ajudar** a entender melhor a parte do funil de conversão na qual clientes perdem o interesse no produto ou onde possam existir problemas no processo de finalização.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como remover possíveis barreiras que possam existir no processo de finalização, como uma experiência de usuário complicada.<br/>Este modelo usa a métrica “Remoções do carrinho”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--purchaseConversionReport"
>title="Modelo de funil de conversão de compras"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--commerce-and-marketing-management"
>title="Veja insights pré-criados para varejistas em suas atividades comerciais para ajudar a melhorar as vendas. Ele é direcionado para usuários do Magento, mas pode ser aproveitado por qualquer varejista online."
>abstract="**Isso pode ajudá-lo** a entender melhor como suas atividades comerciais estão contribuindo para os números de vendas.<br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como ajustar orçamentos para atividades que estão obtendo o maior ROI."

<!-- markdownlint-enable MD034 -->

Os seguintes modelos estão disponíveis:

| Nome do modelo | Por que usar este modelo <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Funil de Conversão de Produto**] | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |
| **Produtos** | Veja quais produtos estão impulsionando as métricas principais, como os mais vendidos ou os mais vistos. <p>**Isso pode ajudar** a entender melhor quais produtos são mais bem-sucedidos.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar os fundos destinados a produtos bem-sucedidos e diminuir os de produtos de menor sucesso.</p><p>Esse modelo usa a métrica Pedidos e a dimensão Produto. |
| **Desempenho do produto** | Veja quais produtos têm o melhor desempenho.<p>**Isso pode ajudar** a entender melhor quais produtos são mais bem-sucedidos.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar os fundos destinados a produtos bem-sucedidos e diminuir os de produtos de menor sucesso.</p><p>Esse modelo usa as métricas Exibições do produto, Adições ao carrinho, Pedidos, Receita e Unidades. Ele também usa a dimensão “Produto”. |
| **Categorias** |  |
| **Funis de conversão de carrinho** | Veja o número de vezes que as pessoas executam eventos importantes de check-out, como adicionar itens ao carrinho, visualizar o carrinho, remover itens do carrinho e concluir o pagamento. <p>**Isso pode ajudar** a entender melhor quais partes do funil do processo de finalização levam à conversão e quais são mais propensos a abandono de carrinho.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como reduzir o atrito em determinadas etapas do processo de finalização.</p><p>Este modelo usa o |
| **Carrinhos** | Veja o número de pessoas que adicionaram um produto ao carrinho.<p>**Isso pode ajudar** a entender melhor o número de pessoas que adicionam um produto ao carrinho, em vez do número geral de produtos adicionados a um carrinho.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como medir a eficácia das páginas dos seus produtos.</p><p>Esse modelo usa a métrica Carrinhos. |
| **Visualizações do carrinho** | Veja o número de vezes que as pessoas visualizaram seus carrinhos de compras. <p>**Isso pode ajudar** a entender melhor a experiência de check-out na tentativa de reduzir as taxas de abandono de carrinho ou analisar o tempo entre as adições ao carrinho e os check-outs de diferentes produtos.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como oferecer promoções para produtos que permanecem mais tempo no carrinho e têm um risco maior de abandono.</p><p>Esse modelo usa a métrica Exibições do carrinho. |
| **Adições ao carrinho** | Veja o número de vezes que as pessoas adicionaram algo ao carrinho. <p>**Isso pode ajudar** a entender melhor a parte do funil de conversão na qual o interesse de clientes em um produto é alto o suficiente para que o adicionem ao carrinho.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como melhorar as recomendações de produto para clientes. Para isso, é possível analisar quais produtos são adicionados com frequência aos mesmos carrinhos e sugerir produtos relacionados com base em itens já presentes no carrinho. |
| **Remoções do carrinho** | Veja o número de vezes que as pessoas removeram algo do carrinho.<p>**Isso pode ajudar** a entender melhor a parte do funil de conversão na qual clientes perdem o interesse no produto ou onde possam existir problemas no processo de finalização.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como remover possíveis barreiras que possam existir no processo de finalização, como uma experiência de usuário complicada.</p><p>Este modelo usa a métrica Remoções do carrinho. |
| **Funil de Conversão de Compra** | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |
| **Receita** | <!--duplicated in Most popular section-->Exibir a quantidade monetária de produtos comprados em todos os pedidos.<p>**Isso pode ajudá-lo** a entender melhor quais itens de dimensão contribuíram para a receita, combinando a métrica Receita com qualquer dimensão. Por exemplo, você pode ver as campanhas principais (usando a dimensão Código de rastreamento ) que contribuíram para a receita. </p><p>**Com base no que você aprendeu, é possível** executar várias ações, como ajustar campanhas que não estão atingindo as metas de receita que você esperaria.</p><p>Este modelo usa a métrica Receita. |
| **Pedidos** | <!--duplicated in Most popular section-->Visualize o número total de eventos de compra feitos em seu site. <p>**Isso pode ajudá-lo** a entender melhor quais itens de dimensão contribuíram para um pedido, combinando a métrica Pedidos com qualquer dimensão. Por exemplo, você pode ver as campanhas principais (usando a dimensão Código de rastreamento ) que contribuíram com as compras.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como ajustar campanhas que não estão atingindo os objetivos de compra esperados. </p><p>Esse modelo usa a métrica Pedidos. |
| [!UICONTROL **Unidades**] | Exibir o número total de unidades compradas em todas as ordens. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudá-lo** a entender melhor como as vendas de unidades estão aumentando ou diminuindo com o tempo. Você poderia aplicar um segmento para saber quais clientes ou regiões geográficas estão comprando mais unidades e como essas vendas de unidades estão em tendência ao longo do tempo.</p><p>**Com base no que você aprendeu, é possível** executar várias ações, como avaliar a eficácia de uma campanha de marketing iniciada recentemente comparando as vendas de unidade antes e depois do lançamento da campanha. Ou você pode comparar as vendas de unidades ano a ano durante os feriados.</p><p>Este modelo usa a [dimensão de Dia](/help/components/dimensions/day.md) e a [métrica de Unidades](/help/components/metrics/units.md).</p> |
| [!UICONTROL **Magento: Marketing e Commerce**] | Veja insights pré-criados para varejistas em suas atividades comerciais para ajudar a melhorar as vendas. Ele é direcionado para usuários do Magento, mas pode ser aproveitado por qualquer varejista online. <p>**Isso pode ajudá-lo** a entender melhor como suas atividades comerciais estão contribuindo para os números de vendas.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como ajustar orçamentos para atividades que estão obtendo o maior ROI.</p> |

### Público-alvo {#web-audience}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--countryGeoReport"
>title="Veja o país de origem das pessoas que visitam o site."
>abstract="**Isso pode ajudar** a entender melhor quais são os principais países de origem de visitantes do site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como usar os dados para aumentar o foco das campanhas de marketing nesses países ou garantir que a experiência do site seja ideal em países com diferentes idiomas nativos.<br/>Este modelo usa a dimensão “Países”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--stateGeoReport"
>title="Veja o estado (nos Estados Unidos) de origem das pessoas que visitaram o site. Ele é semelhante ao modelo “Regiões geográficas”, exceto pelo fato de ser específico para os Estados Unidos."
>abstract="**Isso pode ajudar** a entender melhor os principais estados de origem dos usuários dos Estados Unidos que visitam o seu site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como usar os dados para aumentar o foco das campanhas de marketing nesses estados.<br/>Este modelo utiliza a dimensão “Estados dos EUA”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--regionGeoReport"
>title="Veja a região geográfica de origem de visitantes do site. Uma região é uma área geográfica menor que um país, mas maior que uma cidade. Em alguns países, uma região é um estado, província ou distrito. Em outras áreas, é um país constituinte, departamento ou região metropolitana. "
>abstract="**Isso pode ajudar** a entender melhor as regiões de origem principais de visitantes do seu site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como usar os dados para aumentar o foco das campanhas de marketing nessas regiões ou verificar se a experiência do site é ideal em regiões com diferentes idiomas nativos. <br/>Este modelo usa as dimensões “ID (variáveis/país geográfico)” e “Regiões”. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cityGeoReport"
>title="Veja a cidade de origem de visitantes do site."
>abstract="**Isso pode ajudar** a entender melhor as cidades de origem principais de visitantes do seu site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como usar os dados para aumentar o foco das campanhas de marketing nessas cidades. <br/>Este modelo usa a dimensão “Cidades”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--dmaGeoReport"
>title="Veja as áreas de marketing designadas (DMAs) de origem de visitantes do site nos Estados Unidos."
>abstract="**Isso pode ajudar** a entender melhor as regiões de origem principais de visitantes do seu site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como usar os dados para aumentar o foco das campanhas de marketing nas regiões mais bem-sucedidas. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--languageRankedReport"
>title="Veja os principais idiomas nos quais visitantes preferem visualizar o conteúdo."
>abstract="**Isso pode ajudar** a entender melhor os idiomas preferidos de visitantes.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das atividades de localização ou campanhas de marketing nos idiomas mais populares.<br/>Este modelo usa a dimensão “Idioma”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timeZoneRankedReport"
>title="Exibir os principais fusos horários dos visitantes que acessam o site."
>abstract="**Isso pode ajudá-lo** a entender melhor em quais fusos horários seus visitantes vivem.<br/>**Com base no que você aprendeu, é possível** executar várias ações, como ajustar a manutenção do site em momentos que afetarão o menor número possível de pessoas."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--domainRankedReport"
>title="Exibir os principais domínios de visitantes que acessam seu site."
>abstract="**Isso pode ajudá-lo** a entender melhor de quais organizações seus visitantes vêm.<br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como direcionar seu conteúdo para os maiores clientes."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--topLevelDomainRankedReport"
>title="Exibir os principais domínios de visitantes que acessam seu site."
>abstract="**Isso pode ajudá-lo** a entender melhor de quais organizações seus visitantes vêm.<br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como direcionar seu conteúdo para os maiores clientes."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--web-technology-template"
>title="Visão geral da tecnologia"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--browserRankedReport"
>title="Veja o nome e a versão dos principais navegadores que as pessoas usam para acessar o seu site."
>abstract="**Isso pode ajudar** a entender melhor os navegadores mais comuns que visitantes usam.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como melhorar a qualidade do site por testar novas versões dele nos principais navegadores. Isso pode maximizar os resultados do controle de qualidade.<br/>Este modelo usa a dimensão “Navegador”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--browserTypeRankedReport"
>title="Veja os nomes das organizações que criaram os principais navegadores que as pessoas usam para acessar o seu site. Ele é diferente do modelo “Navegador”, pois não lista diferentes versões do mesmo navegador como itens de dimensão separados."
>abstract="**Isso pode ajudar** a entender melhor os navegadores mais comuns que visitantes usam <br/>**Com base no que aprender, você poderá** fazer várias coisas, como melhorar a qualidade do site por testar novas versões dele nos principais navegadores. Isso pode maximizar os resultados do controle de qualidade. <br/>Esse modelo utiliza a dimensão “Tipo de navegador”. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--browserWidthRankedReport"
>title="Exibir as principais larguras do navegador que as pessoas usam para acessar o site."
>abstract="**Isso pode ajudá-lo** a entender melhor como o conteúdo é exibido para os visitantes.<br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como melhorar a qualidade do site testando novas versões do site usando as larguras de navegador mais comuns. Isso pode maximizar os resultados do controle de qualidade.<br/>Este modelo usa a dimensão “Navegador”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--browserHeightRankedReport"
>title="Exibir as principais alturas do navegador que as pessoas usam para acessar o site."
>abstract="**Isso pode ajudá-lo** a entender melhor como o conteúdo é exibido para os visitantes.<br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como melhorar a qualidade do site testando novas versões do site usando as alturas de navegador mais comuns. Isso pode maximizar os resultados do controle de qualidade.<br/>Este modelo usa a dimensão “Navegador”. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--operatingSystemRankedReport"
>title="Exibir o nome dos sistemas operacionais e a versão que as pessoas usam para acessar o site."
>abstract="**Isso pode ajudá-lo** a entender melhor os sistemas operacionais e as versões mais comuns que os visitantes usam.<br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como melhorar a qualidade do site testando novas versões do site usando os principais sistemas operacionais e versões. Isso pode maximizar os resultados do controle de qualidade."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--operatingSystemTypeRankedReport"
>title="Exibir o nome dos sistemas operacionais que as pessoas usam para acessar seu site."
>abstract="**Isso pode ajudá-lo** a entender melhor os sistemas operacionais mais comuns que os visitantes usam.<br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como melhorar a qualidade do site testando novas versões do site usando os principais sistemas operacionais. Isso pode maximizar os resultados do controle de qualidade."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileCarrierRankedReport"
>title="Veja a empresa de telecomunicação que fornece conectividade de rede celular aos dispositivos móveis que as pessoas usam para acessar o seu site."
>abstract="**Isso pode ajudar** a entender melhor quais operadoras de celular são mais usadas pela sua base de usuários.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como adaptar a entrega de conteúdo com base nos recursos de rede de diferentes operadoras para garantir uma experiência de usuário fluida.<br/>Este modelo usa a dimensão “Operadora de celular”."

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
>abstract="**Isso pode ajudá-lo** a entender melhor como os visitantes estão envolvidos ao retornar ao seu site. Isso se aplica à duração do visitante, independentemente do intervalo de datas do projeto.<br/>**Com base no que você aprende, é possível** fazer várias coisas, como ajustar esforços de marketing para visitantes frequentes.<br/>Este modelo usa a dimensão Número de visitas."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--customerLoyaltyRankedReport"
>title="Veja o número de visitantes do site que fizeram 0 compras anteriores, 1 compra anterior, 2 compras anteriores ou mais de 3 compras anteriores."
>abstract="**Isso pode ajudá-lo** a entender melhor como seu site afeta o comportamento de compra. .<br/>**Com base no que você aprende, é possível** realizar várias ações, como concentrar-se nos visitantes que retornam para fazer uma compra, para que você possa incentivar comportamentos semelhantes para novos visitantes.<br/>Este modelo usa a dimensão Fidelização do cliente."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--daysBeforeFirstPurchaseRankedReport"
>title="Visualize o número de dias que se passam entre a primeira vez que um visitante acessa seu site e quando ele faz uma compra. Por exemplo, se um visitante faz uma compra um dia após a primeira visita, qualquer visita ou evento subsequente pertence ao item de dimensão 1 dia."
>abstract="**Isso pode ajudá-lo** a entender melhor quanto tempo os visitantes levam para fazer uma compra.<br/>**Com base no que você aprendeu, você pode** fazer várias coisas, como atualizar seu site para incentivar uma aquisição mais rápida.<br/>Este modelo usa a dimensão Dias antes da primeira compra."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--daysSinceLastPurchaseRankedReport"
>title="Visualize a quantidade de tempo decorrido entre a ocorrência atual do visitante e sua compra mais recente no momento."
>abstract="**Isso pode ajudá-lo** a entender melhor o comportamento do visitante após comprar algo no seu site.<br/>**Com base no que você aprendeu, você pode** fazer várias coisas, como atualizar seu site para incentivar compras de acompanhamento.<br/>Este modelo usa a dimensão Dias desde a última compra."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileDeviceNameRankedReport"
>title="Veja a marca e o modelo dos dispositivos móveis que as pessoas usam para acessar o seu site."
>abstract="**Isso pode ajudar** a entender melhor quais dispositivos móveis são mais usados pela sua base de usuários.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como otimizar a renderização do site para os dispositivos móveis mais comuns.<br/>Este modelo usa a dimensão “Nome do dispositivo móvel”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileDeviceTypeRankedReport"
>title="Veja os tipos de dispositivo móvel que as pessoas usam para acessar o seu site, como telefones e tablets."
>abstract="**Isso pode ajudar** a entender melhor os vários tipos de dispositivo móvel usados para acessar o seu site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como otimizar o site para os tipos de dispositivo móvel mais usados.<br/>Este modelo usa a dimensão “Tipo de dispositivo móvel”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileManufacturerRankedReport"
>title="Veja quais fabricantes produzem os dispositivos móveis que as pessoas usam para acessar o seu site, como Apple e Samsung."
>abstract="**Isso pode ajudar** a entender melhor quais fabricantes são mais usados pela sua base de usuários.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como adaptar a entrega de conteúdo com base nos recursos de diferentes fabricantes para garantir uma experiência de usuário fluida.<br/>Este modelo usa a dimensão “Fabricante do dispositivo móvel”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileScreenSizeRankedReport"
>title="Exibir os principais tamanhos de tela de celular que as pessoas usam para acessar seu site."
>abstract="**Isso pode ajudá-lo** a entender melhor como o conteúdo é exibido para os visitantes.<br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como melhorar a qualidade do site testando novas versões do site usando os tamanhos de tela de celular mais comuns. Isso pode maximizar os resultados do controle de qualidade."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileScreenHeightRankedReport"
>title="Exibir as principais alturas de tela de dispositivos móveis que as pessoas usam para acessar o site."
>abstract="**Isso pode ajudá-lo** a entender melhor como o conteúdo é exibido para os visitantes.<br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como melhorar a qualidade do site testando novas versões do site usando as alturas de tela de celular mais comuns. Isso pode maximizar os resultados do controle de qualidade."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileScreenWidthRankedReport"
>title="Exibir as principais larguras de tela móvel que as pessoas usam para acessar o site."
>abstract="**Isso pode ajudá-lo** a entender melhor como o conteúdo é exibido para os visitantes.<br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como melhorar a qualidade do site testando novas versões do site usando as larguras de tela móveis mais comuns. Isso pode maximizar os resultados do controle de qualidade."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobile-lifecycle-metrics-app-usage-template"
>title="Visualize o número de usuários, inicializações e primeiras inicializações no aplicativo, bem como a duração média das sessões."
>abstract="**Isso pode ajudá-lo** a entender melhor quanto seu aplicativo está sendo usado. <br/>**Com base no que você aprendeu, é possível** executar várias ações, como melhorar o desempenho do aplicativo para que ele possa ser dimensionado de acordo com a quantidade de uso."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobile-app-journeys"
>title="Veja os principais padrões de uso do seu aplicativo móvel."
>abstract="**Isso pode ajudá-lo** a entender melhor como as pessoas estão usando seu aplicativo. <br/>**Com base no que você aprendeu, é possível** executar várias ações, como melhorar a forma como as pessoas podem passar de uma tela para outra para direcionar os fluxos de trabalho mais comuns."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobile-app-key-metrics"
>title="Veja algumas das métricas mais comuns do aplicativo móvel."
>abstract="**Isso pode ajudá-lo** a entender melhor o desempenho básico do seu aplicativo móvel.<br/>**Com base no que você aprendeu, você pode** fazer várias coisas, como avaliar a integridade e o desempenho geral do seu aplicativo."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobile-app-messaging"
>title="Visualize dados de desempenho de mensagens no aplicativo e de mensagens por push para seu aplicativo."
>abstract="**Isso pode ajudá-lo** a entender melhor como as pessoas estão usando os recursos de mensagens no aplicativo, bem como a eficiência com que as notificações por push estão direcionando o tráfego para o seu aplicativo.<br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como melhorar a experiência de notificação por push de mensagens no aplicativo."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobile-app-performance-template"
>title="Veja o desempenho do seu aplicativo e onde os usuários estão com problemas."
>abstract="**Isso pode ajudá-lo** a entender melhor se as pessoas que usam seu aplicativo estão encontrando lentidão ou desempenho degradado. <br/>**Com base no que você aprendeu, é possível** executar várias ações, como corrigir problemas existentes ou melhorar o desempenho do aplicativo antes que eles ocorram."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobile-app-retention"
>title="Veja quais usuários são os mais fiéis ao seu aplicativo e o que eles fazem dentro do aplicativo."
>abstract="**Isso pode ajudá-lo** a entender melhor como seus usuários mais fiéis estão usando seu aplicativo.<br/>**Com base no que você aprendeu, você pode** fazer várias coisas, como melhorar seus esforços de marketing para os recursos que seus usuários mais fiéis estão usando."

<!-- markdownlint-enable MD034 -->


Os seguintes modelos estão disponíveis:

| Nome do modelo | Por que usar este modelo <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Métrica de pessoas**] | Visualize o número de pessoas que estão interagindo com a sua marca. <p>**Isso pode ajudá-lo** a entender melhor as tendências de uso do site.</p><p>**Com base no que você aprendeu, você pode** fazer várias coisas, como medir a eficácia dos esforços recentes de marketing em gerar novos visitantes para o seu site.</p> |
| **Perfil do Visitante** > **Visão Geral da Localização** | Exibir uma visão geral da localização do visitante em uma visualização de mapa.<p>**Isso pode ajudá-lo** a entender melhor onde estão os visitantes que estão visitando seu site. </p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como focalizar recursos de marketing nos locais onde você vê mais interesse e oportunidade.</p><!-- This template uses the --> |
| **Perfil do Visitante** > **Países Geográficos** | Veja o país de origem das pessoas que visitam o site.<p>**Isso pode ajudar** a entender melhor quais são os principais países de origem de visitantes do site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como usar os dados para aumentar o foco das campanhas de marketing nesses países ou garantir que a experiência do site seja ideal em países com diferentes idiomas nativos.</p><p>Este modelo usa a dimensão Países. </p> |
| **Perfil do Visitante** > **Geo US States** | Veja o estado (nos Estados Unidos) de origem das pessoas que visitaram o site. Ele é semelhante ao modelo “Regiões geográficas”, exceto pelo fato de ser específico para os Estados Unidos.<p>**Isso pode ajudar** a entender melhor os principais estados de origem dos usuários dos Estados Unidos que visitam o seu site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como usar os dados para aumentar o foco das campanhas de marketing nesses estados.</p><p>Esse modelo usa a dimensão Estados dos EUA. </p> |
| **Perfil do Visitante** > **Geo Regions** | Veja a região geográfica de origem de visitantes do site. Uma região é uma área geográfica menor que um país, mas maior que uma cidade. Em alguns países, uma região é um estado, província ou distrito. Em outras áreas, é um país constituinte, departamento ou região metropolitana. <p>**Isso pode ajudar** a entender melhor as regiões de origem principais de visitantes do seu site.</p><p>**Com base no que você aprendeu, é possível** realizar várias ações, como usar os dados para se concentrar nos esforços de marketing nessas regiões ou verificar se a experiência do site é ideal em regiões com idiomas principais diferentes. </p><p>Esse modelo usa as dimensões ID(variáveis/país_geográfico) e Regiões. </p> |
| **Perfil do Visitante** > **Cidades Geográficas** | Veja a cidade de origem de visitantes do site. <p>**Isso pode ajudar** a entender melhor as cidades de origem principais de visitantes do seu site.</p><p>**Com base no que você aprendeu, você pode** fazer várias coisas, como usar os dados para se concentrar nos esforços de marketing nessas cidades. </p><p>Esse modelo usa a dimensão Cidades. </p> |
| **Perfil do visitante** > **Geo US DMA** | Veja as áreas de marketing designadas (DMAs) de origem de visitantes do site nos Estados Unidos.<p>**Isso pode ajudar** a entender melhor as regiões de origem principais de visitantes do seu site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como usar os dados para aumentar o foco das campanhas de marketing nas regiões mais bem-sucedidas. </p><!-- This template uses the --> |
| **Perfil do visitante** > **Idiomas** | Veja os principais idiomas nos quais visitantes preferem visualizar o conteúdo. <p>**Isso pode ajudar** a entender melhor os idiomas preferidos de visitantes.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das atividades de localização ou campanhas de marketing nos idiomas mais populares.</p><p>Esse modelo usa a dimensão Idioma.</p> |
| **Perfil do Visitante** > **Fusos Horários** | Exibir os principais fusos horários dos visitantes que acessam o site. <p>**Isso pode ajudá-lo** a entender melhor em quais fusos horários seus visitantes vivem.</p><p>**Com base no que você aprendeu, é possível** executar várias ações, como ajustar a manutenção do site em momentos que afetarão o menor número possível de pessoas.</p> |
| **Perfil do Visitante** > **Domínios** | Exibir os principais domínios de visitantes que acessam seu site. <p>**Isso pode ajudá-lo** a entender melhor de quais organizações seus visitantes vêm.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como direcionar seu conteúdo para os maiores clientes.</p> |
| **Perfil do Visitante** > **Domínios de Nível Superior** | Exibir os domínios de nível superior dos visitantes que acessam o site. <p>**Isso pode ajudá-lo** a entender melhor de quais organizações seus visitantes vêm.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como direcionar seu conteúdo para os maiores clientes.</p> |
| **Perfil do Visitante** > **Tecnologia** > **Visão Geral da Tecnologia** | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o </p> |
| **Perfil do Visitante** > **Tecnologia** > **Navegadores** | Veja o nome e a versão dos principais navegadores que as pessoas usam para acessar o seu site.<p>**Isso pode ajudar** a entender melhor os navegadores mais comuns que visitantes usam.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como melhorar a qualidade do site por testar novas versões dele nos principais navegadores. Isso pode maximizar os resultados do controle de qualidade.</p><p>Esse modelo usa a dimensão Navegador. </p> |
| **Perfil do Visitante** > **Tecnologia** > **Tipos de Navegador** | Veja os nomes das organizações que criaram os principais navegadores que as pessoas usam para acessar o seu site. Ele é diferente do modelo “Navegador”, pois não lista diferentes versões do mesmo navegador como itens de dimensão separados.<p>**Isso pode ajudá-lo** a entender melhor os navegadores mais comuns que os visitantes usam</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como melhorar a qualidade do site por testar novas versões dele nos principais navegadores. Isso pode maximizar os resultados do controle de qualidade. </p><p>Esse modelo usa a dimensão Tipo de navegador. </p> |
| **Perfil do Visitante** > **Tecnologia** > **Largura do Navegador** | Exibir as principais larguras do navegador que as pessoas usam para acessar o site.<p>**Isso pode ajudá-lo** a entender melhor como o conteúdo é exibido para os visitantes.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como melhorar a qualidade do site testando novas versões do site usando as larguras de navegador mais comuns. Isso pode maximizar os resultados do controle de qualidade.</p><p>Esse modelo usa a dimensão Navegador. </p> |
| **Perfil do Visitante** > **Tecnologia** > **Altura do Navegador** | Exibir as principais alturas do navegador que as pessoas usam para acessar o site.<p>**Isso pode ajudá-lo** a entender melhor como o conteúdo é exibido para os visitantes.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como melhorar a qualidade do site testando novas versões do site usando as alturas de navegador mais comuns. Isso pode maximizar os resultados do controle de qualidade.</p><p>Esse modelo usa a dimensão Navegador. </p> |
| **Perfil do Visitante** > **Tecnologia** > **Sistema Operacional** | Exibir o nome dos sistemas operacionais e a versão que as pessoas usam para acessar o site.<p>**Isso pode ajudá-lo** a entender melhor os sistemas operacionais e as versões mais comuns que os visitantes usam.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como melhorar a qualidade do site testando novas versões do site usando os principais sistemas operacionais e versões. Isso pode maximizar os resultados do controle de qualidade.</p> |
| **Perfil do Visitante** > **Tecnologia** > **Tipos de Sistema Operacional** | Exibir o nome dos sistemas operacionais que as pessoas usam para acessar seu site.<p>**Isso pode ajudá-lo** a entender melhor os sistemas operacionais mais comuns que os visitantes usam.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como melhorar a qualidade do site testando novas versões do site usando os principais sistemas operacionais. Isso pode maximizar os resultados do controle de qualidade.</p> |
| **Perfil do Visitante** > **Tecnologia** > [!UICONTROL **Operadora de Celular**] | Veja a empresa de telecomunicação que fornece conectividade de rede celular aos dispositivos móveis que as pessoas usam para acessar o seu site.<p>**Isso pode ajudar** a entender melhor quais operadoras de celular são mais usadas pela sua base de usuários.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como adaptar a entrega de conteúdo com base nos recursos de rede de diferentes operadoras para garantir uma experiência de usuário fluida.</p><p>Esse modelo usa a dimensão Operadora de celular.</p> |
| **Retenção De Visitantes** > **Frequência De Retorno** | Veja a empresa de telecomunicação que fornece conectividade de rede celular aos dispositivos móveis que as pessoas usam para acessar o seu site.<p>**Isso pode ajudar** a entender melhor quais operadoras de celular são mais usadas pela sua base de usuários.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como adaptar a entrega de conteúdo com base nos recursos de rede de diferentes operadoras para garantir uma experiência de usuário fluida.</p><p>Esse modelo usa a dimensão Operadora de celular.</p> |
| **Retenção De Visitantes** > **Visitas De Retorno** | Veja a empresa de telecomunicação que fornece conectividade de rede celular aos dispositivos móveis que as pessoas usam para acessar o seu site.<p>**Isso pode ajudar** a entender melhor quais operadoras de celular são mais usadas pela sua base de usuários.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como adaptar a entrega de conteúdo com base nos recursos de rede de diferentes operadoras para garantir uma experiência de usuário fluida.</p><p>Esse modelo usa a dimensão Operadora de celular.</p> |
| **Retenção de Visitantes** > **Número de Visitas** | Visualize quantas vezes um visitante visitou o site.<p>**Isso pode ajudá-lo** a entender melhor como os visitantes estão envolvidos ao retornar ao seu site. Isso se aplica à duração do visitante, independentemente do intervalo de datas do projeto.</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como ajustar esforços de marketing para visitantes frequentes.</p><p>Esse modelo usa a dimensão Número de visitas.</p> |
| **Retenção De Visitantes** > **Ciclo De Vendas** > **Fidelidade Do Cliente** | Veja o número de visitantes do site que fizeram 0 compras anteriores, 1 compra anterior, 2 compras anteriores ou mais de 3 compras anteriores. <p>**Isso pode ajudá-lo** a entender melhor como seu site afeta o comportamento de compra. .</p><p>**Com base no que você aprende, é possível** realizar várias ações, como concentrar-se nos visitantes que retornam para fazer uma compra, para que você possa incentivar comportamentos semelhantes para novos visitantes.</p><p>Esse modelo usa a dimensão Fidelização do cliente.</p> |
| **Retenção De Visitantes** > **Ciclo De Vendas** > **Dias Antes Da Primeira Compra** | Visualize o número de dias que se passam entre a primeira vez que um visitante acessa seu site e quando ele faz uma compra. Por exemplo, se um visitante efetua uma compra um dia após a primeira visita, qualquer visita ou evento subsequente pertence ao item de dimensão “1 dia”.<p>**Isso pode ajudá-lo** a entender melhor quanto tempo os visitantes levam para fazer uma compra.</p><p>**Com base no que você aprendeu, você pode** fazer várias coisas, como atualizar seu site para incentivar uma aquisição mais rápida.</p><p>Esse modelo usa a dimensão Dias antes da primeira compra.</p> |
| **Retenção De Visitantes** > **Ciclo De Vendas** > **Dias Desde A Última Compra** | Visualize a quantidade de tempo decorrido entre a ocorrência atual do visitante e sua compra mais recente no momento.<p>**Isso pode ajudá-lo** a entender melhor o comportamento do visitante após comprar algo no seu site.</p><p>**Com base no que você aprendeu, você pode** fazer várias coisas, como atualizar seu site para incentivar compras de acompanhamento.</p><p>Esse modelo usa a dimensão Dias desde a última compra.</p> |
| **Dispositivos móveis** > **Dispositivos móveis** | Veja a marca e o modelo dos dispositivos móveis que as pessoas usam para acessar o seu site.<p>**Isso pode ajudar** a entender melhor quais dispositivos móveis são mais usados pela sua base de usuários.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como otimizar a renderização do site para os dispositivos móveis mais comuns.</p><p>Esse modelo usa a dimensão Nome do dispositivo móvel.</p> |
| **Celular** > **Tipo de Dispositivo Móvel** | Veja os tipos de dispositivo móvel que as pessoas usam para acessar o seu site, como telefones e tablets.<p>**Isso pode ajudar** a entender melhor os vários tipos de dispositivo móvel usados para acessar o seu site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como otimizar o site para os tipos de dispositivo móvel mais usados.</p><p>Esse modelo usa a dimensão Tipo de dispositivo móvel.</p> |
| **Celular** > **Fabricante** | Veja quais fabricantes produzem os dispositivos móveis que as pessoas usam para acessar o seu site, como Apple e Samsung.<p>**Isso pode ajudar** a entender melhor quais fabricantes são mais usados pela sua base de usuários.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como adaptar a entrega de conteúdo com base nos recursos de diferentes fabricantes para garantir uma experiência de usuário fluida.</p><p>Esse modelo usa a dimensão Fabricante do dispositivo móvel.</p> |
| **Celular** > **Tamanho de Tela** | Exibir os principais tamanhos de tela de celular que as pessoas usam para acessar seu site.<p>**Isso pode ajudá-lo** a entender melhor como o conteúdo é exibido para os visitantes.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como melhorar a qualidade do site testando novas versões do site usando os tamanhos de tela de celular mais comuns. Isso pode maximizar os resultados do controle de qualidade.</p> |
| **Celular** > **Altura da Tela** | Exibir as principais alturas de tela de dispositivos móveis que as pessoas usam para acessar o site.<p>**Isso pode ajudá-lo** a entender melhor como o conteúdo é exibido para os visitantes.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como melhorar a qualidade do site testando novas versões do site usando as alturas de tela de celular mais comuns. Isso pode maximizar os resultados do controle de qualidade.</p> |
| **Celular** > **Largura da Tela** | Exibir as principais larguras de tela móvel que as pessoas usam para acessar o site.<p>**Isso pode ajudá-lo** a entender melhor como o conteúdo é exibido para os visitantes.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como melhorar a qualidade do site testando novas versões do site usando as larguras de tela móveis mais comuns. Isso pode maximizar os resultados do controle de qualidade.</p> |
| **Dispositivo móvel** > **Uso de aplicativos móveis** | Visualize o número de usuários, inicializações e primeiras inicializações no aplicativo, bem como a duração média das sessões.<p>**Isso pode ajudá-lo** a entender melhor quanto seu aplicativo está sendo usado. </p><p>**Com base no que você aprendeu, é possível** executar várias ações, como melhorar o desempenho do aplicativo para que ele possa ser dimensionado de acordo com a quantidade de uso.</p><!-- This template uses the --> |
| **Celular** > **Jornadas de Aplicativos Móveis** | Veja os principais padrões de uso do seu aplicativo móvel. <p>**Isso pode ajudá-lo** a entender melhor como as pessoas estão usando seu aplicativo. </p><p>**Com base no que você aprendeu, é possível** executar várias ações, como melhorar a forma como as pessoas podem passar de uma tela para outra para direcionar os fluxos de trabalho mais comuns. </p><!-- This template uses the --> |
| **Dispositivo móvel** > **Métricas de Aplicativo Móvel** | Veja algumas das métricas mais comuns do aplicativo móvel. <p>**Isso pode ajudá-lo** a entender melhor o desempenho básico do seu aplicativo móvel.</p><p>**Com base no que você aprendeu, você pode** fazer várias coisas, como avaliar a integridade e o desempenho geral do seu aplicativo.</p><!-- This template uses the --> |
| **Dispositivo móvel** > **Mensagens de Aplicativo Móvel** | Visualize dados de desempenho de mensagens no aplicativo e de mensagens por push para seu aplicativo.<p>**Isso pode ajudá-lo** a entender melhor como as pessoas estão usando os recursos de mensagens no aplicativo, bem como a eficiência com que as notificações por push estão direcionando o tráfego para o seu aplicativo.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como melhorar a experiência de notificação por push de mensagens no aplicativo.</p><!-- This template uses the --> |
| **Dispositivo móvel** > **Desempenho de aplicativo móvel** | Veja o desempenho do seu aplicativo e onde os usuários estão com problemas. <p>**Isso pode ajudá-lo** a entender melhor se as pessoas que usam seu aplicativo estão encontrando lentidão ou desempenho degradado. </p><p>**Com base no que você aprendeu, é possível** executar várias ações, como corrigir problemas existentes ou melhorar o desempenho do aplicativo antes que eles ocorram.</p><!-- This template uses the --> |
| **Dispositivo móvel** > **Retenção de aplicativo móvel** | Veja quais usuários são os mais fiéis ao seu aplicativo e o que eles fazem dentro do aplicativo. <p>**Isso pode ajudá-lo** a entender melhor como seus usuários mais fiéis estão usando seu aplicativo.</p><p>**Com base no que você aprendeu, você pode** fazer várias coisas, como melhorar seus esforços de marketing para os recursos que seus usuários mais fiéis estão usando.</p><!-- This template uses the --> |

### Aquisição {#web-acquisition}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--marketing-channel-overview-template"
>title="Por meio da atribuição personalizada, este modelo mostra como visitantes chegam ao seu site."
>abstract="**Isso pode ajudar** a entender melhor quais dos seus canais de marketing são mais eficazes.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o investimento em canais de marketing eficazes e livrar-se de canais de marketing menos eficazes.<br/>Este modelo usa a dimensão “ID (variáveis/canal de marketing)” e a métrica “Receita”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--firstouchChannelRankedReport"
>title="Veja o primeiro canal de marketing que um(a) visitante utiliza durante seu período de engajamento (30 dias por padrão). "
>abstract="**Isso pode ajudar** a entender melhor quais canais de marketing geram o tráfego inicial para o seu site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das campanhas de marketing em áreas mais eficazes.<br/>Este modelo usa a dimensão “Canal de primeiro contato”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--firstouchChannelDetailRankedReport"
>title="Veja os detalhes do primeiro canal de marketing que um(a) visitante utiliza durante o seu período de engajamento (30 dias por padrão). "
>abstract="**Isso pode ajudar** a entender melhor o que contribuiu para que a visita ocorresse por meio daquele canal de marketing. Por exemplo, se um visitante chegasse ao seu site e correspondesse ao canal de marketing &quot;Pesquisa paga&quot;, você poderia usar os detalhes do canal para ver qual mecanismo de pesquisa foi usado ou qual palavra-chave foi pesquisada.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das campanhas de marketing em áreas mais eficazes.<br/>Este modelo usa a dimensão “Detalhes do canal de primeiro contato”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--campaignConversionReport"
>title="Funil de conversão da campanha"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--retail-campaign-performance-template"
>title="Veja os detalhes do desempenho das suas campanhas de marketing."
>abstract="**Isso pode ajudar** a entender melhor os vários indicadores de sucesso associados às campanhas, como receita, exibições de produtos, pedidos e assim por diante.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das campanhas de marketing nas maiores fontes de receita. <br/>Este modelo usa as métricas “Receita”, “Exibições do produto”, “Adições ao carrinho”, “Pedidos” e “Unidades”. Ele também usa as dimensões “Código de rastreamento” e “Domínio de referência”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobile-app-acquisition-template"
>title="Veja como seu site obtém visitantes em dispositivos móveis."
>abstract="**Isso pode ajudar** a entender melhor os vários fatores que levam à aquisição, como palavras-chave de pesquisa, domínio de referência e assim por diante.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das campanhas de marketing nos canais mais eficientes.<br/>Este modelo usa as métricas “Taxa de rejeição” e “Rejeições”. Ele também usa as dimensões “Mecanismo de pesquisa”, “Palavra-chave de pesquisa”, “Página de entrada”, “Domínio de referência”, “Código de rastreamento” e “Referenciador”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--web-acquisition-template"
>title="Veja como o seu site obtém visitantes."
>abstract="**Isso pode ajudar** a entender melhor os vários fatores que levam à aquisição, como palavras-chave de pesquisa, domínio de referência e assim por diante.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das campanhas de marketing nos canais mais eficientes.<br/>Este modelo usa as métricas “Taxa de rejeição” e “Rejeições”. Ele também usa as dimensões “Mecanismo de pesquisa”, “Palavra-chave de pesquisa”, “Página de entrada”, “Domínio de referência”, “Código de rastreamento” e “Referenciador”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--advertisingAnalyticsPaidSearch"
>title="Visualize todos os dados de pesquisa paga do Google e do Bing lado a lado."
>abstract="**Isso pode ajudá-lo** a entender melhor a quantidade de tráfego que está sendo enviada para o seu site e se os clientes estão convertendo.<br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como estimar a relação custo/benefício de uma campanha publicitária."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchKeywordRankedReport"
>title="Veja as palavras-chave de pesquisa que visitantes usam para acessar o seu site, sejam elas pagas ou naturais."
>abstract="**Isso pode ajudar** a entender melhor as palavras-chave que as pessoas usam em pesquisas que resultam no tráfego do site. <br/>**Com base no que aprender, você poderá** fazer várias coisas, como identificar e preencher lacunas de SEO entre as palavras-chave usadas e as que estão gerando tráfego para o site.<br/>Este modelo usa a dimensão “Palavra-chave de pesquisa”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchPaidKeywordRankedReport"
>title="Veja as palavras-chave de pesquisa que visitantes usam para acessar o seu site que correspondem à detecção de pesquisa paga."
>abstract="**Isso pode ajudar** a entender melhor as palavras-chave que as pessoas usam em pesquisas que geram tráfego para o site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como identificar e preencher lacunas de SEO entre as palavras-chave usadas e as que estão gerando tráfego para o site. <br/>Este modelo usa a dimensão “Palavra-chave de pesquisa paga”. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchNaturalKeywordRankedReport"
>title="Veja as palavras-chave de pesquisa que visitantes usam para acessar o seu site e que não correspondem à detecção de pesquisa paga."
>abstract="**Isso pode ajudar** a entender melhor as palavras-chave que as pessoas usam em pesquisas que geram tráfego para o site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como identificar e preencher lacunas de SEO entre as palavras-chave usadas e as que estão gerando tráfego para o site.<br/>Este modelo usa a dimensão “Palavra-chave de pesquisa natural”. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchRankedReport"
>title="Veja os mecanismos de pesquisa que visitantes usam para acessar o seu site, sejam elas pagas ou naturais."
>abstract="**Isso pode ajudar** a entender melhor os mecanismos de pesquisa usados pelas pessoas que resultam em tráfego para o site. <br/>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco de SEO nos mecanismos de pesquisa que geram mais tráfego para o site.<br/>Este modelo usa a dimensão “Mecanismo de pesquisa”. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchPaidRankedReport"
>title="Veja os mecanismos de pesquisa que visitantes usam para acessar o seu site e que correspondem à detecção de pesquisa paga."
>abstract="**Isso pode ajudar** a entender melhor os mecanismos de pesquisa usados pelas pessoas que resultam em tráfego para o site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco de SEO nos mecanismos de pesquisa que geram mais tráfego para o site. <br/>Este modelo usa a dimensão “Mecanismo de pesquisa paga”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchNaturalRankedReport"
>title="Veja as palavras-chave de pesquisa que visitantes usam para acessar o seu site e que não correspondem à detecção de pesquisa paga."
>abstract="**Isso pode ajudar** a entender melhor os mecanismos de pesquisa usados pelas pessoas que resultam em tráfego para o site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco de SEO nos mecanismos de pesquisa que geram mais tráfego para o site.<br/>Este modelo usa a dimensão “Mecanismo de pesquisa natural”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--searchEngineRankRankedReport"
>title="Visualize em qual página de resultados de pesquisa um visitante clicou para acessar seu site. Por exemplo, se o site for exibido na segunda página dos resultados de pesquisa de um mecanismo de pesquisa, o item de dimensão para essa variável será Página de pesquisa 2."
>abstract="**Isso pode ajudá-lo** a entender melhor o nível de classificação das suas páginas nos resultados da pesquisa.<br/>**Com base no que você aprendeu, é possível** fazer várias coisas e melhorar sua estratégia de SEO para garantir que seu conteúdo apareça na primeira página dos resultados da pesquisa."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--referringDomainRankedReport"
>title="Veja em quais domínios as pessoas clicam para acessar o seu site."
>abstract="**Isso pode ajudar** a entender quais sites de terceiros geram mais tráfego para o seu site. (Deve haver um link no site externo e o(a) visitante precisa clicar nele para que o item de dimensão seja exibido.)<br/>**Com base no que aprender, você poderá** fazer várias coisas, como criar ou ajustar o conteúdo para melhor se alinhar aos interesses de visitantes provenientes dos principais domínios referenciadores. <br/>Este modelo usa a dimensão “Domínio referenciador”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--referringDomainOriginalRankedReport"
>title="Veja o primeiro domínio referenciador no qual as pessoas clicam para acessar o seu site. (Depois de definido, ele mantém o mesmo valor por toda a vida útil da ID do(a) visitante em questão.)"
>abstract="**Isso pode ajudar** a entender melhor quais sites de terceiros originalmente geram tráfego para o seu site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como criar ou ajustar o conteúdo para melhor se alinhar aos interesses de visitantes provenientes dos principais domínios referenciadores originais. <br/>Este modelo usa a dimensão “Domínio referenciador original”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--referrerRankedReport"
>title="Veja em quais URLs os(as) visitantes estavam quando clicaram para acessar o seu site. (Deve haver um link no URL externo e o(a) visitante precisa clicar nele para que o item de dimensão seja exibido.)"
>abstract="**Isso pode ajudar** a entender quais URLs específicos geram mais tráfego para o seu site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como criar ou ajustar o conteúdo para melhor se alinhar aos interesses de visitantes provenientes dos principais URLs. <br/>Este modelo usa a dimensão “Domínio referenciador”.</p>"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--referrerTypeRankedReport"
>title="Veja em quais canais genéricos os(as) visitantes clicaram para acessar o seu site. A Adobe mantém as regras de cada canal. Os possíveis canais incluem mecanismos de pesquisa, redes sociais, outros sites, disco rígido ou email."
>abstract="**Isso pode ajudar** a entender melhor qual tipo de referenciador gera mais tráfego para o site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como criar ou ajustar o conteúdo para melhor se alinhar aos interesses de visitantes provenientes de um determinado canal.<br/>Este modelo usa a dimensão “Tipo de referenciador”."

<!-- markdownlint-enable MD034 -->

Os seguintes modelos estão disponíveis:

| Nome do modelo | Por que usar este modelo <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Canais de marketing**] > [!UICONTROL **Relatório de visão geral do canal de marketing**] | Por meio da atribuição personalizada, este modelo mostra como visitantes chegam ao seu site.<p>**Isso pode ajudar** a entender melhor quais dos seus canais de marketing são mais eficazes.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o investimento em canais de marketing eficazes e livrar-se de canais de marketing menos eficazes.</p><p>Esse modelo usa a dimensão ID(variables/marketingchannel) e a métrica Receita.</p> |
| [!UICONTROL **Canais de marketing**] > [!UICONTROL **Canal de marketing de primeiro contato**] | Veja o primeiro canal de marketing que um(a) visitante utiliza durante seu período de engajamento (30 dias por padrão).  <p>**Isso pode ajudar** a entender melhor quais canais de marketing geram o tráfego inicial para o seu site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das campanhas de marketing em áreas mais eficazes.</p><p>Esse modelo usa a dimensão Canal de primeiro contato.</p> |
| [!UICONTROL **Canais de marketing**] > [!UICONTROL **Detalhes do canal de marketing de primeiro contato**] | Veja os detalhes do primeiro canal de marketing que um(a) visitante utiliza durante o seu período de engajamento (30 dias por padrão). <p>**Isso pode ajudar** a entender melhor o que contribuiu para que a visita ocorresse por meio daquele canal de marketing. Por exemplo, se um visitante chegasse ao seu site e correspondesse ao canal de marketing &quot;Pesquisa paga&quot;, você poderia usar os detalhes do canal para ver qual mecanismo de pesquisa foi usado ou qual palavra-chave foi pesquisada.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das campanhas de marketing em áreas mais eficazes.</p><p>Esse modelo usa a dimensão Detalhes do canal de primeiro contato.</p> |
| [!UICONTROL **Canais de marketing**] > [!UICONTROL **Canal de marketing de último contato**] | Visualize o canal de marketing mais recente com o qual um visitante corresponde durante o período de envolvimento do visitante (30 dias por padrão).<p>**Isso pode ajudá-lo** a entender melhor quais canais de marketing direcionam o tráfego para o seu site que resulta em conversões.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das campanhas de marketing em áreas mais eficazes.</p><p>Esse modelo usa a dimensão Canal de último contato.  </p> |
| [!UICONTROL **Canais de marketing**] > [!UICONTROL **Detalhes do canal de marketing de último contato**] | Exibir detalhes sobre o canal de marketing mais recente com o qual um visitante corresponde durante o período de engajamento do visitante (30 dias por padrão)<p>**Isso pode ajudar** a entender melhor o que contribuiu para que a visita ocorresse por meio daquele canal de marketing. Por exemplo, se um visitante chegasse ao seu site e correspondesse ao canal de marketing &quot;Pesquisa paga&quot;, você poderia usar os detalhes do canal para ver qual mecanismo de pesquisa foi usado ou qual palavra-chave foi pesquisada.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das campanhas de marketing em áreas mais eficazes. </p><p>Esse modelo usa a dimensão Detalhe do canal de último contato. </p> |
| [!UICONTROL **Campanhas**] > [!UICONTROL **Campanhas (Código de Acompanhamento)**] | Exiba os nomes dos códigos de rastreamento no site. Você pode colocar links com diferentes valores de parâmetro de sequência de consulta em diferentes lugares na Internet.<p>**Isso pode ajudá-lo** a entender melhor quais links foram os mais bem-sucedidos ao direcionar tráfego para o site. Anexar sequências de consulta de código de rastreamento é comum em emails, anúncios, publicações em redes sociais e outros esforços de marketing que sua organização usa</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como concentrar esforços de marketing nas campanhas que geram mais receita.</p><p>Esse modelo usa a dimensão Código de rastreamento. </p> |
| [!UICONTROL **Campanhas**] > [!UICONTROL **Funil de conversão de campanha**] | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o  </p> |
| [!UICONTROL **Campanhas**] > [!UICONTROL **Desempenho da campanha**] | Veja os detalhes do desempenho das suas campanhas de marketing.<p>**Isso pode ajudar** a entender melhor os vários indicadores de sucesso associados às campanhas, como receita, exibições de produtos, pedidos e assim por diante.</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como concentrar esforços de marketing nas campanhas que geram mais receita. </p><p>Esse modelo usa a métrica Receita, Exibições do produto, Adições ao carrinho, Pedidos e Unidades. Ele também usa as dimensões “Código de rastreamento” e “Domínio de referência”. </p> |
| **Aquisição por dispositivo móvel** | Veja como seu site obtém visitantes em dispositivos móveis.<p>**Isso pode ajudar** a entender melhor os vários fatores que levam à aquisição, como palavras-chave de pesquisa, domínio de referência e assim por diante.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das campanhas de marketing nos canais mais eficientes.</p><p>Esse modelo usa as métricas Taxa de rejeição e Rejeições. Ele também usa as dimensões “Mecanismo de pesquisa”, “Palavra-chave de pesquisa”, “Página de entrada”, “Domínio de referência”, “Código de rastreamento” e “Referenciador”.  </p> |
| **Aquisição pela Web** | Veja como o seu site obtém visitantes.<p>**Isso pode ajudar** a entender melhor os vários fatores que levam à aquisição, como palavras-chave de pesquisa, domínio de referência e assim por diante.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das campanhas de marketing nos canais mais eficientes.</p><p>Esse modelo usa as métricas Taxa de rejeição e Rejeições. Ele também usa as dimensões “Mecanismo de pesquisa”, “Palavra-chave de pesquisa”, “Página de entrada”, “Domínio de referência”, “Código de rastreamento” e “Referenciador”.  </p> |
| **Advertising Analytics: Pesquisa paga** | Visualize todos os dados de pesquisa paga do Google e do Bing lado a lado. <p>**Isso pode ajudá-lo** a entender melhor a quantidade de tráfego que está sendo enviada para o seu site e se os clientes estão convertendo.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como estimar a relação custo/benefício de uma campanha publicitária.</p> |
| **Pesquisar Palavras-Chave-Todas** | Veja as palavras-chave de pesquisa que visitantes usam para acessar o seu site, sejam elas pagas ou naturais. <p>**Isso pode ajudar** a entender melhor as palavras-chave que as pessoas usam em pesquisas que geram tráfego para o site. </p><p>**Com base no que aprender, você poderá** fazer várias coisas, como identificar e preencher lacunas de SEO entre as palavras-chave usadas e as que estão gerando tráfego para o site.</p><p>Esse modelo usa a dimensão Palavra-chave de pesquisa. </p> |
| **Palavras-chave de Pesquisa Pagas** | Veja as palavras-chave de pesquisa que visitantes usam para acessar o seu site que correspondem à detecção de pesquisa paga.<p>**Isso pode ajudar** a entender melhor as palavras-chave que as pessoas usam em pesquisas que geram tráfego para o site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como identificar e preencher lacunas de SEO entre as palavras-chave usadas e as que estão gerando tráfego para o site. </p><p>Esse modelo usa a dimensão Palavra-chave de pesquisa - Paga. </p> |
| **Palavras-chave de Pesquisa-Natural** | Veja as palavras-chave de pesquisa que visitantes usam para acessar o seu site e que não correspondem à detecção de pesquisa paga.<p>**Isso pode ajudar** a entender melhor as palavras-chave que as pessoas usam em pesquisas que geram tráfego para o site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como identificar e preencher lacunas de SEO entre as palavras-chave usadas e as que estão gerando tráfego para o site.</p><p>Esse modelo usa a dimensão Palavra-chave de pesquisa - Natural. </p> |
| **Mecanismos de Pesquisa-Todos** | Veja os mecanismos de pesquisa que visitantes usam para acessar o seu site, sejam elas pagas ou naturais. <p>**Isso pode ajudar** a entender melhor os mecanismos de pesquisa usados pelas pessoas que resultam em tráfego para o site. </p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco de SEO nos mecanismos de pesquisa que geram mais tráfego para o site.</p><p>Esse modelo usa a dimensão Mecanismo de pesquisa. </p> |
| **Mecanismos de Pesquisa-Pagos** | Veja os mecanismos de pesquisa que visitantes usam para acessar o seu site e que correspondem à detecção de pesquisa paga.<p>**Isso pode ajudar** a entender melhor os mecanismos de pesquisa usados pelas pessoas que resultam em tráfego para o site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco de SEO nos mecanismos de pesquisa que geram mais tráfego para o site. </p><p>Esse modelo usa a dimensão Mecanismo de pesquisa - Pago. </p> |
| **Mecanismos de Pesquisa-Natural** | Veja as palavras-chave de pesquisa que visitantes usam para acessar o seu site e que não correspondem à detecção de pesquisa paga.<p>**Isso pode ajudar** a entender melhor os mecanismos de pesquisa usados pelas pessoas que resultam em tráfego para o site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco de SEO nos mecanismos de pesquisa que geram mais tráfego para o site.</p><p>Esse modelo usa a dimensão Mecanismo de pesquisa - Natural. </p> |
| **Toda a Classificação da Página de Pesquisa** | Visualize em qual página de resultados de pesquisa um visitante clicou para acessar seu site. Por exemplo, se o site for exibido na segunda página dos resultados de pesquisa de um mecanismo de pesquisa, o item de dimensão para essa variável será “Página de pesquisa 2”.<p>**Isso pode ajudá-lo** a entender melhor o nível de classificação das suas páginas nos resultados da pesquisa.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas e melhorar sua estratégia de SEO para garantir que seu conteúdo apareça na primeira página dos resultados da pesquisa. </p> |
| **Domínios de referência** | Veja em quais domínios as pessoas clicam para acessar o seu site.<p>**Isso pode ajudar** a entender quais sites de terceiros geram mais tráfego para o seu site. (Deve haver um link no site externo e o(a) visitante precisa clicar nele para que o item de dimensão seja exibido.)</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como criar ou ajustar o conteúdo para melhor se alinhar aos interesses dos visitantes provenientes dos principais domínios de referência. </p><p>Esse modelo usa a dimensão Domínio de referência. </p> |
| **Domínios de referência originais** | Veja o primeiro domínio referenciador no qual as pessoas clicam para acessar o seu site. (Depois de definido, ele mantém o mesmo valor por toda a vida útil da ID do(a) visitante em questão.)<p>**Isso pode ajudar** a entender melhor quais sites de terceiros originalmente geram tráfego para o seu site.</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como criar ou ajustar o conteúdo para melhor se alinhar aos interesses dos visitantes provenientes dos principais domínios de referência originais. </p><p>Esse modelo usa a dimensão Domínio de referência original. </p> |
| **Referenciadores** | Veja em quais URLs os(as) visitantes estavam quando clicaram para acessar o seu site. (Deve haver um link no URL externo e o(a) visitante precisa clicar nele para que o item de dimensão seja exibido.)  <p>**Isso pode ajudar** a entender quais URLs específicos geram mais tráfego para o seu site.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como criar ou ajustar o conteúdo para alinhar melhor os interesses dos visitantes que vêm das principais URLs. </p><p>Este modelo usa a dimensão Domínio de referência </p><p>Esse modelo usa a dimensão Referenciador. </p> |
| **Tipos de Referenciador** | Veja em quais canais genéricos os(as) visitantes clicaram para acessar o seu site. A Adobe mantém as regras de cada canal. Os possíveis canais incluem mecanismos de pesquisa, redes sociais, outros sites, disco rígido ou email.<p>**Isso pode ajudar** a entender melhor qual tipo de referenciador gera mais tráfego para o site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como criar ou ajustar o conteúdo para melhor se alinhar aos interesses de visitantes provenientes de um determinado canal.</p><p>Esse modelo usa a dimensão Tipo de referenciador.</p> |