---
description: Perguntas frequentes sobre a configuração, configuração e utilização de recursos no [!DNL Activity Map].
seo-description: Perguntas frequentes sobre a configuração, configuração e utilização de recursos no [!DNL Activity Map].
seo-title: Perguntas frequentes sobre o [!DNL Activity Map]
solution: Analytics
title: Perguntas frequentes sobre o [!DNL Activity Map]
topic: Activity Map
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# [!DNL Activity Map] Perguntas frequentes

Perguntas frequentes sobre a instalação, configuração e utilização dos recursos no [!DNL Activity Map].

## Implementação e AppMeasurement {#section_FB46DD652E854C07AD339D7DD5CBCEC6}

**P: Quais são as etapas de implementação para habilitar o novo[!DNL Activity Map]?**

A: Revise [Ativar [!DNL Activity Map]](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)

**P: Todos os clientes do Analytics têm acesso à página de Ativação das Ferramentas administrativas no Activity Map?**

A: Adobe SiteCatalyst customers do not have access to the Admin Console's [!DNL Activity Map] Enablement page. Apenas as empresas com contratos do Adobe Analytics Standard e Adobe Analytics Premium têm acesso a essa página de configuração.

**P: O novo código AppMeasurement pode ser configurado por meio do Dynamic Tag Management (DTM)?**

R: Sim, é possível [implementar manualmente](https://marketing.adobe.com/resources/help/en_US/dtm/analytics_dtm.html) o novo código AppMeasurement.

**P: Quais são as grandes mudanças na biblioteca do AppMeasurement v1.6?**

A: The only change in AppMeasurement v1.6 is in the [!DNL Activity Map] link tracking process methodology that requires the collection of Page name, Link ID and RegionID.

**P: O AppMeasurement será implementado no nível de domínio, em vez de em páginas específicas?**

R: O AppMeasurement é implementado no nível de conjunto de relatórios. O nível de conjunto de relatórios é normalmente associado a um nível de domínio, mas isso difere com cada implementação.

**[!DNL Activity Map]P: O DTM carrega automaticamente uma versão mais antiga (1.3.4) da API do visitante, em vez da versão desejada pelo  (1.5.1). Isso é um problema?**

R: Não. [!DNL Activity Map] não depende da VisitorAPI.

## [!DNL Activity Map] aplicação {#section_E4F2DAC09EBA4E3BA7BACB49A0A89F8D}

**[!DNL Activity Map]P: Posso usar o se não tiver usado anteriormente o ClickMap do visitante no meu site?**

R: Ter a versão herdada, agora chamada simplesmente de ClickMap, instalada não é um pré-requisito para a implementação da nova versão. A Adobe vai continuar a oferecer suporte para a versão herdada por um período limitado.

**P: Quais navegadores e versões são compatíveis com o[!DNL Activity Map]?**

P: Oferecemos suporte somente para a versão mais recente dos quatro navegadores principais (Chrome, Firefox, Safari e IE).

**P: Quais são as Configurações de sobreposição padrão?**

A: By default, [!DNL Activity Map] shows ALL links that have collected data.

Quando os painéis pop-up são mostrados na parte superior das páginas da Web do cliente, as sobreposições pertencentes aos links, localizados abaixo desse painel, também podem ser exibidas na parte superior.

**P: Por que algumas sobreposições de itens classificados estão ausentes?**

R: Alguns links classificados podem estar ocultos na página (links de submenu, por exemplo). Como consequência, as sobreposições do link correspondente não serão exibidas. Assim, é possível esperar classificações de sobreposição com alguns valores de classificação específicos ocultos, pois a classificação é calculada para todos os links na página (o atual + os ocultos).

**P: Como a classificação de links é determinada no Relatório de todos os links?**

* No modo **Gradiente** e em **Bolha**: a classificação é determinada pela coluna de métricas.  Para os links com o mesmo valor métrico, a classificação é ainda baseada na ordem alfabética da ID do link.
* No modo **Ganhador e perdedor**, a classificação é determinada principalmente pela coluna de porcentagem de Ganho. Para os links com o mesmo Ganho, a classificação é ainda baseada na ordem alfabética da ID do link.

**[!DNL Activity Map]P: Por que os dados de cliques em links não são coletados quando o está em execução?**

A: While [!DNL Activity Map] is in use, link click data is not collected by the Analytics tag. Esse comportamento segue o comportamento do plug-in ClickMap.

**P: Por que o menu suspenso de métrica lista as mesmas métricas várias vezes?**

A: [!DNL Activity Map] lists metrics for all report suites. Como resultado, é possível que ocorra uma duplicação se a empresa não tiver passado por um processo de [consolidação de métrica](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/cm_transition.html).

A lista suspensa de Métricas permite que você limite a lista de métricas calculadas para as métricas atribuídas ao conjunto de relatórios da página visitada.

**P: Como o Relatório de todos os links[!DNL Activity Map]se compara aos relatórios do Relatórios e análises[!DNL Activity Map]?**

A: Para obter o Relatório de todos os links, [!DNL Activity Map]criamos uma solicitação de detalhamento da seguinte maneira: [!DNL Activity Map] Página = "visitedpage", detalhada por [!DNL Activity Map] Link&amp;Region em `<list of link&regions present in the page at rendering time>`.

To get an equivalent report in Reports &amp; Analytics, you would need to first navigate to the [!DNL Activity Map] Page report. Lá, é possível filtrar pelo nome da página visitada no [!DNL Activity Map]. The visited Pagename is shown in the left column in the [!DNL Activity Map] Page Details Bottom Panel. Once the page has been found, you can break down from that page and choose [!DNL Activity Map] Links &amp; Regions as a secondary dimension.

No entanto, é importante observar que o relatório obtido em Relatórios e análises vai listar todos os links e regiões que foram coletados nessa página. But [!DNL Activity Map] only reports on Links&amp;Regions that are currently present in the webpage. Por isso, se você tiver um site de notícias, ele só mostrará os dados da notícia presentes neste momento, e não as notícias que estavam presentes no início do dia.

**[!DNL Activity Map]P: Como o funciona com as páginas que contêm várias tags, listando vários conjuntos de relatórios?**

A: By default, [!DNL Activity Map] uses the report suite that is associated with the first tag that is sent by the page.

É possível selecionar um conjunto de relatórios com tags diferentes na guia [!DNL Activity Map]Configurações do  &gt;  &gt; Outros.

**[!DNL Activity Map]P: Por quanto tempo o verifica a tag do Analytics?**

R: Verificamos a tag do Analytics em até 20 segundos após a conclusão de um evento na página.

**P: Como[!DNL Activity Map]lidar com conteúdo dinâmico?**

A: [!DNL Activity Map] checks every 2 seconds to see if it has found changes in the state of the web page such as:

* Conteúdo HTML que se tornou visível
* Conteúdo HTML que está oculto
* Novo conteúdo HTML que foi inserido

Se o conteúdo estiver oculto ou exibido, o aplicativo altera automaticamente o estado dos links afetados (e, portanto, as sobreposições), de oculto para exibido ou vice-versa.

Se o novo conteúdo for inserido, o aplicativo vai recuperar os links associados, extrair os dados de análise e adicionar as sobreposições para esses links.

**P: Em qual métrica é baseada o Relatório de fluxo de página?**

R: Todos os dados mostrados são baseados nas exibições de página. 

**[!DNL Activity Map]P: É possível explicar o comportamento do com vários tipos de páginas?**

*Página da Web sem a tag do Analytics*

Uma mensagem de aviso é mostrada abaixo da barra de ferramentas, indicando que nenhuma tag está presente.

*Página da Web com a tag do Analytics incompatível (AppMeasurement v1.5 ou anterior)*

Uma mensagem de aviso é exibida, indicando que você precisa (/home/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md) atualizar o código da página para v1.6.

*[!DNL Activity Map]Página da Web com a tag do Analytics compatível (AppMeasurement v1.6 ou posterior), mas o relatório do não foi ativado nas Ferramentas administrativas*

Uma mensagem de aviso é exibida, indicando que você precisa solicitar ao administrador que \[Habilite o [!DNL Activity Map] relatório\](/home/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md") .

**P: É possível exportar[!DNL Activity Map]dados (contextData) por meio do Feed[de dados do](https://marketing.adobe.com/resources/help/en_US/reference/analytics-data-feed.html)Analytics?**

R: Não.

## Segmentação em [!DNL Activity Map]{#section_44D6C5F59B8542DC8A3AF38BD8078DCA}

**P: Os segmentos estão vinculados aos segmentos de usuários individuais? Or are shared Admin-level segments available in[!DNL Activity Map]?**

A: [!DNL Activity Map] inherits your Admin-level segments (reporting segments) from Analytics.

**P: Os segmentos funcionam no modo Online?**

R: Não, os segmentos não funcionam no modo Online. A funcionalidade é equivalente ao dos relatórios em tempo real nos Reports &amp; Analytics.

## Conjuntos de relatórios virtuais {#section_BDB0CA9E732F478EAC349A79753A78DB}

**P: É[!DNL Activity Map]compatível com conjuntos de relatórios virtuais?**

R: Sim. However, due to virtual report suite limitations, [!DNL Activity Map]'s Live Mode is not compatible with virtual report suites.
