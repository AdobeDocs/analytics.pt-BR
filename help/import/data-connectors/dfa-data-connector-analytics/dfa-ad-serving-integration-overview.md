---
description: 'Essa integração captura dados de diversas maneiras sobre o visitante direcionado por anúncios. A primeira maneira é pelo clique em um anúncio que resulta na chegada a uma página de aterrissagem marcada, chamado de click-through '
keywords: DFA
seo-description: 'Essa integração captura dados de diversas maneiras sobre o visitante direcionado por anúncios. A primeira maneira é pelo clique em um anúncio que resulta na chegada a uma página de aterrissagem marcada, chamado de click-through '
seo-title: Visão geral da integração de veiculação de anúncios
solution: Analytics
title: Visão geral da integração de veiculação de anúncios
topic: Conectores de dados
uuid: e 286 f 61 e -4 b 09-48 b 5-b 1 e 9-3 c 07 b 6 face 24
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Visão geral da integração de veiculação de anúncios{#ad-serving-integration-overview}

Essa integração captura dados de diversas maneiras sobre o visitante direcionado por anúncios. A primeira maneira é pelo clique em um anúncio que resulta na chegada a uma página de aterrissagem marcada, chamado de click-through:

![](assets/Diagram1.png)

O visitante é direcionado para o site de um editor, que hospeda o anúncio. Esse anúncio tem um identificador exclusivo, chamado ID do anúncio. Anúncios incluem um posicionamento e uma criação, que descrevem a localização do anúncio no site do editor e que conteúdo foi exibido ao visitante. Quando o visitante chega ao anúncio, posicionamento ou criação dos servidores de conteúdo do DFA, é enviada uma impressão para os servidores do DFA Floodlight sobre esse visitante (1).

Se o visitante clica no anúncio (2), o servidor Floodlight é consultado, o que conta um clique, e o 302 redireciona (3) o visitante para a página de aterrissagem. A chegada do visitante à página de aterrissagem é chamada de click-through. Essa página contém um código de acompanhamento da Adobe que consulta dados do servidor do DFA Floodlight.

Se o visitante não chega realmente à página de aterrissagem depois que o servidor Floodlight rastreia um clique, isso não é chamado de click-through. Alguns anúncios e implementações podem não fazer com que o navegador do visitante realmente obedeça ao redirecionamento 302. Para saber mais sobre esse assunto, consulte [Comparação de discrepâncias de métricas](../dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies/dfa-reconciling-metric-discrepancies.md#concept-8c31ebe761ca4b3fab1e3a18ef5d098f).

A próxima métrica capturada por essa integração ocorre quando o visitante recebe a impressão do anúncio, não clica nele, mas em algum momento no futuro chega à página de aterrissagem por outros meios.

![](assets/Viewthrough.png)

Esse cenário é chamado de view-through. A diferença entre esse cenário e o cenário de click-through é que o visitante não clica no anúncio, mas dá continuidade a outras atividades antes de chegar à página de aterrissagem (2). No caso mais simples, o visitante digita o URL da página de aterrissagem no navegador. Em outros casos, o visitante continua navegando, mas usa depois um mecanismo de pesquisa, que o leva para a página de aterrissagem. Em todo caso, o usuário chega à página de aterrissagem.
