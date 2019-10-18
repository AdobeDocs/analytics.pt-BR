---
description: Você pode usar a função s.tl() para rastrear elementos personalizados e configurar a renderização de sobreposição para o conteúdo dinâmico.
seo-description: Você pode usar a função s.tl() para rastrear elementos personalizados e configurar a renderização de sobreposição para o conteúdo dinâmico.
seo-title: Usar a função s.tl()
solution: Analytics
title: Usar a função s.tl()
topic: Activity Map
uuid: 59e062af-6a1c-46ff-9c3b-6cf7a0453711
translation-type: tm+mt
source-git-commit: 36637b76b8026fbf87ad48adcfa47386c530e732

---


# Usar a função s.tl()

Você pode usar a função s.tl() para rastrear elementos personalizados e configurar a renderização de sobreposição para o conteúdo dinâmico.

## Tracking custom elements {#section_5D6688DFFFC241718249A9A0C632E465}

Usar a [função s.tl()](https://marketing.adobe.com/resources/help/en_US/sc/implement/function_tl.html) como parte do módulo AppMeasurement do permite rastrear qualquer objeto clicado, até mesmo objetos que não são tags de âncora ou elementos de imagem. [!DNL Activity Map] Ao usar a s.tl, é possível rastrear todos os elementos personalizados que não resultam em um carregamento da página.

Na função s.tl, o parâmetro linkName é atualmente usado para identificar links de saída, links personalizados, etc. is now also used to identify the Link ID for the [!DNL Activity Map] variable.

```
s.tl(this,linkType, 
<b>linkName</b>,variableOverrides,doneAction)
```

Em outras palavras, se você usar a s.tl para rastrear seus elementos personalizados, a ID do link é retirada do valor passado como o terceiro parâmetro (linkName) na função s.tl. Ela não é retirada do algoritmo de rastreamento de links padrão, utilizado para o [rastreamento padrão](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md) no [!DNL Activity Map].

## Overlay rendering for dynamic content {#section_FD24B61A732149C7B58BA957DD84A5E7}

When the s.tl() function is called directly from the HTML element’s on-click event, [!DNL Activity Map] can display an overlay for that element when the web page is loaded. Exemplo:

```
<div onclick="s.tl(this,'o','some link name')">Text to click on</a>
```

Sempre que qualquer conteúdo da página da Web for adicionado à página após o carregamento inicial, a função s.tl é chamada indiretamente e não é possível exibir sobreposições para o novo conteúdo, a menos que elas sejam expressamente ativadas/clicadas. Em seguida, um novo processo de coleta de links é acionado no [!DNL Activity Map].

When the s.tl() function is not called directly from the HTML element’s on-click event, [!DNL Activity Map] can only display overlay once that element has been clicked by the user. Veja um exemplo onde a função s.tl() é chamada indiretamente:

```
<div onclick="someFn(event)"></div> 
 <script>function someFn (event) 
 {    
 s.tl(event.srcElement,'o','some link name'); 
 } 
 </script>
```

The best way for [!DNL Activity Map] to overlay dynamic content links is to have a customized ActivityMap.link function set up to call the same function whose return value is passed to s.tl. Veja um exemplo:

```
var originalLinkFunction = s.ActivityMap.link; 
s.ActivityMap.link = function(element,linkName){ 
    return linkName ||      // if this is a s.tl call, just return string passed 
        makeLinkName(element) || // this is ActivityMap reporting time 
        originalLinkFunction(element,linkName); // our custom function didn't return anything, so just return the default ActivityMap Link 
};
```

```
<button type=”button” onclick=”s.tl(this,’o’,makeLinkName(this)”>Add To Cart</button>
```

Aqui, reconfiguramos a função ActivityMap.link para executar uma das seguintes ações quando chamada:

1. Se linkName for passado, a chamada será feita por s.tl(), portanto retorne somente o que s.tl passou como linkName.
1. This is called by [!DNL Activity Map] at reporting time, so a linkName is never passed, and so call makeLinkName() with the link element. This is the crucial step here - the “makeLinkName(element)” call should be the same at the s.tl call’s 3rd argument in the `<button>` tag. Ou seja, quando s.tl é chamado, rastreamos a sequência de caracteres retornada por makeLinkName. When [!DNL Activity Map] reports on the links on the page, is uses the same call to make a link.
1. A solução final é retornar o valor original de retorno da função padrão de link do Activity Map. Recomenda-se que você mantenha esta referência para fazer a chamada no caso padrão, para que seja necessário somente sobrescrever ou escrever um código personalizado para makeLinkName e não ter que criar um valor de retorno de link para todos os links na página.
