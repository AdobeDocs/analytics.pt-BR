---
title: linkInternalFilters
description: Use a variável linkInternalFilters para ajudar no rastreamento automático do link de saída.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkInternalFilters

O AppMeasurement oferece a capacidade de rastrear automaticamente links que apontam para fora do site. If [`trackExternalLinks`](trackexternallinks.md) is enabled, an image request is sent to Adobe right as a visitor clicks a link to leave your site. As variáveis [`linkExternalFilters`](linkexternalfilters.md) e `linkInternalFilters` determinam quais links são considerados internos/externos.

Se essa variável contiver um valor, o rastreamento automático de link de saída se comportará de maneira semelhante à lista de não permissão. Se um clique em um link não corresponder a algum valor `linkInternalFilters`, ele será considerado um link de saída. O URL inteiro é examinado em relação a essa variável. If [`linkLeaveQueryString`](linkleavequerystring.md) is enabled, the query string is also examined.

Se você usar `linkInternalFilters` e `linkExternalFilters` simultaneamente, o link clicado deverá corresponder a `linkExternalFilters` **e** não corresponder a `linkInternalFilters` para ser considerado um link de saída. Se um link clicado corresponder aos critérios do link de saída e do link de download, o tipo de link de download terá prioridade.

>[!NOTE] Os filtros de URL interno `linkInternalFilters`[](/help/admin/admin/internal-url-filter-admin.md) e são recursos separados que atendem a diferentes objetivos. A variável `linkInternalFilters` funciona especificamente para o rastreamento de link de saída. Os filtros de URL internos são uma configuração de administrador que ajuda com dimensões de origens de tráfego, como Domínio de referência.

## Links externos - Nunca rastrear no Adobe Experience Platform Launch

The Never Track field is a comma-separated list of filters (usually domains) under the [!UICONTROL Link Tracking] accordion when configuring the Adobe Analytics extension.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Amplie o [!UICONTROL Link Tracking] acordeão, que revela o [!UICONTROL Outbound Links - Never Track] campo.

Coloque os filtros que deseja que nunca sejam rastreados como links de saída neste campo. Separe vários domínios por vírgula sem espaço.

## s.linkInternalFilters no AppMeasurement e no editor de código personalizado do Launch

A variável `s.linkInternalFilters` é uma cadeia de caracteres que contém filtros (como domínios) tidos como internos no site. Separe vários filtros usando uma vírgula sem espaços.

```js
s.linkInternalFilters = "example.com,example.net,example.org";
```

Considere o exemplo de implementação a seguir como se ele estivesse em `adobe.com`:

```html
<script>
  s.trackExternalLinks = true;
  s.linkInternalFilters = "adobe.com";
</script>

<!-- The following link is an exit link because it does not match the anything under linkInternalFilters -->
<a href = "example.com">Example link 2</a>
```
