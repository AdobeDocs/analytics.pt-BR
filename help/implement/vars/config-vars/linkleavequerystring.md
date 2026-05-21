---
title: linkLeaveQueryString
description: Permite a preservação de cadeias de caracteres de consulta em dimensões de rastreamento de link.
feature: Appmeasurement Implementation
exl-id: 266f7d9c-803d-4dbe-95a1-282230012878
role: Admin, Developer
TQID: https://experienceleague.adobe.com/ebg-JRfYQ4VBpZChrgHN4IF5PBGCVriVWWQ7qN3a5pM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 331
ht-degree: 84%

---

# linkLeaveQueryString

Por padrão, o AppMeasurement remove as cadeias de caracteres de consulta dos URLs de rastreamento de link. Use a variável `linkLeaveQueryString` para manter as sequências de consulta nas dimensões de rastreamento de link.

Em alguns links de saída e de downloads, a parte importante do URL pode estar na cadeia de caracteres de consulta. Por exemplo, um link de download como `https://example.com/download.asp?filename=myfile.exe` contém informações importantes do link na cadeia de caracteres de consulta.

Se as informações de rastreamento de link não estiverem nos URLs do site, não será necessário usar essa variável. A remoção de cadeias de caracteres de consulta de URLs de rastreamento de link ajuda a limitar o número de valores únicos contidos na dimensão.

A habilitação de `linkLeaveQueryString` se aplica a todas as dimensões de rastreamento de link (incluindo links personalizados, links de saída e links de download).

>[!TIP]
>
>Essa variável não afeta dimensões fora do rastreamento de link. Ela afeta apenas links personalizados, links de saída e links de download.

## Lidar com cadeias de caracteres de consulta de link usando o Web SDK

As cadeias de consulta não são removidas do campo XDM `web.webInteraction.URL`. Se quiser remover cadeias de caracteres de consulta deste campo XDM, você poderá editá-lo usando `onBeforeEventSend`.

## Manter parâmetros de URL usando a extensão do Adobe Analytics

[!UICONTROL Manter parâmetros de URL] é uma caixa de seleção na opção [!UICONTROL Rastreamento de link] ao configurar a extensão Adobe Analytics.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]**, no Adobe Analytics.
4. Expanda a opção [!UICONTROL Rastreamento de link], que revela a caixa de seleção [!UICONTROL Manter parâmetros de URL].

Marque essa caixa se desejar incluir cadeias de caracteres de consulta nas dimensões de rastreamento de link.

## s.linkLeaveQueryString no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.linkLeaveQueryString` é booleana. O valor padrão é `false`.

* Se essa variável estiver definida como `true`, as cadeias de caracteres de consulta serão mantidas nos URLs de rastreamento de link.
* Se essa variável for definida como `false` ou não estiver definida, as cadeias de caracteres de consulta serão removidas dos URLs de rastreamento de link.

```js
s.linkLeaveQueryString = true;
```

## Exemplo

Tenha cuidado ao definir essa variável como true, pois ela pode afetar os filtros de rastreamento de link como [`linkInternalFilters`](linkinternalfilters.md), [`linkExternalFilters`](linkexternalfilters.md) e [`linkDownloadFiletypes`](linkdownloadfiletypes.md).

Considere o exemplo a seguir como se ele estivesse em `adobe.com`:

```html
<script>
  s.linkInternalFilters = "adobe.com";
  s.linkLeaveQueryString = true;
</script>

<!--This link is not an exit link because the internal filter matches part of the query string -->
<a href = "example.com?r=adobe.com">Example link</a>
```
