---
title: ActivityMap.link
description: Personalize como o Activity Map coleta os cliques no link.
feature: Variables
role: Admin, Developer
source-git-commit: 72b38970e573b928e4dc4a8c8efdbfb753be0f4e
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 8%

---

# ActivityMap.link

A variável `ActivityMap.link` permite que você substitua a lógica que o Activity Map usa para definir valores de link. Essa variável é útil em áreas onde você deseja ter mais controle do que o [`ActivityMap.linkExclusions`](../config-vars/activitymap-linkexclusions.md) oferece.

>[!CAUTION]
>Essa variável substitui completamente a lógica de Activity Map. Configurar uma função de substituição aqui que retorna valores incorretos pode causar problemas de coleta de dados com dimensões de Activity Map e a sobreposição de Activity Map.

## Substituição de valores de link usando o SDK da Web

Você pode usar o retorno de chamada [`OnBeforeLinkClickSend`](https://experienceleague.adobe.com/pt-br/docs/experience-platform/web-sdk/commands/configure/onbeforelinkclicksend) para alterar a carga do SDK da Web ou cancelar o envio de dados.

## Substituição de link usando a extensão do Adobe Analytics

Não há um campo dedicado na extensão do Adobe Analytics para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## ActivityMap.link no AppMeasurement e no editor de código personalizado da extensão do Analytics

Atribua a essa variável uma função que:

* Recebe o elemento de HTML que foi clicado; e
* Retorna um valor de string. Este valor de cadeia de caracteres é o valor final usado para a dimensão [Link de Activity Map](/help/components/dimensions/activity-map-link.md).

Se o valor de retorno for [falsy](https://developer.mozilla.org/pt-BR/docs/Glossario/Falsy), todas as variáveis de dados de contexto de Activity Map serão limpas e nenhum dado de link será rastreado.

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
2. Quando chamado por Activity Map, um `linkName` nunca é passado, então, chame `customFunction()` com o elemento de link. Você pode usar qualquer função personalizada para retornar um valor.
3. Se nenhum dos valores de retorno acima for exibido, use o nome do link normalmente coletado como um fallback.
