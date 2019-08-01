---
description: 'A Adobe usa os seguintes termos ao falar sobre as métricas relacionadas à integração do DFA '
keywords: DFA
seo-description: 'A Adobe usa os seguintes termos ao falar sobre as métricas relacionadas à integração do DFA '
seo-title: Definições de Métricas
solution: Analytics
title: Definições de Métricas
topic: Conectores de dados
uuid: 062 f 6863-3 daa -4 e 8 a-b 6 ea -84279 d 49 c 388
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Definições de Métricas{#metric-definitions}

A Adobe usa os seguintes termos ao falar sobre as métricas relacionadas à integração do DFA:

**Impressões**: as impressões se referem ao número de vezes que um anúncio foi visualizado. As impressões são registradas para cada anúncio, mas também podem ser agregadas em grupos de anúncios ou outros agrupamentos de vários anúncios. A métrica de impressões no Analytics é importada do DFA por uma importação noturna de fontes de dados.

**Cliques**: os cliques se referem ao número de vezes que um anúncio foi clicado, conforme o relatório do DFA. Os cliques são registrados na página de redirecionamento do DFA antes que o visitante chegue ao site do cliente. Assim como as impressões, a métrica de cliques no Analytics é importada do DFA por uma importação noturna de fontes de dados.

**Click-throughs**: os click-throughs se referem ao número de vezes que o usuário chegou à página de aterrissagem após clicar em um anúncio. Essa métrica pode ser ligeiramente diferente dos cliques.

**View-throughs**: os view-throughs se referem ao número de vezes que um visitante acessou o site do cliente após visualizar um anúncio, mas SEM ter clicado no anúncio. O visitante deve acessar o site dentro do período de view-through, que por padrão é definido para 30 dias. A impressão deve ter ocorrido mais recentemente do que o último clique. Os view-throughs são registrados uma vez por campanha, por visita, e são contados quando a integração preenche a eVar de view-through com a ID de campanha do DFA e o evento de view-through é definido.
