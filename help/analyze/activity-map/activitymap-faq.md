---
description: Perguntas frequentes sobre a instalação, configuração e utilização dos recursos no Activity Map.
title: Perguntas frequentes sobre o Activity Map
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
feature: Activity Map
role: User, Admin
exl-id: 6b2767cb-6c2c-4bf3-b9a9-a23418624650
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 100%

---

# Perguntas frequentes sobre o Activity Map

Perguntas frequentes sobre a instalação, configuração e utilização dos recursos no Activity Map.

## Todos os clientes do Analytics têm acesso à página de Ativação das ferramentas administrativas no Activity Map?

Organizações com um contrato do Adobe Analytics Standard, Premium e Ultimate têm acesso ao Activity Map.

## Como o Activity Map oferece suporte a Aplicativos de página única (SPA)?

A cada poucos segundos, o Activity Map verifica a página da Web, procurando por alterações na página. O ActivityMap encontra novo conteúdo na página sem precisar de um novo carregamento, mas esse novo conteúdo é sempre atribuído ao primeiro pageName encontrado quando a página é carregada.

* O Activity Map verifica se a visibilidade dos links que ele conhece foi alterada. Se uma alteração na visibilidade for encontrada, a coluna Presente da tabela de Links na página para esse link será atualizada com [!UICONTROL Exibido] ou [!UICONTROL Oculto].

* Quando a interação do usuário cria novo conteúdo, qualquer novo elemento encontrado pelo AppMeasurement como um link será adicionado à tabela [!UICONTROL Links na página]. O Activity Map envia uma nova solicitação de dados que inclui esses novos links. Os novos links deverão aparecer na tabela [!UICONTROL Links na página] quando a solicitação de dados for tratada pela interface do usuário.


## O Activity Map fornece dados sobre &quot;visualizações&quot;?

Não, a Adobe não rastreia links que foram exibidos.

## Quais navegadores e versões são compatíveis com o Activity Map?

O Activity Map é compatível com a versão mais recente da maioria dos navegadores modernos.

## O Activity Map aumenta as chamadas do servidor?

O Activity Map não envia chamadas de servidor sozinho. Em vez disso, as variáveis de dados de contexto do Activity Map são incluídas com chamadas de exibição de página do Analytics na página subsequente.

## Por que algumas sobreposições de itens classificados estão ausentes?**

Alguns links classificados, como links de submenu, estão ocultos na página. Como consequência, as sobreposições do link correspondente não serão exibidas. A classificação é calculada para todos os links na página, incluindo links ocultos.

## Como a classificação de links é determinada no Relatório de todos os links?**

* **No modo gradiente e bolha**: a classificação é determinada pela coluna de métricas. Para os links com o mesmo valor métrico, a classificação é ainda baseada na ordem alfabética da ID do link.
* **No modo ganhador e perdedor**: a classificação é determinada principalmente pela coluna % de ganho. Para os links com o mesmo ganho, a classificação ainda é baseada na ordem alfabética da ID do link.

## Como o Activity Map funciona com páginas que usam vários conjuntos de relatórios?

Por padrão, o Activity Map usa o conjunto de relatórios associado à primeira tag enviada pela página. É possível selecionar um conjunto de relatórios com tags diferentes na guia **[!UICONTROL Configurações do Activity Map]** > **[!UICONTROL Outros]**.

## Por quanto tempo o Activity Map verifica o Adobe Analytics na página?

O Activity Map verifica a presença do Adobe Analytics por até 20 segundos após um evento de conclusão de página.

## Como o Activity Map lida com o conteúdo dinâmico?

O Activity Map verifica se ocorreram alterações no estado da página da Web a cada dois segundos, como:

* Conteúdo HTML que se tornou visível
* Conteúdo HTML que está oculto
* Novo conteúdo HTML que foi inserido

Se o conteúdo estiver oculto ou exibido, o aplicativo altera automaticamente o estado dos links afetados (e, portanto, as sobreposições), de oculto para exibido ou vice-versa. Se novo conteúdo for inserido, o aplicativo recuperará os links associados, extrairá os dados de análise e adicionará sobreposições para esses links.

## Em qual métrica se baseia o Relatório de fluxo de página?

Todos os dados mostrados se baseiam nas exibições de página.

## Posso exportar variáveis de dados de contexto do Activity Map por meio de feeds de dados?

As variáveis de dados de contexto do Activity Map não estão disponíveis em feeds de dados.

## Os segmentos funcionam no modo Online?

Não, os segmentos não funcionam no modo Online. A funcionalidade é equivalente à dos relatórios em tempo real no Reports &amp; Analytics, que não oferecem suporte à segmentação.

## O Activity Map é compatível com os conjuntos de relatórios virtuais?

Sim. No entanto, devido às limitações do conjunto de relatórios virtuais, não há compatibilidade com o modo Online do Activity Map.
