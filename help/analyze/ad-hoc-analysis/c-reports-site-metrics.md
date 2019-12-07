---
description: Exibe informações quantitativas sobre o seu site, como quantas vezes os visitantes exibiram determinadas páginas, o número de compras gerais realizadas em páginas específicas, quando as visitas ocorreram e outros dados quantitativos similares. Cada um desses relatórios é uma métrica que pode ser colocada em outros relatórios baseados em itens.
title: Métricas de site relatórios
topic: Ad hoc analysis
uuid: 0730747a-216f-4a58-b62b-a9812968cde5
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Relatórios de métricas do site

Exibe informações quantitativas sobre o seu site, como quantas vezes os visitantes exibiram determinadas páginas, o número de compras gerais realizadas em páginas específicas, quando as visitas ocorreram e outros dados quantitativos similares. Cada um desses relatórios é uma métrica que pode ser colocada em outros relatórios baseados em itens.

## Métricas de site reports {#concept_0639CA16551749A693F49ADED4842CCE}

Exibe informações quantitativas sobre o seu site, como quantas vezes os visitantes exibiram determinadas páginas, o número de compras gerais realizadas em páginas específicas, quando as visitas ocorreram e outros dados quantitativos similares. Cada um desses relatórios é uma métrica que pode ser colocada em outros relatórios baseados em itens.

A tendência dos relatórios de métrica é avaliada conforme o tempo. Você pode aplicar granularidade de tempo e dia da semana nesses relatórios. Como alternativa, você pode analisar o tempo gasto no seu site, as compras, a receita e métricas similares.

Os relatórios de métricas do site a seguir estão disponíveis no menu [!UICONTROL Métricas do site].

## Relatório de exibições de página {#concept_5331AFB6948547F7B8DF367B49360E6B}

<!-- 

c_reports_pageviews.xml

 -->

Um relatório de tendências que exibe o número de vezes em que as páginas do site foram visualizadas durante o intervalo selecionado (hora, dia, semana, mês, trimestre ou ano). Uma [!UICONTROL Exibição de página] é uma solicitação de um documento de página inteira, em vez de um elemento de uma página, como uma imagem ou vídeo. Por exemplo, se um único visitante visualiza 15 páginas durante uma visita, isso é contado como 15 exibições de página. Se um usuário visita a mesma página três vezes durante uma visita, três visualizações de páginas são contadas. Este relatório permite que você acompanhe as visualizações de páginas para cada página no seu site, bem como um agregado de exibições de página do site inteiro.

## Relatório de visitas {#concept_50CA55CF2A41430CBC754AEEEE6023A9}

Exibe o número de visitas realizadas em todo o seu site durante um período especificado. Uma *visita* é uma sequência de exibições de página. Uma visita começa quando um visitante carrega uma página e termina após 30 minutos de inatividade. Ela pode durar várias horas, desde que o visitante carregue pelo menos uma página antes do tempo limite. Uma visita não precisa necessariamente coincidir com uma sessão de navegador. Por exemplo, se um visitante fecha e reabre o navegador e visita site cinco minutos depois, a visita é considerada a mesma. Isso também significa que se um visitante permanecer em uma página por 35 minutos, a visita terá sido fechada e processada e uma nova visita será iniciada se o visitante clicar em outra página. As visitas são acompanhadas por cookies. Uma visita é encerrada após 12 horas de atividade contínua.

<!-- 

c_reports_visits.xml

 -->

Em relatórios e análises de marketing, você pode executar um [!UICONTROL Relatório de visitas] em uma página selecionada. Na Ad Hoc Analysis, você pode fazer a segmentação dos dados para visualizar páginas específicas.

## Relatório de visitantes únicos {#concept_39097C54E46C496CBAD537329DB3C84A}

Um relatório de tendências que mostra o número de visitantes únicos que acessaram o seu site. Cada visitante é contado uma vez, independentemente de quantas vezes a pessoa visita seu site. A Adobe usa uma tecnologia de handshake de cookie com patente pendente para diferenciar um visitante individual de um visitante de retorno. O handshake de cookie supera as limitações da tecnologia de cookie do navegador da Internet.

<!-- 

c_reports_unique_visitors.xml

 -->

É possível usar esse relatório para:

* Ver o número de pessoas diferentes que visualizaram seu site durante um determinado período.
* Visualizar os padrões de tráfego recentes e entender como as promoções estão trazendo visitantes únicos ao seu site.
* Comparar o número de seus visitantes únicos com o número de exibições de página.

## Relatório de visitantes {#concept_7371DAB5DA474D03A2D1448F151E011B}

Mostra o número de visitantes únicos do site por uma hora, dia, semana, mês, trimestre ou ano selecionado. Um visitante único é contabilizado apenas uma vez para o intervalo selecionado. Os visitantes que retornam ao site não são contados como usuários únicos novamente até que o período tenha passado.

<!-- 

c_reports_visitors.xml

 -->

O valor total apresentado na parte inferior da tabela do relatório é a soma de todas as visitas para o período especificado e nem sempre reflete o número de visitantes únicos. Por exemplo, se você executar um [!UICONTROL relatório de visitantes únicos diários] com um intervalo de vários dias, o total pode incluir visitantes recorrentes, pois o mesmo visitante pode retornar no dia seguinte e ser contado novamente. Entretanto, se você executar um [!UICONTROL relatório de visitantes únicos mensais], o valor da coluna Totais reflete com precisão quantos visitantes únicos acessaram o site durante o mês.

## Relatório de tempo de permanência por visita {#concept_5CDB759F9C9B4002A786A71F2BDBB292}

Mostra o tempo gasto pelos visitantes em seu site durante cada visita. Ele também mostra a estatística de tempo médio gasto no site, que mostra o tempo médio que os visitantes passaram visitando seu site.

<!-- 

c_reports_time_spent_per_visit.xml

 -->

Use esse relatório para:

* Identificar quanto tempo os visitantes permanecem em seu site.
* Identificar o conteúdo do site ou as promoções que despertam o interesse dos visitantes.
* Identificar por que o tráfego no seu site é alto, mas os visitantes o deixam rapidamente.

## Relatório de compras {#concept_E3B9AF43CCD24F25A85D05DFB51C4740}

Exibe dados de resumo da receita, dos pedidos e das unidades. Você também pode exibir o [!DNL Purchase Conversion Funnel] relatório.

<!-- 

c_reports_purchases.xml

 -->

* **Receita**: permite visualizar o lucro bruto por períodos selecionados. Os exemplos podem incluir receitas durante o mês de março, as compras feitas na semana passada, ou a receita de hoje.
* **Pedidos**: esse relatório mostra o número de pedidos feitos no site durante o intervalo selecionado. Os pedidos podem conter diversos produtos.
* **Unidades**: mostra todas as unidades pedidas para o intervalo selecionado.
* **Funil de conversão de compra**: ideal para mostrar eventos de conversão no site se eles ocorrem em uma ordem específica, como em um ambiente de varejo. Um relatório de funil mostra as métricas de conversão para cada etapa do processo de conversão, assim como os pedidos, a receita e as unidades. 

## Relatório de carrinho de compras {#concept_6AEC5A6C707B46B790C1A79E72F9A339}

Exibe o número de carrinhos de compra abertos durante o período especificado. Você pode executar relatórios para analisar exibições do carrinho, adições, remoções e finalizações. Um carrinho de compras é aberto geralmente quando um cliente seleciona um item para compra, mas também pode ocorrer sem um item.

<!-- 

c_reports_shopping_cart.xml

 -->

Você pode utilizar o [!UICONTROL Relatório do carrinho de compras] para:

* Determinar padrões, altos ou baixos no número de carrinhos abertos no site.
* Examinar períodos de tempo específicos saber mais informações sobre as métricas que, especificamente, contribuíram para a abertura do carrinho.

## Relatório de eventos personalizados {#concept_9337B2FB8A3F417BA8689FE7FD64629F}

As ações de conversão do site que você deseja que os visitantes executem. Essas ações podem ser um registro, uma assinatura, o preenchimento de um formulário de perspectiva de venda, um chat, uma compra, uma reserva ou uma pesquisa concluída. 

<!-- 

c_reports_custom_events.xml

 -->

Como cada conjunto de relatórios é diferente, este conjunto de relatórios é usado de maneira diferente para cada cliente. Um relatório de [!UICONTROL Evento personalizado] pode ser usado como um contador que mostrar o número de vezes que um evento ocorre. Por exemplo, se **[!UICONTROL event1]** estiver definido para contar o número de vezes em que um documento é baixado, o relatório de eventos personalizados para o Evento 1 mostra o número total de vezes em que o evento (ou download) ocorreu.  Você pode ter diversos relatórios de eventos personalizados.

## Relatórios de conversão {#concept_BDD3DD8A46F043BB916C7E346E7C314F}

Mostra a receita obtida com diferentes aspectos do seu site. É possível ver relatórios que mostram a receita de campanhas de publicidade, a comparação entre as receitas de clientes fidelizados e de novos clientes, uma análise de receita por produto e muitos outros relatórios de receita. Os relatórios de conversão também podem mostrar outros eventos bem-sucedidos, como cliques em anúncios, downloads ou outros eventos.

<!-- 

c_reports_conversion.xml

 -->

O relatório de conversões inclui estatísticas em tempo real de todas as atividades importantes do cliente, incluindo:

* Padrões de compra do cliente
* Métricas do carrinho de compras, incluindo desistência
* Taxas de conversão do cliente
* Eficácia da publicidade e do parceiro de canal
* Desempenho da campanha de marketing online e offline
* Métricas de fidelidade do cliente
* Insight dos ciclos de vendas

## Relatórios de canal de marketing {#concept_81FFA8C15A9B4914BFED37488ADD17FD}

Relatórios de canal de marketing exibem a alocação de canais de primeiro e de último contato, com métricas críticas padrão como receita, pedidos e custo, permitindo que você saiba a receita gerada por cada canal. As regras de definição são configuradas no [!DNL Admin Console] e as APIs específicas para relatórios de canais ficam disponíveis.

<!-- 

c_reports_marketing_channel.xml

 -->

**[!UICONTROL Relatório de primeiro ou de último contato]**: exibe as métricas que mostram dados sobre um canal específico de primeiro ou de último contato. Nesses relatórios, é possível decompor canais e mostrar os detalhes de cada um. Se o AdLens estiver ativado, você verá classificações em seus relatórios de canal de relatórios e análises de marketing.

**[!UICONTROL Relatório de primeiro ou de último contato]**: exibe detalhes como nomes de páginas e referenciadores, que são coletados dos valores do canal que você configurou na opção "[!UICONTROL Definir o valor do canal para]" ao configurar as regras. Os Relatórios de detalhes do canal permitem examinar detalhadamente os valores de detalhes do relatório de visão geral.

Para obter informações mais detalhadas sobre a configuração de canais de marketing em relatórios e análises de marketing, consulte o sistema de [Ajuda de canais de marketing](https://marketing.adobe.com/resources/help/en_US/mchannel/index.html).
