---
title: Página
description: O nome da página.
feature: Dimensions
exl-id: 579963c8-8460-425f-b716-3b30d7a259af
TQID: https://experienceleague.adobe.com/npKfFB-zOPzNGJJ6YZvtz0oA3NDWuQiHYBraH09lc58
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 188
ht-degree: 80%

---

# Página

A [dimensão](overview.md) de &quot;Página&quot; lista os nomes das páginas do site. É uma das dimensões mais comuns usadas no Adobe Analytics, pois fornece informações sobre quais páginas do site têm melhor desempenho.

Essa dimensão está relacionada à [Seção do site](site-section.md) e às dimensões de [Servidor](server.md). A dimensão Página é mais granular, a dimensão Servidor é menos granular e a dimensão Seção do site fica entre as duas.

## Preencher esta dimensão com dados

Essa dimensão recupera dados da [`pageName`sequência de consulta](/help/implement/validate/query-parameters.md) em [Chamadas de exibição de página (`t()`)](/help/implement/vars/functions/t-method.md). [As chamadas de rastreamento de link (`tl()`)](/help/implement/vars/functions/tl-method.md) sempre removem essa dimensão, mesmo se a sequência de consulta `pageName` existir.

O AppMeasurement coleta esses dados usando a variável [`pageName`](/help/implement/vars/page-vars/pagename.md). Se a variável `pageName` não estiver definida, essa dimensão voltará a usar a variável [`pageURL`](/help/implement/vars/page-vars/pageurl.md).

## Itens de dimensão

Os itens de dimensão incluem os nome de páginas no site. Sua organização determina quais itens de dimensão específicos deseja usar. Algumas organizações usam diretamente `document.title`, enquanto outras formulam uma navegação estrutural personalizada. Independentemente do método usado, verifique se ele é consistente e registre-o em um [documento de design de solução](/help/implement/prepare/solution-design.md).

>[!NOTE]
>
>O Analysis Workspace usa a última atribuição por padrão, com a opção de usar qualquer modelo de atribuição.
