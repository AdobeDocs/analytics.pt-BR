---
title: Variáveis de eVar (merchandising)
description: Variáveis personalizadas vinculadas a produtos individuais.
feature: Variables
exl-id: 26e0c4cd-3831-4572-afe2-6cda46704ff3
mini-toc-levels: 3
source-git-commit: e8a6400895110a14306e2dc9465e5de03d1b5d73
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 75%

---

# eVar (merchandising)

*Esta página de ajuda descreve como implementar as eVars de merchandising. Para obter informações sobre como as eVars de merchandising funcionam como uma dimensão, consulte [eVars (merchandising)](/help/components/dimensions/evar-merchandising.md) no guia Componentes do usuário.*

Para ver em detalhes como as eVars de merchandising funcionam, consulte [eVars de merchandising e métodos de descoberta de produtos](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/merchandising-evars.html?lang=pt-BR).

## Configurar eVars nas configurações do conjunto de relatórios

Antes de usar as eVars em sua implementação, configure a eVar com a sintaxe desejada nas configurações do conjunto de relatórios. Consulte [Variáveis de conversão](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) no Guia de administração.

>[!WARNING]
>
>A falha na configuração correta das eVars de merchandising resulta em valores inesperados ou perda de dados para a variável. Verifique se a configuração está correta para a implementação.

## Implementar utilizando a sintaxe do produto

Quando a “Sintaxe do produto” estiver ativada, a categoria de merchandising será preenchida diretamente na variável `products`, portanto, não é necessário selecionar ou configurar um evento compulsório. Esse é o método recomendado e que deve ser utilizado, salvo quando o valor não estiver disponível para definição em `products` quando o evento bem-sucedido ocorrer.

```js
// The bare minimum to set a merchandising eVar with product syntax
s.products = ";Example product;;;;eVar1=Example merchandising value";

// An example single product with product syntax
s.products = "Example category;Example product;1;5.99;event1=1;eVar1=Turtles";

// Tie a merchandising eVar to a different values on two different products
s.products = "Birds;Scarlet Macaw;1;4200;;eVar1=talking bird,Birds;Turtle dove;2;550;;eVar1=love birds";
```

O valor para `eVar1` é atribuído ao produto. Todos os eventos bem-sucedidos subsequentes e que envolverem este produto são creditados ao valor da eVar.

### Sintaxe do produto usando o SDK da Web

As variáveis de merchandising da sintaxe do produto são [mapeado para Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=pt-BR) em vários campos XDM diferentes.

* As eVars de merchandising da sintaxe do produto são mapeadas em `productListItems[]._experience.analytics.customDimensions.eVars.eVar1` para `productListItems[]._experience.analytics.customDimensions.eVars.eVar250`.
* Os eventos de merchandising da sintaxe do produto são mapeados em `productListItems[]._experience.analytics.event1to100.event1.value` para `productListItems[]._experience.analytics.event901to1000.event1000.value`. [Serialização de eventos](events/event-serialization.md) Campos XDM são mapeados em `productListItems[]._experience.analytics.event1to100.event1.id` para `productListItems[]._experience.analytics.event901to1000.event1000.id`.

O exemplo a seguir mostra um único [produto](products.md) usando várias eVars de merchandising e eventos:

```js
"productListItems": [
    {
        "name": "Bahama Shirt",
        "priceTotal": "12.99",
        "quantity": 3,
        "_experience": {
            "analytics": {
                "customDimensions" : {
                    "eVars" : {
                        "eVar10" : "green",
                        "eVar33" : "large"
                    }
                },
                "event1to100" : {
                    "event4" : {
                        "value" : 1
                    },
                    "event10" : {
                        "value" : 2,
                        "id" : "abcd"
                    }
                }
            }
        }
    }
]
```

O objeto de exemplo acima seria enviado para o Adobe Analytics como `";Bahama Shirt;3;12.99;event4|event10=2:abcd;eVar10=green|eVar33=large"`.

## Implementar utilizando a sintaxe da variável de conversão

A sintaxe da variável de conversão deve ser utilizada quando o valor da eVar não estiver disponível para a variável `products`. Normalmente, significa que sua página não tem o contexto do canal de merchandising ou do método de descoberta. Nesses casos, você define a variável de merchandising antes de chegar à página do produto e o valor persiste até que o evento compulsório ocorra.

Quando o evento compulsório selecionado durante a configuração ocorre, o valor persistente da eVar é associado ao produto. Por exemplo, se `prodView` for especificado como o evento compulsório, a categoria de merchandising está vinculada à lista de produtos atual somente no momento em que o evento ocorre. Somente eventos compulsórios subsequentes podem atualizar uma eVar de merchandising que já foi atribuída a um produto.

```js
// Place on the same or previous page before the binding event:
s.eVar1 = "Aviary";

// Place on the page where the binding event occurs:
s.events = "prodView";
s.products = ";Canary";
```

O valor `"Aviary"` para `eVar1` é atribuído ao produto `"Canary"`. Todos os eventos bem-sucedidos subsequentes que envolvem este produto são creditados a `"Canary"`. Além disso, o valor atual da variável de merchandising está vinculado a todos os produtos subsequentes até que uma destas condições seja atendida:

* A eVar expira (com base na configuração &quot;Expirar após&quot;)
* A eVar de merchandising é substituída por um novo valor.

### Sintaxe de variável de conversão usando o SDK da Web

A sintaxe da variável de conversão usando o SDK da Web opera de forma semelhante à implementação de outros [eVars](evar.md) e [events](events/events-overview.md). O espelhamento do XDM no exemplo acima seria semelhante ao seguinte:

Defina o eVar na mesma chamada de evento ou na chamada de evento anterior:

```js
"_experience": {
    "analytics": {
        "customDimensions": {
            "eVars": {
                "eVar1" : "Aviary"
            }
        }
    }
}
```

Defina o evento de vinculação e os valores da string de produtos:

```js
"commerce": {
    "productViews" : {
        "value" : 1
    }
},
"productListItems": [
    {
        "name": "Canary"
    }
]
```
