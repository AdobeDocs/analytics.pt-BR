---
title: ActivityMap.regionIDAttribute
description: Altere o atributo que o Activity Map procura para determinar a região.
feature: Variables
role: Admin, Developer
source-git-commit: 05010d58ba2a3376473097e9d4543ee4415e83e1
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 10%

---

# ActivityMap.regionIDAttribute

A variável `ActivityMap.regionIDAttribute` permite alterar o atributo que o Activity Map procura ao determinar a dimensão [Região de Activity Map](/help/components/dimensions/activity-map-region.md). Se o site estiver estruturado de uma forma que torne o atributo `id` menos útil para a região do Activity Map, você poderá definir essa variável para observar um atributo diferente.

## Atributo de ID de região na extensão SDK da Web

Quando a **[!UICONTROL Habilitar coleta de dados de cliques]** estiver habilitada, use o bloco de código de retorno de chamada **[!UICONTROL Propriedades de cliques de filtro]**. Neste bloco de código, você pode verificar o valor de `content.clickedElement` e alterar o valor ou abandonar a coleção de dados de rastreamento de link.

## Atributo de ID de região na biblioteca JavaScript do SDK da Web

Quando [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) estiver habilitado, use o retorno de chamada `filterClickDetails` no objeto `clickCollection`. Dentro dessa chamada de retorno, você pode verificar o valor de `clickedElement` e personalizar a lógica da região coletada.

```js
alloy("configure", {
  clickCollectionEnabled: true,
  clickCollection: {
    filterClickDetails: function(content) {
      // If the clicked element was in a table, set the region to the contents of the data-custom attribute
      // If the clicked element was not in a table, or if the data-custom attribute doesn't exist, leave region as-is
      content.region = content.clickedElement.closest('table')?.getAttribute('data-custom') || content.region;
    }
  }
});
```

## Atributo de ID de região usando a extensão do Adobe Analytics

Não há um campo dedicado na extensão do Adobe Analytics para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.ActivityMap.regionIDAttribute usando o AppMeasurement

A variável `s.ActivityMap.regionIDAttribute` é uma cadeia de caracteres que representa o atributo para determinar a dimensão [Região de Activity Map](/help/components/dimensions/activity-map-region.md). Esta variável está definida como `id` por padrão. Se você alterar essa variável, o Activity Map não procurará mais pelo atributo `id`, mas ainda procurará por outros critérios para determinar a região (como elementos semânticos).

```html
<script>
  var s = s_gi("examplersid");
  s.ActivityMap.regionIDAttribute = "data-custom";
</script>

<!-- Clicking any of these links populates the region dimension with 'left-nav' -->
<div id="676967617A656C6C65" data-custom="left-nav">
  <a href="index.html">Home</a>
  <a href="products.html">View our products</a>
  <a href="contact.html">Contact us</a>
</div>
```
