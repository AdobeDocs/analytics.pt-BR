---
description: Perguntas frequentes sobre a instalação, configuração e utilização dos recursos no Activity Map.
title: Perguntas frequentes sobre o Activity Map
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
feature: Activity Map
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 26%

---


# Perguntas frequentes sobre o Activity Map

Perguntas frequentes sobre a instalação, configuração e utilização dos recursos no Activity Map.

## Todos os clientes do Analytics têm acesso à página de Ativação das Ferramentas administrativas no Activity Map?

Organizações com um contrato para o Adobe Analytics Standard, Premium e Ultimate têm acesso ao Activity Map.

## O Activity Map fornece dados sobre &quot;visualizações&quot;?

Não, a Adobe não rastreia links que foram exibidos.

## Quais navegadores e versões o Activity Map suporta?

O Activity Map suporta a versão mais recente da maioria dos navegadores modernos.

## O Activity Map aumenta as chamadas do servidor?

O Activity Map não envia chamadas de servidor por si só. Em vez disso, as variáveis de dados de contexto do Activity Map são incluídas com chamadas de exibição de página do Analytics na página subsequente.

## Por que algumas sobreposições de item classificado estão ausentes?**

Alguns links classificados, como links de submenu, estão ocultos na página. Como consequência, as sobreposições de link correspondentes não são exibidas. A classificação é calculada para todos os links na página, incluindo links ocultos.

## Como a classificação de links é determinada no relatório Todos os links?**

* **No modo** Gradiente e Bolha : A classificação é determinada pela coluna de métrica. Para os links com o mesmo valor métrico, a classificação é ainda baseada na ordem alfabética da ID do link.
* **No modo** Ganhador e perdedor: A classificação é determinada principalmente pela coluna % Ganho. Para links com o mesmo ganho, a classificação é ainda baseada na ordem alfabética da ID do link.

## Como o Activity Map funciona com páginas que usam vários conjuntos de relatórios?

Por padrão, o Activity Map usa o conjunto de relatórios associado à primeira tag enviada pela página. É possível selecionar um conjunto de relatórios com tags diferentes na guia **[!UICONTROL Configurações do Activity Map]** > **[!UICONTROL Outros]**.

## Por quanto tempo o Activity Map verifica o Adobe Analytics na página?

O Activity Map verifica a presença do Adobe Analytics por até 20 segundos após a conclusão de um evento de página.

## Como o Activity Map trata o conteúdo dinâmico?

O Activity Map verifica a cada 2 segundos para ver se encontrou alterações no estado da página da Web, como:

* Conteúdo HTML que se tornou visível
* Conteúdo HTML que está oculto
* Novo conteúdo HTML que foi inserido

Se o conteúdo estiver oculto ou exibido, o aplicativo altera automaticamente o estado dos links afetados (e, portanto, as sobreposições), de oculto para exibido ou vice-versa. Se o novo conteúdo for inserido, o aplicativo recuperará os links associados, extrairá dados de análise e adicionará sobreposições para esses links.

## Em qual métrica é baseada o Relatório de fluxo de página?

Todos os dados mostrados são baseados nas exibições de página.

## Posso exportar variáveis de dados de contexto do Activity Map por meio de feeds de dados?

As variáveis de dados de contexto do Activity Map não estão disponíveis nos feeds de dados.

## Os segmentos funcionam no modo Online?

Não, os segmentos não funcionam no modo Online. A funcionalidade é equivalente à dos relatórios em tempo real no Reports &amp; Analytics, que não oferecem suporte à segmentação.

## O Activity Map é compatível com os conjuntos de relatórios virtuais?

Sim. No entanto, devido às limitações do conjunto de relatórios virtuais, não há compatibilidade com o modo Online do Activity Map.
