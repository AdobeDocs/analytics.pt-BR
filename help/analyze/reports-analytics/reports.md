---
title: Relatórios
description: As dimensões e métricas usadas pelo Relatórios e análises para cada relatório.
translation-type: tm+mt
source-git-commit: 1968162d856b6a74bc61f22f2e5a6b1599d04c79
workflow-type: tm+mt
source-wordcount: '1863'
ht-degree: 1%

---


# Relatórios

Cada relatório no Relatórios e análises usa uma dimensão dedicada e uma métrica padrão. Você pode alterar a métrica em cada relatório e adicionar detalhamentos, se desejar. As listas a seguir fornecem qual dimensão é usada em cada relatório.

> [!NOTE] O menu de relatórios pode parecer diferente dependendo das personalizações feitas por um administrador em sua organização. See [Menu customizing](/help/admin/admin/customize-menus.md) in the Admin user guide.

## Métricas de site 

Contém relatórios que geralmente tendem usando um intervalo de datas. Também contém relatórios exclusivos, como Relatórios recomendados e Relatórios em tempo real.

* Meus relatórios recomendados: Cria um painel que contém vários reportlets para obter insights imediatos.
* Métricas principais: Um relatório que permite analisar a tendência de até cinco métricas por vez. visualizações [de](/help/components/metrics/page-views.md)página de tendência, [visitas](/help/components/metrics/visits.md)e visitantes [](/help/components/metrics/unique-visitors.md) únicos por padrão.
* visualizações de página: Executa a tendência da métrica visualizações [da](/help/components/metrics/page-views.md) página ao longo do tempo.
* Visitas: Executa a tendência da métrica [Visitas](/help/components/metrics/visits.md) ao longo do tempo.
* Visitantes: Executa a tendência de várias métricas de visitantes [](/help/components/metrics/unique-visitors.md) únicos ao longo do tempo.
   * visitantes únicos: Conta visitantes somente uma vez para todo o intervalo de datas selecionado.
   * visitantes únicos por hora: Conta visitantes várias vezes se visitarem durante horas diferentes do intervalo de datas selecionado.
   * visitantes únicos diários: Conta visitantes várias vezes se visitarem durante dias diferentes do intervalo de datas selecionado.
   * visitantes únicos por semana: Conta visitantes várias vezes se visitarem durante semanas diferentes do intervalo de datas selecionado.
   * visitantes únicos mensais: Conta visitantes várias vezes se visitarem durante meses diferentes do intervalo de datas selecionado.
   * visitantes únicos trimestrais: Conta visitantes várias vezes se visitarem durante diferentes trimestres do intervalo de datas selecionado. Os trimestres são janeiro-março, abril-junho, julho-setembro e outubro-dezembro.
   * visitantes únicos anuais: Conta visitantes várias vezes se visitarem durante anos civis diferentes do intervalo de datas selecionado.
* Tempo gasto por visita: Usa a dimensão [Tempo gasto por visita - segmentado](/help/components/dimensions/time-spent-per-visit.md) .
* Tempo antes do evento: Usa o [Tempo antes da dimensão do evento](/help/components/dimensions/time-prior-to-event.md) .
* Compras: Contém relatórios sobre métricas baseadas em compras.
   * Funil de conversão de compra: Relatório de [visitas](/help/components/metrics/visits.md), [carrinhos](/help/components/metrics/carts.md), [pedidos](/help/components/metrics/orders.md), [receita](/help/components/metrics/revenue.md)e [unidades](/help/components/metrics/units.md) em um relatório de funil. Uma visualização semelhante é obtida na área de trabalho da Análise usando a visualização [Fallout](../analysis-workspace/visualizations/fallout/fallout-flow.md).
   * Receita: Executa a tendência da métrica [Receita](/help/components/metrics/revenue.md) ao longo do tempo.
   * Pedidos: Executa a tendência de [Pedidos](/help/components/metrics/orders.md) de métrica ao longo do tempo.
   * Unidades: Executa a tendência das [Unidades](/help/components/metrics/units.md) métricas ao longo do tempo.
* Carrinho de compras: Contém relatórios sobre métricas do carrinho de compras.
   * Funil de conversão do carrinho: Relatórios de [instâncias](/help/components/metrics/instances.md), [carrinhos](/help/components/metrics/carts.md), [check-outs](/help/components/metrics/checkouts.md), [pedidos](/help/components/metrics/orders.md)e [receita](/help/components/metrics/revenue.md) em um relatório de funil.
   * Carrinhos: Executa a tendência da métrica [Carrinhos](/help/components/metrics/carts.md) ao longo do tempo.
   * visualizações do carrinho: Tendência da métrica visualizações [do](/help/components/metrics/cart-views.md) carrinho ao longo do tempo.
   * Adições ao carrinho: Executa a tendência das adições [métricas ao](/help/components/metrics/cart-additions.md) carrinho ao longo do tempo.
   * Remoções do carrinho: Executa a tendência das remoções [do](/help/components/metrics/cart-removals.md) carrinho ao longo do tempo.
   * Finalizações: Executa a tendência dos [Check-outs](/help/components/metrics/checkouts.md) da métrica ao longo do tempo.
* eventos personalizados: Contém todos os relatórios sobre [Eventos](/help/components/metrics/custom-events.md) personalizados específicos para sua implementação.
* Bots: Mostra relatórios relacionados ao robô.
   * Bots: Mostra os bots que mais frequentam seu site. See [Bot rules](../../admin/admin/bot-removal/bot-rules.md) in the Admin user guide.
   * Páginas de bot: Mostra as páginas que mais acessaram os bots.
* Tempo real: Mostra determinadas dimensões e métricas em segundos após a coleta de dados. See [Real-time reports](/help/components/c-real-time-reporting/realtime.md) for more information.

## Conteúdo do site

Contém relatórios sobre dimensões que normalmente exibem o conteúdo do site. É possível aplicar classificações a alguns desses relatórios. Aplicar classificações significa que um relatório se torna um menu que contém o relatório de origem e os relatórios de classificação.

* Páginas: Usa a dimensão [Página](/help/components/dimensions/page.md) .
* Seção do site: Usa a dimensão da seção [](/help/components/dimensions/site-section.md) Site.
* Servidores: Usa a dimensão [Servidor](/help/components/dimensions/server.md) .
* Links: Contém relatórios que usam rastreamento de link.
   * Links de saída: Usa a dimensão de link [](/help/components/dimensions/exit-link.md) Sair.
   * Downloads de arquivos: Usa a dimensão do link [](/help/components/dimensions/download-link.md) Download.
   * Links personalizados: Usa a dimensão de link [](/help/components/dimensions/custom-link.md) Personalizado.
   * Páginas não encontradas: Usa a dimensão [Páginas não encontradas](/help/components/dimensions/pages-not-found.md) .

## Dispositivo móvel

Contém relatórios sobre relatórios móveis herdados. Esses relatórios baseiam seus dados na sequência do agente do usuário. Eles usam várias dimensões [](/help/components/dimensions/mobile-dimensions.md) móveis para seus respectivos relatórios.

* Dispositivos: Usa a dimensão do dispositivo [](/help/components/dimensions/mobile-dimensions.md) móvel.
* Tipo de dispositivo: Usa a dimensão de tipo [de dispositivo](/help/components/dimensions/mobile-dimensions.md) móvel.
* Fabricante: Usa a dimensão do fabricante [do](/help/components/dimensions/mobile-dimensions.md) Mobile.
* Tamanho da tela: Usa a dimensão de tamanho [de tela do](/help/components/dimensions/mobile-dimensions.md) Mobile.
* Altura da tela: Usa a dimensão de altura [da tela](/help/components/dimensions/mobile-dimensions.md) Móvel.
* Largura da tela: Usa a dimensão de largura [da tela](/help/components/dimensions/mobile-dimensions.md) Móvel.
* Suporte a cookies: Usa a dimensão de suporte [a cookies do](/help/components/dimensions/mobile-dimensions.md) Mobile.
* Suporte de imagem: Usa a dimensão de suporte [de imagem do](/help/components/dimensions/mobile-dimensions.md) Mobile.
* Intensidade de cor: Usa a dimensão de profundidade [de cor do](/help/components/dimensions/mobile-dimensions.md) Mobile.
* Suporte de áudio: Usa a dimensão de suporte [de áudio](/help/components/dimensions/mobile-dimensions.md) móvel.
* Suporte de vídeo: Usa a dimensão de suporte [a vídeo](/help/components/dimensions/mobile-dimensions.md) móvel.
* Sistema operacional (obsoleto): Usa a dimensão do sistema operacional [móvel (obsoleto)](/help/components/dimensions/mobile-dimensions.md) .

## Caminhos

Contém relatórios que permitem visualizar os dados de definição de caminho para visitantes.

* Fluxo da próxima página: Usa um relatório de fluxo no valor da dimensão da página superior. visualizações de caminho são semelhantes a [Instâncias](/help/components/metrics/instances.md). Você pode alterar o valor da dimensão reportada. Um relatório semelhante na área de trabalho da Análise está disponível usando uma visualização [de](../analysis-workspace/visualizations/c-flow/flow.md)Fluxo.
* Próxima página: Pega o valor da dimensão da página superior e mostra as páginas seguintes para as quais os visitantes foram.
* Fluxo de página anterior: Usa um relatório de fluxo no valor da dimensão da página superior Um relatório semelhante na área de trabalho de Análise está disponível usando uma visualização [de](../analysis-workspace/visualizations/c-flow/flow.md)Fluxo.
* Página anterior: Pega o valor da dimensão da página superior e mostra de onde vieram os visitantes de páginas anteriores.
* Fallout: Permite selecionar valores de dimensão de página em etapas e mostra a proporção de pessoas que seguiram ou não esse caminho. Um relatório semelhante na área de trabalho da Análise está disponível usando uma visualização [de Fallout](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Caminhos completos: Mostra caminhos individuais como valores de dimensão. Aposentado na área de trabalho da Análise; use a visualização [](../analysis-workspace/visualizations/c-flow/flow.md) de Fluxo.
* PathFinder: Fornece vários tipos de relatórios que permitem analisar caminhos (desativados na área de trabalho da Análise).
* Comprimento do caminho: Usa a dimensão de profundidade [da](/help/components/dimensions/visit-depth.md) Visita.
* Análise de página
   * Resumo da página: Obtém o valor da dimensão da página superior e mostra uma visualização com tendência. Também mostra pontos de entrada, páginas anteriores, pontos de saída e próximas páginas para o valor da dimensão da página superior.
   * Recarregamentos: Usa a dimensão [Página](/help/components/dimensions/page.md) com a métrica [Recarregamentos](/help/components/metrics/reloads.md) .
   * Tempo gasto na página: Usa o [Tempo gasto na dimensão segmentada](/help/components/dimensions/time-spent-on-page.md) da página.
   * Cliques na página: Obtém o valor da dimensão da página superior e mostra o número de cliques necessários para chegar a essa página em uma determinada visita.
* Entradas e saídas
   * Páginas de entrada: Usa a dimensão de páginas [de](/help/components/dimensions/entry-dimensions.md) entrada.
   * Páginas de entrada originais: Usa a dimensão original [da página](/help/components/dimensions/entry-dimensions.md) Entrada.
   * Visitas únicas à página: Usa a dimensão [Página](/help/components/dimensions/page.md) com o segmento &quot;Visitas únicas à página&quot; fornecido pela Adobe aplicado.
   * Páginas de saída: Usa a dimensão [Sair das páginas](/help/components/dimensions/exit-dimensions.md) .

> [!NOTE] Outros relatórios podem aparecer nesta pasta. São outras dimensões, como props, nas quais a definição de [caminho está ativada](../../admin/admin/c-traffic-variables/traffic-var.md) nas configurações do conjunto de relatórios.

## Fontes de tráfego

Contém um relatório que fornece informações de onde os visitantes vieram antes de chegar ao seu site. Esses relatórios não funcionam corretamente a menos que você defina corretamente filtros [de URL](../../admin/admin/internal-url-filter-admin.md) internos nas configurações do conjunto de relatórios.

* Palavras-chave de pesquisa - todas: Usa a dimensão [Pesquisar palavra-chave](/help/components/dimensions/search-keyword.md) .
* Palavras-chave de pesquisa - pagas: Usa a palavra-chave [Pesquisar - dimensão paga](/help/components/dimensions/search-keyword.md) .
* Palavras-chave de pesquisa - naturais: Usa a palavra-chave [Pesquisar - dimensão natural](/help/components/dimensions/search-keyword.md)
* Mecanismos de pesquisa - todos: Usa a dimensão do mecanismo [de](/help/components/dimensions/search-engine.md) pesquisa.
* Mecanismos de pesquisa - pagos: Usa o mecanismo [de pesquisa - dimensão paga](/help/components/dimensions/search-engine.md) .
* Mecanismos de busca - naturais: Usa o mecanismo [de pesquisa - dimensão natural](/help/components/dimensions/search-engine.md) .
* Toda a classificação da página de pesquisa: Usa a dimensão de classificação [da página de pesquisa](/help/components/dimensions/all-search-page-rank.md) Todos.
* Domínios de referência: Usa a dimensão de domínio [de](/help/components/dimensions/referring-domain.md) referência
* Domínios de referência originais: Usa a dimensão de domínio [de referência](/help/components/dimensions/original-referring-domain.md) Original
* Quens indicou: Usa a dimensão de [Quem indicou](/help/components/dimensions/referrer.md) .
* Tipos de Quem indicou: Usa a dimensão do tipo [de](/help/components/dimensions/referrer-type.md) Quem indicou.

## Campanhas

Contém relatórios principalmente sobre a dimensão do código [de](/help/components/dimensions/tracking-code.md) rastreamento.

* Funil de conversão de Campanha: Relatórios de click-throughs, [Check-outs](/help/components/metrics/checkouts.md), [Pedidos](/help/components/metrics/orders.md)e [Receita](/help/components/metrics/revenue.md) em um relatório de funil. A métrica click-throughs é semelhante à métrica [Instâncias](/help/components/metrics/instances.md) no contexto da dimensão do código [de](/help/components/dimensions/tracking-code.md) rastreamento. Uma visualização semelhante é obtida na área de trabalho da Análise usando a visualização [Fallout](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Código de rastreamento: Usa a dimensão do código [de](/help/components/dimensions/tracking-code.md) rastreamento.

## Produtos

Contém relatórios principalmente em torno da dimensão [Produto](/help/components/dimensions/product.md) .

* Funil de conversão de produtos: Relatórios de visualizações [de](/help/components/metrics/product-views.md)produtos, adições [ao](/help/components/metrics/cart-additions.md)carrinho, [Check-outs](/help/components/metrics/checkouts.md), [Pedidos](/help/components/metrics/orders.md), [Unidades](/help/components/metrics/units.md)[](/help/components/metrics/revenue.md) e Receita, em um relatório de funil. Uma visualização semelhante é obtida na área de trabalho da Análise usando a visualização [Fallout](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Produtos: Usa a dimensão [Produtos](/help/components/dimensions/product.md) .
* Venda cruzada: Mostra produtos comumente vendidos juntos (desativados na área de trabalho da Análise).
* Categorias: Usa a dimensão de [Categoria](/help/components/dimensions/category.md) .

## Retenção de visitante

Contém relatórios sobre visitantes que retornam ao site.

* Frequência de retorno: Usa a dimensão de frequência [de](/help/components/dimensions/return-frequency.md) retorno.
* Visitas de retorno: Executa a tendência da métrica [Visitas](/help/components/metrics/visits.md) ao longo do tempo com o segmento &quot;Visitas de retorno&quot; fornecido pela Adobe aplicado.
* Número da visita: Usa a dimensão de número [de](/help/components/dimensions/visit-number.md) Visita.
* Ciclo de vendas: Pasta para relatórios relacionados à compra.
   * Fidelidade do cliente: Usa a dimensão de fidelidade [do](/help/components/dimensions/customer-loyalty.md) Cliente.
   * Dias antes da primeira compra: Usa a dimensão [Dias antes da primeira compra](/help/components/dimensions/days-before-first-purchase.md) .
   * Dias desde a última compra: Usa a dimensão [Dias desde a última compra](/help/components/dimensions/days-since-last-purchase.md) .
   * Clientes únicos diários: Tendências de visitantes [](/help/components/metrics/unique-visitors.md) únicos diários ao longo do tempo com o segmento &quot;compradores&quot; fornecido pela Adobe aplicado.
   * Clientes únicos por semana: Tendência de visitantes [](/help/components/metrics/unique-visitors.md) únicos por semana com o passar do tempo com o segmento &quot;compradores&quot; fornecido pela Adobe aplicado.
   * Clientes únicos mensais: Tendência de visitantes [](/help/components/metrics/unique-visitors.md) únicos mensais ao longo do tempo com o segmento &quot;compradores&quot; fornecido pela Adobe aplicado.
   * Clientes únicos trimestrais: Tendências de visitantes [](/help/components/metrics/unique-visitors.md) únicos trimestrais ao longo do tempo com o segmento &quot;compradores&quot; fornecido pela Adobe aplicado. Os trimestres são janeiro-março, abril-junho, julho-setembro e outubro-dezembro.
   * Clientes únicos anuais: Tendências visitantes [únicos](/help/components/metrics/unique-visitors.md) anuais com o passar do tempo com o segmento &quot;compradores&quot; fornecido pela Adobe aplicado.

## Perfil do visitante

Contém relatórios sobre quem visita seu site.

* Geosegmentação: Relatos sobre de onde vieram as ocorrências no mundo inteiro do site.
   * Países: Usa a dimensão [Países](/help/components/dimensions/countries.md) .
   * Região: Usa a dimensão [Regiões](/help/components/dimensions/regions.md) .
   * Cidades: Usa a dimensão [Cidades](/help/components/dimensions/cities.md) .
   * Estados dos EUA: Usa a dimensão de estados [dos](/help/components/dimensions/us-states.md) EUA.
   * DMA EUA: Usa a dimensão [US DMA](/help/components/dimensions/us-dma.md) .
* Idiomas: Usa a dimensão [Idioma](/help/components/dimensions/language.md) .
* Fusos horários: Usa a dimensão de fuso horário (desativada na área de trabalho da Análise). Os valores de dimensão são o deslocamento GMT da ocorrência.
* Domínio: Usa a dimensão [Domínio](/help/components/dimensions/domain.md) .
* Domínio de nível superior: Usa a dimensão de domínio de nível superior (removida na área de trabalho de Análise). Ela agrupa a dimensão de [domínios](/help/components/dimensions/domain.md) em categorias de nível superior, normalmente por país do domínio.
* Tecnologia: Pasta que contém relatórios sobre o que o visitante usou para acessar seu site.
   * Navegadores: Usa a dimensão [Navegadores](/help/components/dimensions/browser.md) .
   * Tipo de navegador: Usa a dimensão do tipo [](/help/components/dimensions/browser-type.md) Navegador.
   * Largura do navegador: Usa a dimensão Largura do [navegador - segmentado](/help/components/dimensions/browser-width.md) .
   * Altura do navegador: Usa a dimensão Altura [do navegador - segmentado](/help/components/dimensions/browser-height.md) .
   * Sistema operacional: Usa a dimensão de sistemas [](/help/components/dimensions/operating-systems.md) operacionais.
   * Tipo de sistema operacional: Usa a dimensão de tipos [de sistema](/help/components/dimensions/operating-system-types.md) operacional.
   * Intensidade de cor do monitor: Usa a dimensão de profundidade [de](/help/components/dimensions/color-depth.md) cor.
   * Resolução do monitor: Usa a dimensão de resolução [do](/help/components/dimensions/monitor-resolution.md) Monitor.
   * Java: Usa a dimensão habilitada [para](/help/components/dimensions/java-enabled.md) Java.
   * JavaScript: Usa a dimensão habilitada para JavaScript (removida na área de trabalho da Análise). Os valores de dimensão são &#39;Enabled&#39;, &#39;Disabled&#39; ou &#39;Unknown&#39;, dependendo se o navegador tiver o JavaScript ativado.
   * Versão do JavaScript: usa a dimensão da versão do JavaScript (desativada na área de trabalho da Análise). Os valores de dimensão mostram a versão do JavaScript que o navegador usa.
   * Cookies: Usa a dimensão de suporte [a](/help/components/dimensions/cookie-support.md) cookies.
   * Tipos de conexão: Usa a dimensão Tipo [de](/help/components/dimensions/connection-type.md) conexão.
   * Operadora de celular: Usa a dimensão Operadora [](/help/components/dimensions/mobile-dimensions.md) móvel.
* Estado do Visitante: Usa a dimensão Estado (desativada na área de trabalho da Análise). Os valores de dimensão são originários da [`state`](../../implement/vars/page-vars/state.md) variável.
* CEP/código postal do Visitante: Usa a dimensão [CEP](/help/components/dimensions/zip-code.md) .

## Conversão personalizada

Contém relatórios específicos para sua implementação. Os relatórios de conversão personalizados usam [eVars](/help/components/dimensions/evar.md) como dimensão.

## Tráfego personalizado

Contém relatórios específicos para sua implementação. Os relatórios de tráfego personalizados usam [props](/help/components/dimensions/prop.md) como dimensão.

## Canais de marketing

Contém relatórios que envolvem canais [de marketing](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

* Relatório de visão geral do Canal: Um relatório personalizado específico para Relatórios e análises. Usa canais de marketing como valores de dimensão, com métricas que usam atribuição de primeiro ou último toque.
* canal de primeiro toque: Usa a dimensão canal [de](/help/components/dimensions/first-touch-channel.md) primeiro toque.
* Detalhes do canal de primeiro toque: Usa a dimensão de detalhes [do canal de](/help/components/dimensions/first-touch-detail.md) primeiro toque.
* canal de último toque: Usa a dimensão canal [](/help/components/dimensions/last-touch-channel.md) de último toque.
* Detalhe do canal de último toque: Usa a dimensão de detalhes [do canal de](/help/components/dimensions/last-touch-detail.md) último toque.

## Marcadores

Contém relatórios que você marcou. Consulte [Marcadores](bookmarks.md) para obter mais informações.

## Painéis

Contém painéis que você criou. Consulte [Painéis](dashboard.md) para obter mais informações.

## Metas

Contém públicos alvos que você criou. Consulte [Públicos alvos](targets.md) para obter mais informações.

> [!NOTE] Se você não conseguir encontrar seu relatório nesta página de ajuda, é possível que o administrador tenha renomeado ou ajustado as pastas. See [Menu customizing](/help/admin/admin/customize-menus.md) in the Admin user guide.
