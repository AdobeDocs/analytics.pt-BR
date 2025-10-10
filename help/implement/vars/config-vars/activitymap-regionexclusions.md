---
title: ActivityMap.regionExclusions
description: Filtrar dados do Activity Map por região.
role: Admin, Developer
feature: Appmeasurement Implementation
exl-id: 353282aa-860c-45dc-a6b0-8d9f1fa09f13
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 13%

---

# ActivityMap.regionExclusions

A variável `ActivityMap.regionExclusions` permite filtrar ou excluir seletivamente dados do Activity Map com base nos itens de dimensão coletados na dimensão [Região da Activity Map](/help/components/dimensions/activity-map-region.md).

## Exclusões de região na extensão Web SDK

Quando a **[!UICONTROL Habilitar coleta de dados de cliques]** estiver habilitada, use o bloco de código de retorno de chamada **[!UICONTROL Propriedades de cliques de filtro]**. Neste bloco de código, você pode verificar o valor de `content.linkRegion` e alterar o valor ou abandonar a coleção de dados de rastreamento de link.

## Exclusões de região na biblioteca JavaScript do Web SDK

Quando [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) estiver habilitado, use o retorno de chamada `filterClickDetails` no objeto `clickCollection`. Dentro dessa chamada de retorno, você pode verificar o valor de `linkRegion` e alterar o valor ou abandonar a coleção de dados de rastreamento de link.

```js
alloy("configure", {
  clickCollectionEnabled: true,
  clickCollection: {
    filterClickDetails: function(content) {
      // If the clicked region has personal links in it, don't send click data
      if(content.linkRegion.includes("personal")) {
        return false;
      }
    }
  }
});
```

## Exclusões de região usando a extensão do Adobe Analytics

Não há um campo dedicado na extensão do Adobe Analytics para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.ActivityMap.regionExclusions usando o AppMeasurement

A variável `s.ActivityMap.regionExclusions` é uma cadeia de caracteres que contém frases delimitadas por vírgulas a serem excluídas do rastreamento do Activity Map. Se qualquer uma das frases corresponder ao valor coletado na dimensão [Região da Activity Map](/help/components/dimensions/activity-map-region.md), todos os dados do Activity Map serão removidos da ocorrência.

```html
<script>
  var s = s_gi("examplersid");
  s.ActivityMap.regionExclusions = "contact";
</script>

<!-- Clicking any of these links tracks normally. -->
<!-- While "contact" is present, it is not tracked in region. The region is "nav" -->
<nav>
  <a href="index.html">Home</a>
  <a href="products.html">View our products</a>
  <a href="contact.html">Contact us</a>
</nav>

<!-- Activity Map data is not tracked for any of these links. -->
<!-- All these links belong to the region "Personal contact information" -->
<div id="personal-contact-information">
 <a href="mailto:user@example.com">Example user</a>
 <a href="mailto:user2@example.com">Example user 2</a>
 <a href="mailto:user3@example.com">Example user 3</a>
</div>
```
