---
description: Perguntas frequentes sobre a instalação, configuração e utilização dos recursos no Activity Map.
seo-description: Perguntas frequentes sobre a instalação, configuração e utilização dos recursos no Mapa de atividade.
seo-title: Perguntas frequentes sobre o Mapa de atividade
solution: Analytics
title: Perguntas frequentes sobre o Activity Map
topic: Activity Map
uuid: e 4 f 6 d 4 e 2-55 d 1-4 e 32-bf 70-a 334178 af 370
translation-type: tm+mt
source-git-commit: 8f72f8cf086be0eade5616b074123a9f22e33347

---


# Perguntas frequentes sobre o Activity Map

Perguntas frequentes sobre a instalação, configuração e utilização dos recursos no Activity Map.

## Implementação e AppMeasurement {#section_FB46DD652E854C07AD339D7DD5CBCEC6}

**P: Quais são as etapas de implementação para habilitar o novo Activity Map?**

A: Please review [Enable Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)

**P: Todos os clientes do Analytics têm acesso à página de Ativação das Ferramentas administrativas no Activity Map?**

R: Os clientes do Adobe SiteCatalyst não têm acesso à página de Ativação do Admin Console no Activity Map. Apenas as empresas com contratos do Adobe Analytics Standard e Adobe Analytics Premium têm acesso a essa página de configuração.

**P: O novo código AppMeasurement pode ser configurado por meio do Dynamic Tag Management (DTM)?**

R: Sim, é possível [implementar manualmente](https://marketing.adobe.com/resources/help/en_US/dtm/analytics_dtm.html) o novo código AppMeasurement.

**P: Quais são as grandes mudanças na biblioteca do AppMeasurement v1.6?**

R: A única alteração no AppMeasurement v1.6 está na metodologia do processo de rastreamento de links no Activity Map, que exige a coleta de Nome da página, ID do link e ID da região.

**P: O AppMeasurement será implementado no nível de domínio, em vez de em páginas específicas?**

R: O AppMeasurement é implementado no nível de conjunto de relatórios. O nível de conjunto de relatórios é normalmente associado a um nível de domínio, mas isso difere com cada implementação.

**P: O DTM carrega automaticamente uma versão mais antiga (1.3.4) da API do visitante, em vez da versão desejada pelo Activity Map (1.5.1). Isso é um problema?**

R: Não. A funcionalidade do Activity Map não depende da API do visitante.

## Activity Map application {#section_E4F2DAC09EBA4E3BA7BACB49A0A89F8D}

**P: Posso usar o Activity Map se não tiver usado anteriormente o ClickMap do visitante no meu site?**

R: Ter a versão herdada, agora chamada simplesmente de ClickMap, instalada não é um pré-requisito para a implementação da nova versão. A Adobe vai continuar a oferecer suporte para a versão herdada por um período limitado.

**P: Quais navegadores e versões são compatíveis com o Activity Map?**

P: Oferecemos suporte somente para a versão mais recente dos quatro navegadores principais (Chrome, Firefox, Safari e IE).

**P: Quais são as Configurações de sobreposição padrão?**

R: Por padrão, o Activity Map mostra TODOS os links com dados coletados.

Quando os painéis pop-up são mostrados na parte superior das páginas da Web do cliente, as sobreposições pertencentes aos links, localizados abaixo desse painel, também podem ser exibidas na parte superior.

**P: Por que algumas sobreposições de itens classificados estão ausentes?**

R: Alguns links classificados podem estar ocultos na página (links de submenu, por exemplo). Como consequência, as sobreposições do link correspondente não serão exibidas. Assim, é possível esperar classificações de sobreposição com alguns valores de classificação específicos ocultos, pois a classificação é calculada para todos os links na página (o atual + os ocultos).

**P: Como a classificação de links é determinada no Relatório de todos os links?**

* No modo **Gradiente** e em **Bolha**: a classificação é determinada pela coluna de métricas.  Para os links com o mesmo valor métrico, a classificação é ainda baseada na ordem alfabética da ID do link.
* No modo **Ganhador e perdedor**, a classificação é determinada principalmente pela coluna de porcentagem de Ganho. Para os links com o mesmo Ganho, a classificação é ainda baseada na ordem alfabética da ID do link.

**P: Por que os dados de cliques em links não são coletados quando o Activity Map está em execução?**

R: Enquanto o Activity Map estiver em uso, os dados do cliques em links não são coletados pela tag do Analytics. Esse comportamento segue o comportamento do plug-in ClickMap.

**P: Por que o menu suspenso de métrica lista as mesmas métricas várias vezes?**

R: O Activity Map lista as métricas para todos os conjuntos de relatórios.  Como resultado, é possível que ocorra uma duplicação se a empresa não tiver passado por um processo de [consolidação de métrica](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/cm_transition.html).

A lista suspensa de Métricas permite que você limite a lista de métricas calculadas para as métricas atribuídas ao conjunto de relatórios da página visitada.

**P: Como o Relatório de todos os links pode ser comparado aos Reports &amp; Analytics do Activity Map?**

A: To pull the All Links Report in Activity Map, we create a breakdown request as follows: Activity Map Page = “visitedpage”, broken down by Activity Map Link&amp;Region in `<list of link&regions present in the page at rendering time>`.

Para obter um relatório equivalente em Reports &amp; Analytics, você precisa primeiro navegar até o relatório de página do Activity Map. Lá, é possível filtrar pelo nome da página visitada no Activity Map. O nome da página visitada é mostrado na coluna esquerda do painel inferior Detalhes da página, no Activity Map. Após encontrar a página, é possível separar-se dessa página e escolher Links e regiões do Activity Map como uma dimensão secundária.

No entanto, é importante observar que o relatório obtido em Relatórios e análises vai listar todos os links e regiões que foram coletados nessa página. Porém, o Activity Map apenas informa aos Links e regiões que estão presentes na página da Web. Por isso, se você tiver um site de notícias, ele só mostrará os dados da notícia presentes neste momento, e não as notícias que estavam presentes no início do dia.

**P: Como o Activity Map funciona com as páginas que contêm várias tags, listando vários conjuntos de relatórios?**

R: Por padrão, o Activity Map usa o conjunto de relatórios associado à primeira tag enviada pela página.

É possível selecionar um conjunto de relatórios com tags diferentes na guia Configurações do Activity Map &gt; Outros.

**P: Por quanto tempo o Activity Map verifica a tag do Analytics?**

R: Verificamos a tag do Analytics em até 20 segundos após a conclusão de um evento na página.

**P: Como o Activity Map lida com o conteúdo dinâmico?**

O Activity Map verifica se ocorreram alterações no estado da página da Web a cada 2 segundos, como:

* Conteúdo HTML que se tornou visível
* Conteúdo HTML que está oculto
* Novo conteúdo HTML que foi inserido

Se o conteúdo estiver oculto ou exibido, o aplicativo altera automaticamente o estado dos links afetados (e, portanto, as sobreposições), de oculto para exibido ou vice-versa.

Se o novo conteúdo for inserido, o aplicativo vai recuperar os links associados, extrair os dados de análise e adicionar as sobreposições para esses links.

**P: Em qual métrica é baseada o Relatório de fluxo de página?**

R: Todos os dados mostrados são baseados nas exibições de página. 

**P: É possível explicar o comportamento do Activity Map com vários tipos de páginas?**

*Página da Web sem a tag do Analytics*

Uma mensagem de aviso é mostrada abaixo da barra de ferramentas, indicando que nenhuma tag está presente.

*Página da Web com a tag do Analytics incompatível (AppMeasurement v1.5 ou anterior)*

Uma mensagem de aviso é mostrada indicando que você precisa (/home/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable. md) atualizar o código da página para v 1.6.

*Página da Web com a tag do Analytics compatível (AppMeasurement v1.6 ou posterior), mas o relatório do Activity Map não foi ativado nas Ferramentas administrativas*

Uma mensagem de aviso é mostrada, indicando que você precisa perguntar ao administrador\ [Ativar o relatório do Activity Map\] (/home/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable. md ").

**P: Posso exportar dados do Activity Map (contextData) por meio do[Feed de dados do Analytics](https://marketing.adobe.com/resources/help/en_US/reference/analytics-data-feed.html)?**

R: Não.

## Segmentação no Activity Map {#section_44D6C5F59B8542DC8A3AF38BD8078DCA}

**P: Os segmentos estão vinculados aos segmentos de usuários individuais? Ou são segmentos de nível de administrador compartilhados, disponíveis no Activity Map?**

A: O Activity Map herda seus segmentos de nível de administrador (segmentos de relatórios) do Analytics.

**P: Os segmentos funcionam no modo Online?**

R: Não, os segmentos não funcionam no modo Online. A funcionalidade é equivalente ao dos relatórios em tempo real nos Reports &amp; Analytics.

## Virtual report suites {#section_BDB0CA9E732F478EAC349A79753A78DB}

**P: O Activity Map é compatível com os conjuntos de relatórios virtuais?**

R: Sim. No entanto, devido às limitações do conjunto de relatórios virtuais, não há compatibilidade com o modo Online do Activity Map.
