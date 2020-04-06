---
title: linkExternalFilters
description: Use a variável linkExternalFilters para ajudar no rastreamento automático do link de saída.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkExternalFilters

O AppMeasurement oferece a capacidade de rastrear automaticamente links que apontam para fora do site. If [`trackExternalLinks`](trackexternallinks.md) is enabled, an image request is sent to Adobe right as a visitor clicks a link to leave your site. As variáveis `linkExternalFilters` e [`linkInternalFilters`](linkinternalfilters.md) determinam quais links são considerados internos/externos.

Se essa variável contiver um valor, o rastreamento automático de link de saída se comportará de maneira semelhante à lista de permissões. Se um clique em um link não corresponder a algum valor `linkExternalFilters`, ele não será considerado um link de saída. O URL inteiro é examinado em relação a essa variável. If [`linkLeaveQueryString`](linkleavequerystring.md) is enabled, the query string is also examined.

>[!TIP] Use essa variável somente se você souber exatamente quais domínios deseja considerar como links de saída. Muitas organizações acham que usar o `linkInternalFilters` é suficiente para as necessidades de rastreamento de link de saída, e não usam `linkExternalFilters`.

Se você usar `linkInternalFilters` e `linkExternalFilters` simultaneamente, o link clicado deverá corresponder a `linkExternalFilters` **e** não corresponder a `linkInternalFilters` para ser considerado um link de saída. Se um link clicado corresponder aos critérios do link de saída e do link de download, o tipo de link de download terá prioridade.

## Links externos - Rastrear no Adobe Experience Platform Launch

The Track field is a comma-separated list of filters (usually domains) under the [!UICONTROL Link Tracking] accordion when configuring the Adobe Analytics extension.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Amplie o [!UICONTROL Link Tracking] acordeão, que revela o [!UICONTROL Outbound Links - Track] campo.

Coloque filtros que deseja sempre considerar como externos neste campo. Separe vários domínios por vírgula sem espaço.

## s.linkExternalFilters no AppMeasurement e no editor de código personalizado do Launch

A variável `s.linkExternalFilters` é uma cadeia de caracteres que contém filtros (como domínios) tidos como links de saída. Separe vários domínios usando uma vírgula sem espaços.

```js
s.linkExternalFilters = "example.com,example.net,example.org";
```

Considere o exemplo de implementação a seguir como se ele estivesse em `adobe.com`:

```html
<script>
  s.trackExternalLinks = true;
  s.linkExternalFilters = "example.com,example.net";
</script>

<!-- The following link is NOT considered an exit link, even though the link is outside adobe.com -->
<a href = "example.org">Example link 1</a>

<!-- The following link is an exit link because it matches the linkExternalFilters whitelist -->
<a href = "example.com">Example link 2</a>
```
