---
title: ActivityMap.link
description: Personalize como o Activity Map coleta o link clicado.
feature: Appmeasurement Implementation
role: Admin, Developer
exl-id: 3a31f80b-dbee-4a45-ac3c-0b8ca198c95a
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 9%

---

# ActivityMap.link

A variável `ActivityMap.link` permite substituir a lógica usada pelo Activity Map para definir valores de link. Essa variável é útil em áreas onde você deseja ter mais controle do que o [`ActivityMap.linkExclusions`](../config-vars/activitymap-linkexclusions.md) oferece.

>[!CAUTION]
>Essa variável substitui completamente a lógica do Activity Map. Definir uma função de substituição aqui que retorna valores incorretos pode causar problemas de coleta de dados com dimensões do Activity Map e a sobreposição do Activity Map.

## Substituição de valores de link usando o Web SDK

Você pode usar o retorno de chamada [`OnBeforeLinkClickSend`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/onbeforelinkclicksend) para alterar a carga do Web SDK ou cancelar o envio de dados.

## Substituição de link usando a extensão do Adobe Analytics

Não há um campo dedicado na extensão do Adobe Analytics para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## ActivityMap.link no AppMeasurement e no editor de código personalizado da extensão do Analytics

Atribua a essa variável uma função que:

* Recebe o elemento HTML que foi clicado; e
* Retorna um valor de string. Este valor de cadeia de caracteres é o valor final usado para a dimensão [Link do Activity Map](/help/components/dimensions/activity-map-link.md).

Se o valor de retorno for [falsy](https://developer.mozilla.org/pt-BR/docs/Glossario/Falsy), todas as variáveis de dados de contexto do Activity Map serão limpas e nenhum dado de link será rastreado.

## Exemplos

Use somente o atributo de título de `<a>` marcas. Se o atributo de título não estiver presente, nenhum link será rastreado.

```js
s.ActivityMap.link = function(clickedElement) {
  var linkId;
  if (clickedElement && clickedElement.tagName.toUpperCase() === 'A') {
    linkId = clickedElement.getAttribute('title');
  }
  return linkId;
}
```

Retorne o nome do link definido manualmente em `s.tl`, se ele existir, caso contrário, retorne a URL do link.

```js
s.ActivityMap.link = function(ele, linkName) {
  if (linkName) {
    return linkName;
  }
  if (ele && ele.tagName == 'A' && ele.href) {
    return ele.href;
  }
}
```

Em vez de substituir completamente a lógica de link padrão, você pode alterá-la condicionalmente.

```html
<script>
  // Copy the original link function
  var originalLinkFunction = s.ActivityMap.link;
  // Return the link name from s.tl, a modified activity map value, or the original activity map value
  s.ActivityMap.link = function(element,linkName)
  {
    return linkName || customFunction(element) || originalLinkFunction(element,linkName);
  };
</script>

<button type="button" onclick="s.tl(this,'o',customFunction(this)">Add To Cart</button>
```

1. Se `linkName` for passado, o método foi chamado por `tl()`. Retornar o que `tl()` passou como `linkName`.
2. Quando chamado pelo Activity Map, um `linkName` nunca é passado, então, chame `customFunction()` com o elemento de link. Você pode usar qualquer função personalizada para retornar um valor.
3. Se nenhum dos valores de retorno acima for exibido, use o nome do link normalmente coletado como um fallback.
