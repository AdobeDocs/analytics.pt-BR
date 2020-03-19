---
description: Você pode usar o método s.tl() para rastrear elementos personalizados e configurar a renderização de sobreposição para conteúdo dinâmico.
title: Usar o método s.tl()
topic: Activity map
uuid: 59e062af-6a1c-46ff-9c3b-6cf7a0453711
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Usar o `tl()` método

You can use the `tl()` method to track custom elements and to configure overlay rendering for dynamic content.

## Rastreamento de elementos personalizados {#section_5D6688DFFFC241718249A9A0C632E465}

Using the [`tl()` method](/help/implement/vars/functions/tl-method.md) as part of the Activity Map AppMeasurement module lets you track any object that is clicked on, even objects that are not anchor tags or image elements. Ao usar a s.tl, é possível rastrear todos os elementos personalizados que não resultam em um carregamento da página.

In the `tl()` method, the `linkName` parameter that is currently used to identify the exit links, custom links, etc. Ele também é usado para identificar a ID do link para a variável do Activity Map.

```js
s.tl(this,linkType,linkName,variableOverrides)
```

In other words, if you use `s.tl()` to track your custom elements, the link ID is pulled from the value passed as the third parameter (linkName) in the `s.tl()` method. Ela não é retirada do algoritmo de rastreamento de links padrão, utilizado para o [rastreamento padrão](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md) no Activity Map.

## Renderização de sobreposição para o conteúdo dinâmico {#section_FD24B61A732149C7B58BA957DD84A5E7}

Quando a função s.tl() é chamada diretamente no evento de cliques do elemento HTML, o Activity Map poderá exibir uma sobreposição para esse elemento ao carregar a página da Web. Exemplo:

```html
<div onclick="s.tl(this,'o','Example custom link')">Example link text</a>
```

Whenever any web page content is added to the page after the initial page load, the `tl()` method is called indirectly and we cannot display overlays for that new content unless it is expressly activated/clicked. Em seguida, um novo processo de coleta de links é acionado no Activity Map.

When the `tl()` method is not called directly from the HTML element&#39;s on-click event, Activity Map can only display overlay once that element has been clicked by the user. Here is an example where the `tl()` method is called indirectly:

```html
<div onclick="someFn(event)"></div>
<script>function someFn (event)
{
  s.tl(event.srcElement,'o','Example custom link');
}
</script>
```

A melhor maneira de fazer com que o Activity Map sobreponha links de conteúdo dinâmico é ter uma função ActivityMap.link personalizada configurada para chamar a mesma função cujo valor de retorno é passado a `s.tl`. Por exemplo:

```js
var originalLinkFunction = s.ActivityMap.link;
s.ActivityMap.link = function(element,linkName) {
    return linkName ||      // if this is a s.tl call, just return string passed
        makeLinkName(element) || // this is ActivityMap reporting time
        originalLinkFunction(element,linkName); // our custom function didn't return anything, so just return the default ActivityMap Link
};
```

```html
<button type="button" onclick="s.tl(this,'o',makeLinkName(this)">Add To Cart</button>
```

Aqui, reconfiguramos a função ActivityMap.link para executar uma das seguintes ações quando chamada:

1. Se linkName for passado, a chamada será feita por s.tl(), portanto retorne somente o que s.tl passou como linkName.
2. A chamada é feita pelo Activity Map no momento do relatório, para que um linkName não seja passado, portanto chame makeLinkName() com o elemento do link. Esta é a etapa principal – a chamada “makeLinkName(element)” deve ser a mesma no terceiro argumento s.tl da chamada na tag `<button>`. Ou seja, quando s.tl é chamado, rastreamos a sequência de caracteres retornada por makeLinkName. Quando o Activity Map reportas os links na página, ele usa a mesma chamada para criar um link.
3. A solução final é retornar o valor original de retorno da função padrão de link do ActivityMap. Recomenda-se que você mantenha esta referência para fazer a chamada no caso padrão, para que seja necessário somente sobrescrever ou escrever um código personalizado para makeLinkName e não ter que criar um valor de retorno de link para todos os links na página.
