---
description: 'null'
keywords: DFA
seo-description: 'null'
seo-title: Atualizar seu parâmetro de sequência de consulta do DFA
solution: Analytics
title: Atualizar seu parâmetro de sequência de consulta do DFA
topic: Conectores de dados
uuid: adf 585 ac -84 ff -44 c 1-a 48 d-b 072726 c 8494
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Atualize seu parâmetro de sequência de consulta do DFA{#update-your-dfa-query-string-parameter}

Se você já esteve monitorando campanhas de anúncios com o Adobe Analytics antes da integração do DFA, é possível que todas as campanhas (email, pesquisa ou banner) usem o mesmo parâmetro de sequência de consulta para identificar a ID da campanha de referência na página de aterrissagem.

Para entender quando solicitar dados de view-through e de click-through dos dados do DFA para suas campanhas de anúncios do DFA, os Conectores de dados precisam identificar quando um visitante clicou em um anúncio de banner de campanha do DFA. Para tornar isso possível, adicione um parâmetro de sequência de consulta diferenciado ao URL da página de aterrissagem da campanha do anúncio do DFA para que os Conectores de dados possam distinguir entre as páginas de campanha de anúncios do DFA e outras páginas de campanhas de anúncios que possam existir em seu site. O `dfa_overrideParam` plug-in do javascript (consulte [Atualizar o código de coleta de dados de seu site](../../../dfa-data-connector-analytics/dfa-integration/dfa-web-site-updates/dfa-update-data-collection-code.md#concept-8c108723ea0b4cc9a8c5cdc2d05894e3)) usado para o DFA.

>[!CAUTION]
>
>Embora a variável Campanha possa ser usada para outras campanhas, não a use para campanhas do DFA. Se você definir a variável de campanha para a página de aterrissagem de uma campanha do DFA, a Adobe não poderá associar impressões e cliques a click-throughs de campanha do DFA. Uma vez a cada visita, os servidores de coleta da Adobe verificam nos servidores do DFA se há um click-through ou view-through anterior. Por esse motivo, inclua o código de plug-in do DFA (consulte [Atualizar o código de coleta de dados de seu site](../../../dfa-data-connector-analytics/dfa-integration/dfa-web-site-updates/dfa-update-data-collection-code.md#concept-8c108723ea0b4cc9a8c5cdc2d05894e3)) somente em páginas de aterrissagem comuns a fim de evitar redirecionamentos desnecessários que possam retardar os tempos de carregamento de página, especialmente para usuários com conexões de Internet mais lentas.

