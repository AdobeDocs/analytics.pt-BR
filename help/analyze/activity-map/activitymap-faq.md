---
description: Perguntas frequentes sobre a instalação, configuração e utilização dos recursos no Activity Map.
title: Perguntas frequentes sobre o Activity Map
topic: Activity map
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
translation-type: tm+mt
source-git-commit: 5a8ff1c81644c12f7d00ef147db197f54c48f60c

---


# Perguntas frequentes sobre o Activity Map

Perguntas frequentes sobre a instalação, configuração e utilização dos recursos no Activity Map.

## Implementação e AppMeasurement

**P: Quais são as etapas de implementação para habilitar o novo Activity Map?**

A: Revise [Ativar o Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)

**P: Todos os clientes do Analytics têm acesso à página de Ativação das Ferramentas administrativas no ActivityMap?**

R: Os clientes do Adobe SiteCatalyst não têm acesso à página de Ativação do Admin Console no Activity Map. Somente as empresas sob o contrato Adobe Analytics Standard e Adobe Analytics Premium têm acesso a essa página de configuração.

**P: O novo código AppMeasurement pode ser configurado por meio do Gerenciamento dinâmico de tags (DTM)?**

A: Sim, você pode implementar [](https://marketing.adobe.com/resources/help/en_US/dtm/analytics_dtm.html) manualmente o novo código do AppMeasurement.

**P: Quais são as grandes alterações na biblioteca do AppMeasurement v1.6?**

A: A única alteração no AppMeasurement v1.6 está na metodologia do processo de rastreamento de links do Mapa de Atividades que exige a coleta de Nome da página, ID do link e ID da região.

**P: O AppMeasurement será implantado no nível do domínio em vez de em páginas específicas?**

A: O AppMeasurement é implantado no nível do conjunto de relatórios. O nível do conjunto de relatórios normalmente está associado a um nível de domínio, mas isso difere com cada implementação.

**P: O DTM carrega automaticamente uma versão mais antiga (1.3.4) da API do Visitante do que a desejada pelo mapa de Atividades (1.5.1). Isso é um problema?**

R: Não. A funcionalidade do Mapa de Atividades não depende da API do visitante.

## Aplicativo do Activity Map

<!--**Q: How does Activity Map support Single-Page Applications (SPA)?**

A: 

* Every few seconds, Activity Map scans the web page, looking for changes to the page. ActivityMap finds new content on the page without needing a new page load, but this new content is always attributed to the first pageName found when the page loaded.

* Activity Map checks to see if the visibility of links that it knows about has changed. If a change in visibility is found, then the [Links On Page](/help/analyze/activity-map/activitymap-links-report.md) table's Present column for that link updates with **[!UICONTROL Displayed]** or **[!UICONTROL Hidden]**.

* When user interaction creates new content, any new elements that are found by AppMeasurement to be a link will be added to the **[!UICONTROL Links On Page]** table. Activity Map sends a new data request that includes these new links. The new links should appear in the **[!UICONTROL Links On Page]** table when the data request is handled by the UI.-->

**P: O Mapa de Atividades fornece dados sobre &quot;visualização&quot;?**

A: Não, a Adobe não rastreia links exibidos.

**P: Posso usar o Mapa de Atividades se não tiver usado o ClickMap do Visitante anteriormente em meu site?**

A: Ter a versão herdada - agora chamada simplesmente de ClickMap - instalada não é um pré-requisito para implementar a nova versão. A Adobe continuará a oferecer suporte à versão herdada por um período limitado.

**P: Quais navegadores e versões são compatíveis com o Mapa de Atividades?**

A: Oferecemos suporte à versão mais recente dos quatro navegadores principais (Chrome, Firefox, Safari e IE).

**P: Quais são as Configurações de sobreposição padrão?**

A: Por padrão, o Mapa de Atividade mostra TODOS os links que coletaram dados.

Quando os painéis pop-up são exibidos na parte superior das páginas da Web do cliente, as sobreposições pertencentes aos links localizados abaixo do painel pop-up podem ser exibidas na parte superior do painel pop-up.

**P: Por que algumas sobreposições de itens classificados estão ausentes?**

A: Alguns links classificados podem estar ocultos da página (links de submenu, por exemplo). Como consequência, as sobreposições de link correspondentes não serão exibidas. Portanto, você pode esperar classificações de sobreposição que não têm alguns valores de classificação específicos, pois a classificação é calculada para todos os links na página (o atual + os ocultos).

**P: Como a classificação de links é determinada no relatório Todos os links?**

* No modo **Gradiente** e em **Bolha**: a classificação é determinada pela coluna de métricas. Para links com o mesmo valor métrico, a classificação é ainda baseada na ordem alfabética da ID do link.
* No modo **Ganhador e perdedor** , a classificação é determinada principalmente pela coluna % Ganho. Para links com o mesmo Ganho, a classificação é ainda baseada na ordem alfabética da ID do link.

**P: Por que os dados de cliques em links não são coletados quando o Mapa de Atividades está em execução?**

A: Enquanto o Mapa de Atividades estiver em uso, os dados de cliques em links não serão coletados pela tag do Analytics. Esse comportamento segue o comportamento do plug-in ClickMap.

**P: Como o Relatório de todos os links do Mapa de Atividades se compara ao relatórios do Mapa de Atividades do Relatórios e análises?**

R: Para usar o Relatório de todos os links no Activity Map, criamos uma solicitação de detalhamento, como a seguinte: página do Activity Map = “visitedpage”, detalhado pelo Link e Região do Activity Map em `<list of link&regions present in the page at rendering time>`.

Para obter um relatório equivalente no Relatórios e análises, é necessário primeiro navegar até o relatório de Página do mapa de Atividade. Lá, você filtraria o nome da página visitada no Mapa de Atividades. O nome da página visitada é mostrado na coluna esquerda no painel inferior Detalhes da página do mapa de Atividade. Depois que a página for encontrada, você poderá fazer o detalhamento dessa página e escolher Links e regiões do mapa de Atividade como uma dimensão secundária.

No entanto, é importante observar que o relatório obtido em P&amp;R lista todos os Links e regiões coletados para essa página. Mas o Mapa de Atividades somente informa sobre Links e Regiões que estão presentes na página da Web. Então, se você tem um site de notícias, ele só mostrará os dados da notícia presentes neste momento, e não as notícias que estavam presentes no começo do dia.

**P: Como o Mapa de Atividades funciona com páginas que contêm várias tags que listam vários conjuntos de relatórios?**

A: Por padrão, o Mapa de Atividades usa o conjunto de relatórios associado à primeira tag enviada pela página. É possível selecionar um conjunto de relatórios com tags diferentes na guia Configurações do Activity Map > Outros.

**P: Por quanto tempo o Mapa de Atividades verifica a tag do Analytics?**

A: Verificamos a tag do Analytics por até 20 segundos após o evento de conclusão da página.

**P: Como o Mapa de Atividades lida com o conteúdo dinâmico?**

A: O Mapa de Atividades verifica a cada 2 segundos para ver se encontrou alterações no estado da página da Web, como:

* Conteúdo HTML que se tornou visível
* Conteúdo HTML oculto
* Novo conteúdo HTML que foi inserido

Se o conteúdo estiver oculto ou exibido, o aplicativo altera automaticamente o estado dos links afetados (e, portanto, as sobreposições) de oculto para exibido ou de exibido para oculto.

Se o novo conteúdo for inserido, o aplicativo recuperará os links associados, coletará dados de análise e adicionará sobreposições para esses links.

**P: Em que métrica o relatório de Fluxo de página se baseia?**

R: Todos os dados mostrados são baseados nas exibições de página.

**P: Você pode explicar o comportamento do Mapa de Atividade com vários tipos de páginas?**

*Página da Web sem tag do Analytics*

Uma mensagem de aviso é mostrada abaixo da barra de ferramentas, indicando que nenhuma tag está presente.

*Página da Web com a tag do Analytics incompatível (AppMeasurement v1.5 ou anterior)*

Uma mensagem de aviso é exibida indicando que é necessário atualizar o código da página para v1.6 ou mais.

*Página da Web com a tag do Analytics compatível (AppMeasurement v1.6 ou posterior), mas o relatório do Activity Map não foi ativado nas Ferramentas administrativas*

Uma mensagem de aviso é mostrada, indicando a necessidade de solicitar ao administrador a \[Ativação do relatório do Activity Map\](/home/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md&quot;).

**P: Posso exportar dados do Activity Map (contextData) por meio do [Feed de dados do Analytics](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/data-feed-overview.html)?**

R: Não.

## Segmentação no Activity Map

**P: Os segmentos estão vinculados aos segmentos de usuários individuais? Os segmentos compartilhados estão disponíveis no Mapa de Atividades?**

A: O Mapa de Atividades herda seus segmentos de relatórios do Analytics.

**P: Os segmentos funcionam no modo Online?**

A: Não, os segmentos não funcionam no modo Online. A funcionalidade é equivalente à do relatórios em tempo real no Relatórios e análises.

## Conjuntos de relatórios virtuais

**P: O Mapa de Atividades é compatível com conjuntos de relatórios virtuais?**

R: Sim. No entanto, devido às limitações do conjunto de relatórios virtual, o modo Online do Mapa de Atividade não é compatível com os conjuntos de relatórios virtuais.
