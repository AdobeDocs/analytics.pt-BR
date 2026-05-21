---
title: pageName
description: O nome da página do seu site.
feature: Appmeasurement Implementation
exl-id: 24ac40a9-f0e7-4534-abf2-2397f5fe16c2
role: Admin, Developer
TQID: https://experienceleague.adobe.com/8afiyqnZrImK-YJ-GvQGu0H4fzhcJrMh20QN2WbO0T0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 262
ht-degree: 86%

---

# pageName

A variável `pageName` geralmente armazena o nome de uma determinada página. É útil para determinar quais páginas individuais são mais populares. Essa variável preenche a dimensão [Página](/help/components/dimensions/page.md).

Se essa variável não for definida em uma chamada de rastreamento de página específica, a variável [`pageURL`](pageurl.md) será usada.

>[!NOTE]
>
>Os servidores de coleção de dados da Adobe removem essa dimensão de todas as solicitações de imagem de [rastreamento de link](/help/implement/vars/functions/tl-method.md). Se quiser que essa dimensão apareça nas ocorrências de rastreamento de link, considere copiar a dimensão em uma [eVar](evar.md).

## Nome da página usando o Web SDK

O nome da página é mapeado para as seguintes variáveis:

* [objeto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.web.webPageDetails.name`
* [Objeto de dados](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.pageName`

## Nome da página usando a extensão do Adobe Analytics

Você pode definir o nome da página ao configurar a extensão do Analytics (variáveis globais) ou em Regras.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone “+”.
5. Defina a lista suspensa [!UICONTROL Extensão] como Adobe Analytics e o [!UICONTROL Tipo de ação] como [!UICONTROL Definir variáveis].
6. Localize a seção [!UICONTROL Nome da página].

É possível definir o nome da página como qualquer valor de string, incluindo elementos de dados.

## s.pageName no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.pageName` é uma string que geralmente contém o nome da página. A variável tem um valor máximo de 100 bytes; valores mais longos são truncados. Esse truncamento inclui instâncias nas quais é utilizada a `pageURL` se a variável estiver em branco.

```js
// Set page name to a static value
s.pageName = "Example page name";

// Set page name to the page's title
s.pageName = window.document.title;
```

Se estiver usando a `digitalData` [camada de dados](../../prepare/data-layer.md):

```js
s.pageName = digitalData.page.pageInfo.pageName;
```
