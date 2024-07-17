---
title: ActivityMap.region
description: Personalize como o Activity Map coleta os cliques na região.
feature: Variables
role: Admin, Developer
source-git-commit: 1fb57590714ad2412323416289dee967eef07fad
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 12%

---

# ActivityMap.region

A variável `ActivityMap.region` permite que você substitua a lógica que o Activity Map usa para definir valores de região. Essa variável é útil em áreas onde você deseja ter mais controle do que o [`ActivityMap.regionExclusions`](../config-vars/activitymap-regionexclusions.md) oferece.

>[!CAUTION]
>Essa variável substitui completamente a lógica de Activity Map. Configurar uma função de substituição aqui que retorna valores incorretos pode causar problemas de coleta de dados com dimensões de Activity Map e a sobreposição de Activity Map.

## Substituição de valores de região usando o SDK da Web

Você pode usar o retorno de chamada [`OnBeforeLinkClickSend`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/onbeforelinkclicksend) para alterar a carga do SDK da Web ou cancelar o envio de dados.

## Substituição de região usando a extensão do Adobe Analytics

Não há um campo dedicado na extensão do Adobe Analytics para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## ActivityMap.region no AppMeasurement e o editor de código personalizado da extensão Analytics

Atribua a essa variável uma função que:

* Recebe o elemento de HTML que foi clicado; e
* Retorna um valor de string. Este valor de cadeia de caracteres é o valor final usado para a dimensão [Região do Activity Map](/help/components/dimensions/activity-map-region.md).

Se o valor de retorno for [falsy](https://developer.mozilla.org/pt-BR/docs/Glossario/Falsy), todas as variáveis de dados de contexto de Activity Map serão limpas e nenhum dado de link será rastreado.

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
