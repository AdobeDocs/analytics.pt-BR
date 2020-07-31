---
title: Relatórios
description: As dimensões e métricas que o Reports & Analytics usa para cada relatório.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '1863'
ht-degree: 88%

---


# Relatórios

Cada relatório no Reports &amp; Analytics usa uma dimensão dedicada e uma métrica padrão. Você pode alterar a métrica em cada relatório e adicionar detalhamentos, se desejar. As listas a seguir fornecem qual dimensão é usada em cada relatório.

>[!NOTE]
>
>O menu de relatórios pode parecer diferente dependendo das personalizações feitas por um administrador em sua organização. Consulte [Personalização de menu](/help/admin/admin/customize-menus.md) no Guia do usuário de administração.

## Métricas de site

Contém relatórios que geralmente usam um intervalo de datas. Também contém relatórios exclusivos, como Relatórios recomendados e Relatórios em tempo real.

* Meus relatórios recomendados: cria um painel que contém vários reportlets para obter insights imediatos.
* Métricas principais: um relatório que permite analisar a tendência de até cinco métricas por vez. Exibe a tendência de [Exibições de página](/help/components/metrics/page-views.md), [visitas](/help/components/metrics/visits.md) e [visitantes únicos](/help/components/metrics/unique-visitors.md) por padrão.
* Exibição de página: exibe a tendência da métrica [Exibições de página](/help/components/metrics/page-views.md) ao longo do tempo.
* Visitas: exibe a tendência da métrica [Visitas](/help/components/metrics/visits.md) ao longo do tempo.
* Visitantes: exibe a tendência de várias métricas de [Visitantes únicos](/help/components/metrics/unique-visitors.md) ao longo do tempo.
   * Visitantes únicos: conta visitantes somente uma vez em todo o intervalo de datas selecionado.
   * Visitantes únicos por hora: conta visitantes várias vezes se visitarem durante horas diferentes do intervalo de datas selecionado.
   * Visitantes únicos diários: conta visitantes várias vezes se visitarem durante dias diferentes do intervalo de datas selecionado.
   * Visitantes únicos por semana: conta visitantes várias vezes se visitarem durante semanas diferentes do intervalo de datas selecionado.
   * Visitantes únicos mensais: conta visitantes várias vezes se visitarem durante meses diferentes do intervalo de datas selecionado.
   * Visitantes únicos trimestrais: conta visitantes várias vezes se visitarem durante diferentes trimestres do intervalo de datas selecionado. Os trimestres são janeiro a março, abril a junho, julho a setembro e outubro a dezembro.
   * Visitantes únicos anuais: conta visitantes várias vezes se visitarem durante anos diferentes do intervalo de datas selecionado.
* Tempo gasto por visita: usa a dimensão [Tempo gasto por visita - segmentado](/help/components/dimensions/time-spent-per-visit.md).
* Tempo antes do evento: usa a dimensão [Tempo antes do evento](/help/components/dimensions/time-prior-to-event.md).
* Compras: contém relatórios sobre métricas de compras.
   * Funil de conversão de compra: Relatório de [visitas](/help/components/metrics/visits.md), [carrinhos](/help/components/metrics/carts.md), [pedidos](/help/components/metrics/orders.md), [receita](/help/components/metrics/revenue.md) e [unidades](/help/components/metrics/units.md) em um relatório de funil. Uma visualização semelhante é obtida no Analysis Workspace usando a [Visualização de fallout](../analysis-workspace/visualizations/fallout/fallout-flow.md).
   * Receita: exibe a tendência da métrica [Receita](/help/components/metrics/revenue.md) ao longo do tempo.
   * Pedidos: exibe a tendência da métrica [Pedidos](/help/components/metrics/orders.md) ao longo do tempo.
   * Unidades: exibe a tendência da métrica [Unidades](/help/components/metrics/units.md) ao longo do tempo.
* Carrinho de compras: contém relatórios sobre métricas do carrinho de compras.
   * Funil de conversão do carrinho: Relatórios de [instâncias](/help/components/metrics/instances.md), [carrinhos](/help/components/metrics/carts.md), [check-outs](/help/components/metrics/checkouts.md), [pedidos](/help/components/metrics/orders.md) e [receita](/help/components/metrics/revenue.md) em um relatório de funil.
   * Carrinhos: exibe a tendência da métrica [Carrinhos](/help/components/metrics/carts.md) ao longo do tempo.
   * Visualizações do carrinho: exibe a tendência da métrica [Visualizações do carrinho](/help/components/metrics/cart-views.md) ao longo do tempo.
   * Adições ao carrinho: exibe a tendência da métrica [Adições ao carrinho](/help/components/metrics/cart-additions.md) ao longo do tempo.
   * Remoções do carrinho: exibe a tendência da métrica [Remoções do carrinho](/help/components/metrics/cart-removals.md) ao longo do tempo.
   * Check-outs: exibe a tendência da métrica [Check-outs](/help/components/metrics/checkouts.md) ao longo do tempo.
* Eventos personalizados: contém todos os relatórios sobre [Eventos](/help/components/metrics/custom-events.md) personalizados específicos para sua implementação.
* Bots: mostra relatórios relacionados a bots.
   * Bots: mostra os bots que mais frequentam seu site. Consulte [Regras de bot](../../admin/admin/bot-removal/bot-rules.md) no Guia do usuário de administração.
   * Páginas de bot: mostra as páginas que mais acessaram os bots.
* Tempo real: mostra determinadas dimensões e métricas segundos após a coleta de dados. Consulte [Relatórios em tempo real](/help/components/c-real-time-reporting/realtime.md) para obter mais informações.

## Conteúdo do site

Contém relatórios sobre dimensões que normalmente exibem o conteúdo do site. É possível aplicar classificações a alguns desses relatórios. Aplicar classificações significa que um relatório se torna um menu que contém o relatório de origem e os relatórios de classificação.

* Páginas: usa a dimensão [Página](/help/components/dimensions/page.md).
* Seção do site: usa a dimensão [Seção do site](/help/components/dimensions/site-section.md).
* Servidores: usa a dimensão [Servidor](/help/components/dimensions/server.md).
* Links: contém relatórios que usam rastreamento de link.
   * Links de saída: usa a dimensão de link [Link de saída](/help/components/dimensions/exit-link.md).
   * Downloads de arquivos: usa a dimensão do link [Download](/help/components/dimensions/download-link.md).
   * Links personalizados: usa a dimensão [Link personalizado](/help/components/dimensions/custom-link.md).
   * Páginas não encontradas: usa a dimensão [Páginas não encontradas](/help/components/dimensions/pages-not-found.md).

## Dispositivos móveis

Contém relatórios sobre relatórios móveis herdados. Esses relatórios baseiam seus dados na sequência do agente do usuário. Eles usam várias [dimensões móveis](/help/components/dimensions/mobile-dimensions.md) para seus respectivos relatórios.

* Dispositivos: usa a dimensão [Dispositivo móvel](/help/components/dimensions/mobile-dimensions.md).
* Tipo de dispositivo: usa a dimensão [Tipo de dispositivo móvel](/help/components/dimensions/mobile-dimensions.md).
* Fabricante: usa a dimensão [Fabricante do dispositivo móvel](/help/components/dimensions/mobile-dimensions.md).
* Tamanho da tela: usa a dimensão [Tamanho da tela do dispositivo móvel](/help/components/dimensions/mobile-dimensions.md).
* Altura da tela: usa a dimensão [Altura da tela do dispositivo móvel](/help/components/dimensions/mobile-dimensions.md).
* Largura da tela: usa a dimensão [Altura da tela do dispositivo móvel](/help/components/dimensions/mobile-dimensions.md).
* Suporte a cookies: usa a dimensão [Suporte a cookies móveis](/help/components/dimensions/mobile-dimensions.md).
* Suporte à imagem: usa a dimensão [Suporte à imagem do dispositivo móvel](/help/components/dimensions/mobile-dimensions.md).
* Intensidade de cor: usa a dimensão [Intensidade de cor do dispositivo móvel](/help/components/dimensions/mobile-dimensions.md).
* Suporte ao áudio: usa a dimensão [Suporte ao áudio do dispositivo móvel](/help/components/dimensions/mobile-dimensions.md).
* Suporte ao vídeo: usa a dimensão [Suporte ao vídeo do dispositivo móvel](/help/components/dimensions/mobile-dimensions.md).
* Sistema operacional (obsoleto): usa a dimensão [Sistema operacional do dispositivo móvel (obsoleto)](/help/components/dimensions/mobile-dimensions.md).

## Caminhos

Contém relatórios que permitem visualizar os dados de definição de caminho para visitantes.

* Fluxo da próxima página: Usa um relatório de fluxo no item de dimensão da página superior. Visualizações de caminho são semelhantes a [Instâncias](/help/components/metrics/instances.md). Você pode alterar o item de dimensão relatado. Um relatório semelhante no Analysis Workspace está disponível usando uma [Visualização de fluxo](../analysis-workspace/visualizations/c-flow/flow.md).
* Próxima página: Pega o item de dimensão da página superior e mostra as páginas seguintes para as quais os visitantes foram.
* Previous page flow: Uses a flow report on the top page dimension item A similar report in Analysis Workspace is available using a [Flow visualization](../analysis-workspace/visualizations/c-flow/flow.md).
* Página anterior: Pega o item de dimensão da página superior e mostra de onde vieram os visitantes de páginas anteriores.
* Fallout: Permite que você selecione itens de dimensão de página em etapas e mostra a proporção de pessoas que seguiram ou não esse caminho. Um relatório semelhante no Analysis Workspace está disponível usando uma [Visualização de fallout](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Caminhos completos: Mostra caminhos individuais como itens de dimensão. Descontinuado no Analysis Workspace; use a [Visualização de fluxo](../analysis-workspace/visualizations/c-flow/flow.md).
* PathFinder: fornece vários tipos de relatórios que permitem analisar caminhos (descontinuado no Analysis Workspace).
* Comprimento do caminho: usa a dimensão [Profundidade da visita](/help/components/dimensions/visit-depth.md).
* Análise de página
   * Resumo da página: Pega o item de dimensão da página superior e mostra uma visualização de tendência. Também mostra pontos de entrada, páginas anteriores, pontos de saída e próximas páginas para o item de dimensão da página superior.
   * Recarregamentos: usa a dimensão [Página](/help/components/dimensions/page.md) com a métrica [Recarregamentos](/help/components/metrics/reloads.md).
   * Tempo gasto na página: usa a dimensão [Tempo gasto na página - segmentado](/help/components/dimensions/time-spent-on-page.md).
   * Cliques na página: Pega o item de dimensão da página superior e mostra o número de cliques necessários para chegar a essa página em uma determinada visita.
* Entradas e saídas
   * Páginas de entrada: usa a dimensão [Páginas de entrada](/help/components/dimensions/entry-dimensions.md).
   * Páginas de entrada originais: usa a dimensão [Página de entrada original](/help/components/dimensions/entry-dimensions.md).
   * Visitas únicas à página: usa a dimensão [Página](/help/components/dimensions/page.md) com o segmento &quot;Visitas únicas à página&quot; fornecido pela Adobe aplicado.
   * Páginas de saída: usa a dimensão [Páginas de saída](/help/components/dimensions/exit-dimensions.md).

>[!NOTE]
>
>Outros relatórios podem aparecer nesta pasta. São outras dimensões, como props, nas quais a [definição de caminho está ativada](../../admin/admin/c-traffic-variables/traffic-var.md) nas configurações do conjunto de relatórios.

## Fontes de tráfego

Contém um relatório que fornece informações de onde os visitantes vieram antes de chegar ao seu site. Esses relatórios não funcionam corretamente a menos que você defina corretamente [Filtros de URL internos](../../admin/admin/internal-url-filter-admin.md) nas configurações do conjunto de relatórios.

* Palavras-chave de pesquisa - todas: usa a dimensão [Palavra-chave de pesquisa](/help/components/dimensions/search-keyword.md).
* Palavras-chave de pesquisa - pagas: Usa a dimensão [Palavras-chave de pesquisa - pagas](/help/components/dimensions/search-keyword.md).
* Palavras-chave de pesquisa - naturais: usa a dimensão [Palavra-chave de pesquisa - natural](/help/components/dimensions/search-keyword.md)
* Mecanismos de pesquisa - todos: usa a dimensão [Mecanismo de pesquisa](/help/components/dimensions/search-engine.md).
* Mecanismos de pesquisa - pagos: usa a dimensão [Mecanismo de pesquisa - pago](/help/components/dimensions/search-engine.md).
* Mecanismos de pesquisa - naturais: usa a dimensão [Mecanismo de pesquisa - natural](/help/components/dimensions/search-engine.md).
* Toda a classificação da página de pesquisa: usa a dimensão [Toda a classificação da página de pesquisa](/help/components/dimensions/all-search-page-rank.md).
* Domínios de referência: usa a dimensão [Domínio de referência](/help/components/dimensions/referring-domain.md)
* Domínios de referência originais: usa a dimensão [Domínio de referência original](/help/components/dimensions/original-referring-domain.md)
* Referenciadores: usa a dimensão [Referenciador](/help/components/dimensions/referrer.md).
* Tipos de referenciador: usa a dimensão [Tipo de referenciador](/help/components/dimensions/referrer-type.md).

## Campanhas

Contém relatórios principalmente sobre a dimensão [Código de rastreamento](/help/components/dimensions/tracking-code.md).

* Funil de conversão de campanha: Relatórios de click-throughs, [Check-outs](/help/components/metrics/checkouts.md), [Pedidos](/help/components/metrics/orders.md) e [Receita](/help/components/metrics/revenue.md) em um relatório de funil. A métrica click-throughs é semelhante à métrica [Instâncias](/help/components/metrics/instances.md) no contexto da dimensão [Código de rastreamento](/help/components/dimensions/tracking-code.md). Uma visualização semelhante é obtida no Analysis Workspace usando a [Visualização de fallout](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Código de rastreamento: usa a dimensão [Código de rastreamento](/help/components/dimensions/tracking-code.md).

## Produtos

Contém relatórios principalmente sobre a dimensão [Produto](/help/components/dimensions/product.md).

* Funil de conversão de produtos: Relatórios de [Visualizações de produto](/help/components/metrics/product-views.md), [Adições ao carrinho](/help/components/metrics/cart-additions.md), [Check-outs](/help/components/metrics/checkouts.md), [Pedidos](/help/components/metrics/orders.md), [Unidades](/help/components/metrics/units.md) e [Receita](/help/components/metrics/revenue.md) em um relatório de funil. Uma visualização semelhante é obtida no Analysis Workspace usando a [Visualização de fallout](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Produtos: usa a dimensão [Produtos](/help/components/dimensions/product.md).
* Venda cruzada: mostra produtos comumente vendidos juntos (descontinuado no Analysis Workspace).
* Categorias: usa a dimensão [Categoria](/help/components/dimensions/category.md).

## Retenção de visitante

Contém relatórios sobre visitantes que retornam ao site.

* Frequência de retorno: usa a dimensão [Frequência de retorno](/help/components/dimensions/return-frequency.md).
* Visitas de retorno: exibe a tendência da métrica [Visitas](/help/components/metrics/visits.md) ao longo do tempo com o segmento &quot;Visitas de retorno&quot; fornecido pela Adobe aplicado.
* Número de visitas: usa a dimensão [Número de visitas](/help/components/dimensions/visit-number.md).
* Ciclo de vendas: pasta para relatórios relacionados à compra.
   * Fidelização do cliente: usa a dimensão [Fidelização do cliente](/help/components/dimensions/customer-loyalty.md).
   * Dias antes da primeira compra: usa a dimensão [Dias antes da primeira compra](/help/components/dimensions/days-before-first-purchase.md).
   * Dias desde a última compra: usa a dimensão [Dias desde a última compra](/help/components/dimensions/days-since-last-purchase.md).
   * Clientes únicos diários: exibe a tendência de [Visitantes únicos diários](/help/components/metrics/unique-visitors.md) ao longo do tempo com o segmento &quot;compradores&quot; fornecido pela Adobe aplicado.
   * Clientes únicos por semana: exibe a tendência de [Visitantes únicos por semana](/help/components/metrics/unique-visitors.md) com o passar do tempo com o segmento &quot;compradores&quot; fornecido pela Adobe aplicado.
   * Clientes únicos mensais: exibe a tendência de [Visitantes únicos mensais](/help/components/metrics/unique-visitors.md) ao longo do tempo com o segmento &quot;compradores&quot; fornecido pela Adobe aplicado.
   * Clientes únicos trimestrais: exibe a tendências de [Visitantes únicos trimestrais](/help/components/metrics/unique-visitors.md) ao longo do tempo com o segmento &quot;compradores&quot; fornecido pela Adobe aplicado. Os trimestres são janeiro a março, abril a junho, julho a setembro e outubro a dezembro.
   * Clientes únicos anuais: exibe a tendências de [Visitantes únicos anuais](/help/components/metrics/unique-visitors.md) com o passar do tempo com o segmento &quot;compradores&quot; fornecido pela Adobe aplicado.

## Perfil do visitante

Contém relatórios sobre quem visita seu site.

* Geossegmentação: relatos sobre de onde vieram as ocorrências do site no mundo inteiro.
   * Países: usa a dimensão [Países](/help/components/dimensions/countries.md).
   * Região: usa a dimensão [Regiões](/help/components/dimensions/regions.md).
   * Cidades: usa a dimensão [Cidades](/help/components/dimensions/cities.md).
   * Estados dos EUA: usa a dimensão [Estados dos EUA](/help/components/dimensions/us-states.md).
   * DMA dos EUA: usa a dimensão [DMA dos EUA](/help/components/dimensions/us-dma.md).
* Idiomas: usa a dimensão [Idioma](/help/components/dimensions/language.md).
* Fusos horários: usa a dimensão fuso horário (descontinuado no Analysis Workspace). Os itens de Dimension são o deslocamento GMT da ocorrência.
* Domínio: usa a dimensão [Domínio](/help/components/dimensions/domain.md).
* Domínio de nível superior: usa a dimensão Domínio de nível superior (descontinuado no Analysis Workspace). Ele agrupa a dimensão [domínios](/help/components/dimensions/domain.md) em categorias de nível superior, normalmente por país do domínio.
* Tecnologia: pasta que contém relatórios sobre o que o visitante usou para acessar seu site.
   * Navegadores: usa a dimensão [Navegadores](/help/components/dimensions/browser.md).
   * Tipo de navegador: usa a dimensão [Tipo de navegador](/help/components/dimensions/browser-type.md).
   * Largura do navegador: usa a dimensão [Largura do navegador - segmentado](/help/components/dimensions/browser-width.md).
   * Altura do navegador: usa a dimensão [Altura do navegador - segmentado](/help/components/dimensions/browser-height.md).
   * Sistema operacional: usa a dimensão [Sistemas operacionais](/help/components/dimensions/operating-systems.md).
   * Tipo de sistema operacional: usa a dimensão [Tipos de sistema operacional](/help/components/dimensions/operating-system-types.md).
   * Intensidade de cor do monitor: usa a dimensão [Intensidade de cor](/help/components/dimensions/color-depth.md).
   * Resolução do monitor: usa a dimensão [Resolução do monitor](/help/components/dimensions/monitor-resolution.md).
   * Java: usa a dimensão [Habilitado para Java](/help/components/dimensions/java-enabled.md).
   * JavaScript: usa a dimensão Habilitado para JavaScript (descontinuado no Analysis Workspace). Os itens de Dimension são &#39;Enabled&#39;, &#39;Disabled&#39; ou &#39;Unknown&#39;, dependendo se o navegador tiver o JavaScript ativado.
   * Versão do JavaScript: usa a dimensão Versão do JavaScript (descontinuado no Analysis Workspace). Os itens de Dimension mostram a versão do JavaScript que o navegador usa.
   * Cookies: Usa a dimensão [Suporte a cookies](/help/components/dimensions/cookie-support.md).
   * Tipos de conexão: usa a dimensão [Tipo de conexão](/help/components/dimensions/connection-type.md).
   * Operadora de celular: usa a dimensão [Operadora de celular](/help/components/dimensions/mobile-dimensions.md).
* Estado do visitante: usa a dimensão Estado (descontinuado no Analysis Workspace). Dimension items originate from the [`state`](../../implement/vars/page-vars/state.md) variable.
* CEP/código postal do visitante: usa a dimensão [CEP](/help/components/dimensions/zip-code.md).

## Conversão personalizada

Contém relatórios específicos para sua implementação. Os relatórios de conversão personalizados usam [eVars](/help/components/dimensions/evar.md) como dimensão.

## Tráfego personalizado

Contém relatórios específicos para sua implementação. Os relatórios de tráfego personalizados usam [props](/help/components/dimensions/prop.md) como dimensão.

## Canais de marketing

Contém relatórios que envolvem [Canais de marketing](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

* Relatório de visão geral do canal: um relatório personalizado específico do Reports &amp; Analytics. Usa canais de marketing como itens de dimensão, com métricas que usam atribuição de primeiro ou último toque.
* Canal de primeiro toque: usa a dimensão [Canal de primeiro toque](/help/components/dimensions/first-touch-channel.md).
* Detalhes do canal de primeiro toque: usa a dimensão [Detalhes do canal de primeiro toque](/help/components/dimensions/first-touch-detail.md).
* Canal de último toque: usa a dimensão [Canal de último toque](/help/components/dimensions/last-touch-channel.md).
* Detalhe do canal de último toque: usa a dimensão [Detalhe do canal de último toque](/help/components/dimensions/last-touch-detail.md).

## Marcadores

Contém relatórios que você marcou. Consulte [Marcadores](bookmarks.md) para obter mais informações.

## Painéis

Contém painéis que você criou. Consulte [Painéis](dashboard.md) para obter mais informações.

## Metas

Contém públicos-alvo que você criou. Consulte [Públicos-alvo](targets.md) para obter mais informações.

>[!NOTE]
>
>Se você não conseguir encontrar seu relatório nesta página de ajuda, é possível que o administrador tenha renomeado ou ajustado as pastas. Consulte [Personalização de menu](/help/admin/admin/customize-menus.md) no Guia do usuário de administração.
