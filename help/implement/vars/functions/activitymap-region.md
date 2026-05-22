---
title: ActivityMap.region
description: Personalize como o Activity Map coleta os cliques na região.
feature: Appmeasurement Implementation
role: Admin, Developer
exl-id: 9bbdb124-b865-4431-8a98-9814c3f2e65c
TQID: 'https://experienceleague.adobe.com/EVVto7LRuTewu9y9AHLAPGn7sbqhJU3QSjlNtjKE5bQ'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 218
ht-degree: 15%

---

# ActivityMap.region

A variável `ActivityMap.region` permite substituir a lógica que o Activity Map usa para definir valores de região. Essa variável é útil em áreas onde você deseja ter mais controle do que o [`ActivityMap.regionExclusions`](../config-vars/activitymap-regionexclusions.md) oferece.

>[!CAUTION]
>Essa variável substitui completamente a lógica do Activity Map. Definir uma função de substituição aqui que retorna valores incorretos pode causar problemas de coleta de dados com dimensões do Activity Map e a sobreposição do Activity Map.

## Substituição de valores de região usando o Web SDK

Você pode usar o retorno de chamada [`OnBeforeLinkClickSend`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/onbeforelinkclicksend) para alterar a carga do Web SDK ou cancelar o envio de dados.

## Substituição de região usando a extensão do Adobe Analytics

Não há um campo dedicado na extensão do Adobe Analytics para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## ActivityMap.region no AppMeasurement e no editor de código personalizado da extensão Analytics

Atribua a essa variável uma função que:

* Recebe o elemento HTML que foi clicado; e
* Retorna um valor de string. Este valor de cadeia de caracteres é o valor final usado para a dimensão [Região do Activity Map](/help/components/dimensions/activity-map-region.md).

Se o valor de retorno for [falsy](https://developer.mozilla.org/pt-BR/docs/Glossario/Falsy), todas as variáveis de dados de contexto do Activity Map serão limpas e nenhum dado de link será rastreado.

## Exemplos

Usar um nome de tag em minúsculas como região:

```js
s.ActivityMap.region = function(clickedElement) {
  while (clickedElement && (clickedElement = clickedElement.parentNode)) {
    var regionId = clickedElement.tagName;
    if (regionId) {
      return regionId.toLowerCase();
    }
  }
}
```

Use nomes de classe desejados específicos como região:

```js
s.ActivityMap.region = function(ele) {
  var className,
  classNames = {
    'header': 1,
    'navbar': 1,
    'left-content': 1,
    'main-content': 1,
    'footer': 1,
  };
  while ((ele && (ele = ele.parentNode))) {
    if ((className = ele.className)) {
      let classes = className.split(' ');
      for (let i = 0; i < classes.length; i++) {
        if (classNames[classes[i]]) {
          return classes[i];
        }
      }
    }
  }
  return "BODY";
}
```
