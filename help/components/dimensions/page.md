---
title: Página
description: O nome da página.
feature: Dimensions
exl-id: 579963c8-8460-425f-b716-3b30d7a259af
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 94%

---

# Página

A &#39;Página&#39; [dimension](overview.md) lista os nomes das páginas do site. É uma das dimensões mais comuns usadas no Adobe Analytics, pois fornece informações sobre quais páginas do site têm melhor desempenho.

Essa dimensão está relacionada à [Seção do site](site-section.md) e às dimensões de [Servidor](server.md). A dimensão Página é mais granular, a dimensão Servidor é menos granular e a dimensão Seção do site fica entre as duas.

## Preencher esta dimensão com dados

Essa dimensão recupera dados da [`pageName`sequência de consulta](/help/implement/validate/query-parameters.md) em [Chamadas de exibição de página (`t()`)](/help/implement/vars/functions/t-method.md). [As chamadas de rastreamento de link (`tl()`)](/help/implement/vars/functions/tl-method.md) sempre removem essa dimensão, mesmo se a sequência de consulta `pageName` existir.

O AppMeasurement coleta esses dados usando a variável [`pageName`](/help/implement/vars/page-vars/pagename.md). Se a variável `pageName` não estiver definida, ela voltará a usar a variável [`pageURL`](/help/implement/vars/page-vars/pageurl.md).

## Itens de dimensão

Os itens de dimensão incluem os nome de páginas no site. A organização escolhe quais itens de dimensão específicos quer utilizar. Algumas organizações usam diretamente `document.title`, enquanto outras formulam uma navegação estrutural personalizada. Independentemente do método usado, verifique se ele é consistente e registre-o em um [documento de design de solução](/help/implement/prepare/solution-design.md).

>[!NOTE]
>
>O Analysis Workspace usa a última atribuição por padrão, com a opção de usar qualquer modelo de atribuição.
