---
description: Você pode usar a função s.tl() para rastrear elementos personalizados e configurar a renderização de sobreposição para o conteúdo dinâmico.
title: Usar a função s.tl()
topic: Activity map
uuid: 59e062af-6a1c-46ff-9c3b-6cf7a0453711
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Usar a função s.tl()

Você pode usar a função s.tl() para rastrear elementos personalizados e configurar a renderização de sobreposição para o conteúdo dinâmico.

## Rastreamento de elementos personalizados {#section_5D6688DFFFC241718249A9A0C632E465}

Usar a [função s.tl()](https://marketing.adobe.com/resources/help/en_US/sc/implement/function_tl.html) como parte do módulo AppMeasurement do Activity Map permite rastrear qualquer objeto clicado, até mesmo objetos que não são tags de âncora ou elementos de imagem. Ao usar a s.tl, é possível rastrear todos os elementos personalizados que não resultam em um carregamento da página.

Na função s.tl, o parâmetro linkName é atualmente usado para identificar links de saída, links personalizados, etc. Ele também é usado para identificar a ID do link para a variável do Activity Map.

```
s.tl(this,linkType, 
<b>linkName</b>,variableOverrides,doneAction)
```

Em outras palavras, se você usar a s.tl para rastrear seus elementos personalizados, a ID do link é retirada do valor passado como o terceiro parâmetro (linkName) na função s.tl. Ela não é retirada do algoritmo de rastreamento de links padrão, utilizado para o [rastreamento padrão](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md) no Activity Map.

## Rederização de sobreposição para o conteúdo dinâmico {#section_FD24B61A732149C7B58BA957DD84A5E7}

Quando a função s.tl() é chamada diretamente no evento de cliques do elemento HTML, o Activity Map poderá exibir uma sobreposição para esse elemento ao carregar a página da Web. Exemplo:

```
<div onclick="s.tl(this,'o','some link name')">Text to click on</a>
```

Sempre que qualquer conteúdo da página da Web for adicionado à página após o carregamento inicial, a função s.tl é chamada indiretamente e não é possível exibir sobreposições para o novo conteúdo, a menos que elas sejam expressamente ativadas/clicadas. Em seguida, um novo processo de coleta de links é acionado no Activity Map.

Quando a função s.tl() não é chamada diretamente no evento de cliques do elemento HTML, o Activity Map só poderá exibir a sobreposição depois que o elemento for clicado pelo usuário. Veja um exemplo onde a função s.tl() é chamada indiretamente:

```
<div onclick="someFn(event)"></div> 
 <script>function someFn (event) 
 {    
 s.tl(event.srcElement,'o','some link name'); 
 } 
 </script>
```

A melhor maneira de fazer com que o Activity Map sobreponha links de conteúdo dinâmico é ter uma função ActivityMap.link personalizada configurada para chamar a mesma função cujo valor de retorno é passado a s.tl. Veja um exemplo:

```
var originalLinkFunction = s.ActivityMap.link; 
s.ActivityMap.link = function(element,linkName){ 
    return linkName ||      // if this is a s.tl call, just return string passed 
        makeLinkName(element) || // this is ActivityMap reporting time 
        originalLinkFunction(element,linkName); // our custom function didn't return anything, so just return the default ActivityMap Link 
};
```

```
<button type="button" onclick="s.tl(this,'o',makeLinkName(this)">Add To Cart</button>
```

Aqui, reconfiguramos a função ActivityMap.link para executar uma das seguintes ações quando chamada:

1. Se linkName for passado, a chamada será feita por s.tl(), portanto retorne somente o que s.tl passou como linkName.
1. A chamada é feita pelo Activity Map no momento do relatório, para que um linkName não seja passado, portanto chame makeLinkName() com o elemento do link. Esta é a etapa principal – a chamada “makeLinkName(element)” deve ser a mesma no terceiro argumento s.tl da chamada na tag `<button>`. Ou seja, quando s.tl é chamado, rastreamos a sequência de caracteres retornada por makeLinkName. Quando o Activity Map reportas os links na página, ele usa a mesma chamada para criar um link.
1. A solução final é retornar o valor original de retorno da função padrão de link do Activity Map. Recomenda-se que você mantenha esta referência para fazer a chamada no caso padrão, para que seja necessário somente sobrescrever ou escrever um código personalizado para makeLinkName e não ter que criar um valor de retorno de link para todos os links na página.
