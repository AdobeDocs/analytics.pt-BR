---
title: ActivityMap.linkExclusions
description: Filtre dados de Activity Map pelo nome do link.
role: Admin, Developer
feature: Variables
source-git-commit: 05010d58ba2a3376473097e9d4543ee4415e83e1
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 11%

---

# ActivityMap.linkExclusions

A variável `ActivityMap.linkExclusions` permite filtrar ou excluir seletivamente dados de Activity Map com base no texto na dimensão [Link](/help/components/dimensions/activity-map-link.md) de Activity Map.

## Exclusões de link na extensão SDK da Web

Quando a **[!UICONTROL Habilitar coleta de dados de cliques]** estiver habilitada, use o bloco de código de retorno de chamada **[!UICONTROL Propriedades de cliques de filtro]**. Neste bloco de código, você pode verificar o valor de `content.linkName` e alterar o valor ou abandonar a coleção de dados de rastreamento de link.

## Exclusões de link na biblioteca JavaScript do SDK da Web

Quando [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) estiver habilitado, use o retorno de chamada `filterClickDetails` no objeto `clickCollection`. Dentro dessa chamada de retorno, você pode verificar o valor de `linkName` e alterar o valor ou abandonar a coleção de dados de rastreamento de link.

```js
alloy("configure", {
  clickCollectionEnabled: true,
  clickCollection: {
    filterClickDetails: function(content) {
      // If the link is a clickable telephone number, anonymize it
      if(content.linkUrl.includes("tel:")) {
        content.linkName = content.linkUrl = "Phone number";
      }
      // If the link is an email address, anonymize it
      if(content.linkUrl.includes("mailto:")) {
        content.linkName = content.linkUrl = "Email address";
      }
    }
  }
});
```

## Vincular exclusões usando a extensão do Adobe Analytics

Não há um campo dedicado na extensão do Adobe Analytics para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.ActivityMap.linkExclusions usando o AppMeasurement

A variável `s.ActivityMap.linkExclusions` é uma cadeia de caracteres que contém valores delimitados por vírgulas de frases a serem excluídas do rastreamento de Activity Map. Se qualquer uma das frases corresponder ao valor coletado na dimensão [Activity Map Link](/help/components/dimensions/activity-map-link.md), todos os dados de Activity Map serão removidos da ocorrência. Observe que essa variável procura `linkName`, não `linkUrl`.

```html
<script>
  var s = s_gi("examplersid");
  s.ActivityMap.linkExclusions = "Contact";
</script>

<!-- Clicking this link tracks normally -->
<a href="products.html">View our products</a>

<!-- Activity Map data is not tracked for this link -->
<a href="mailto:user@example.com">Contact this user</a>
```
