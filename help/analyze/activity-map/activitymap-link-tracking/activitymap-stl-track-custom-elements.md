---
title: Use o método tl() com Activity Map
description: Você pode usar o método tl() para rastrear elementos personalizados e configurar a renderização de sobreposição para o conteúdo dinâmico.
feature: Activity Map
role: Profissional de negócios, Administrador
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 43%

---


# Use o método `tl()` com Activity Map

Você pode usar o método `tl()` para rastrear elementos personalizados e configurar a renderização de sobreposição para o conteúdo dinâmico.

## Rastreamento de elementos personalizados

Usar o [`tl()` método](/help/implement/vars/functions/tl-method.md) como parte do módulo AppMeasurement do Activity Map permite rastrear qualquer objeto clicado, até mesmo objetos que não são tags de âncora ou elementos de imagem. Usando `tl()`, você pode rastrear todos os elementos personalizados que não resultam em um carregamento da página.

No método `tl()`, o parâmetro `linkName` é atualmente usado para identificar links de saída, links personalizados, etc. Ele também é usado para identificar a ID do link para a variável do Activity Map.

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

Em outras palavras, se você usar `tl()` para rastrear seus elementos personalizados, a ID do link é retirada do valor passado como o terceiro parâmetro (Nome do link) no método `tl()`. Ela não é retirada do algoritmo de rastreamento de links padrão, utilizado para o [rastreamento padrão](activitymap-link-tracking-methodology.md) no Activity Map.

## Renderização de sobreposição para o conteúdo dinâmico

Quando o método `tl()` é chamado diretamente no evento de cliques do elemento HTML, o Activity Map pode exibir uma sobreposição para esse elemento quando a página da Web é carregada. Exemplo:

```html
<a href="javascript:" onclick="s.tl(this,'o','Example custom link');">Example link text</a>
```

Sempre que qualquer conteúdo da página da Web for adicionado à página após o carregamento inicial, o método `tl()` é chamado indiretamente e não é possível exibir sobreposições para o novo conteúdo, a menos que elas sejam expressamente ativadas/clicadas. Em seguida, um novo processo de coleta de links é acionado no Activity Map.

Quando o método `tl()` não é chamado diretamente no evento de cliques do elemento HTML, o Activity Map só poderá exibir a sobreposição depois que o elemento for clicado pelo usuário. Veja um exemplo onde o método `tl()` é chamado indiretamente:

```html
<a href="javascript:" onclick="someFn(event);">Example link text</a>
<script>function someFn (event)
{
  s.tl(event.srcElement,'o','Example custom link');
}
</script>
```

A melhor maneira de fazer com que o Activity Map sobreponha links de conteúdo dinâmico é ter uma função `ActivityMap.link` personalizada configurada para chamar a mesma função cujo valor de retorno é passado a `tl()`. Por exemplo:

```js
var originalLinkFunction = s.ActivityMap.link;
s.ActivityMap.link = function(element,linkName)
{
    // if this is a s.tl call, just return string passed
    return linkName ||      
    // this is ActivityMap reporting time
    makeLinkName(element) ||
    // our custom function didn't return anything, so just return the default ActivityMap Link
    originalLinkFunction(element,linkName);
};
```

```html
<button type="button" onclick="s.tl(this,'o',makeLinkName(this)">Add To Cart</button>
```

Aqui, substituímos a função `ActivityMap.link` para fazer uma das três coisas quando chamadas:

1. Se `linkName` for passado, isso foi chamado por `tl()`, então apenas retorne o que `tl()` passou como `linkName`.
2. Quando chamado por Activity Map no momento do relatório, um `linkName` nunca é transmitido, portanto, chame `makeLinkName()` com o elemento de link. Esta é a etapa principal - a chamada `makeLinkName(element)` deve ser a mesma do terceiro argumento da chamada `tl()` na tag `<button>`. Isso significa que quando `tl()` é chamado, rastreamos a cadeia de caracteres retornada por `makeLinkName()`. Quando o Activity Map relata os links na página, ele usa a mesma chamada para criar um link.
3. A solução final é retornar o valor original de retorno da função padrão de link do ActivityMap. Manter essa referência em volta para chamar no caso padrão ajuda a precisar apenas substituir ou gravar o código personalizado de `makeLinkName()` e não precisar criar um valor de retorno de link para todos os links na página.
