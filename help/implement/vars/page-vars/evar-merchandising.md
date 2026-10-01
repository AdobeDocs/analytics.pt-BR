---
title: eVar (variável de merchandising)
description: Variáveis personalizadas vinculadas a produtos individuais.
feature: Appmeasurement Implementation
exl-id: 26e0c4cd-3831-4572-afe2-6cda46704ff3
mini-toc-levels: 3
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/BdChWcR9AJqLZ0KjOxSvFAjB8-58JmmGahrpvTyFeFI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: ca917b867cd84b09b899ce7b72586f0b15003106
workflow-type: tm+mt
source-wordcount: '787'
ht-degree: 29%
---
# eVar (merchandising)

>[!BEGINSHADEBOX]

*Esta página de ajuda descreve como implementar as eVars de merchandising. Para obter informações sobre como as eVars de merchandising funcionam como uma dimensão, consulte [eVar (dimensão de merchandising)](/help/components/dimensions/evar-merchandising.md) no guia do usuário Componentes.*

>[!ENDSHADEBOX]

As eVars de merchandising vinculam um valor a produtos individuais, de modo que os eventos bem-sucedidos envolvendo cada produto são creditados ao valor vinculado a esse produto. Você pode definir o valor de uma das duas formas a seguir:

* **[!UICONTROL Sintaxe do produto]**: defina o valor de cada produto na variável [`products`](products.md).
* **[!UICONTROL Sintaxe de variável de conversão]**: defina o valor no próprio eVar. O valor vincula aos produtos em uma ocorrência que contém um evento compulsório.

Para saber como a associação, a alocação e a expiração funcionam, consulte [eVar (dimensão de Merchandising)](/help/components/dimensions/evar-merchandising.md).

## Configurar eVars nas configurações do conjunto de relatórios

Antes de usar as eVars em sua implementação, configure-as com a sintaxe desejada nas configurações do conjunto de relatórios. Consulte [Variáveis de conversão](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md) no Guia de administração.

>[!WARNING]
>
>A falha na configuração correta das eVars de merchandising resulta em valores inesperados ou perda de dados para a variável. Verifique se a configuração está correta para a implementação.

## Escolha uma sintaxe

Use a [!UICONTROL Sintaxe do Produto] quando o valor de merchandising estiver disponível no momento em que você definir a variável `products`, ou quando os produtos na mesma ocorrência precisarem de valores diferentes. Use a [!UICONTROL Sintaxe de variável de conversão] quando o valor for conhecido antes do produto, como o termo de pesquisa ou campanha interna que levou o visitante ao produto. Consulte [Como a associação e a alocação funcionam](/help/components/dimensions/evar-merchandising.md#how-binding-and-allocation-work) para obter uma comparação completa.

## Implementar utilizando a sintaxe do produto

Quando a [!UICONTROL Sintaxe do Produto] está habilitada, o valor de merchandising é definido diretamente na variável `products`, portanto, os eventos de associação não são usados. As eVars de merchandising aparecem no último segmento de cada produto:

```js
s.products = "[category];[name];[quantity];[revenue];[events];[eVars]";
```

Delimite várias eVars de merchandising no mesmo produto usando uma barra vertical (`|`). Os espaços reservados vazios para quantidade, receita e eventos são necessários, mesmo que você não os use. Sem eles, o valor eVar é ignorado.

O valor está vinculado ao produto nessa ocorrência. A substituição de uma associação existente por um valor posterior depende da configuração [!UICONTROL Allocation]. Consulte [Como a associação e a alocação funcionam](/help/components/dimensions/evar-merchandising.md#how-binding-and-allocation-work).

```js
// The bare minimum to set a merchandising eVar with product syntax
s.products = ";Example product;;;;eVar1=Example merchandising value";

// An example single product with product syntax
s.products = "Example category;Example product;1;5.99;event1=1;eVar1=Turtles";

// Tie a merchandising eVar to different values on two different products
s.products = "Birds;Scarlet Macaw;1;4200;;eVar1=talking bird,Birds;Turtle dove;2;550;;eVar1=love birds";
```

### Sintaxe do produto usando o SDK da Web

Se estiver usando o [**objeto XDM**](/help/implement/aep-edge/xdm-var-mapping.md), as variáveis de merchandising da sintaxe do produto usarão os seguintes campos XDM:

* As eVars de merchandising da sintaxe do produto são mapeadas em `xdm.productListItems[]._experience.analytics.customDimensions.eVars.eVar1` para `xdm.productListItems[]._experience.analytics.customDimensions.eVars.eVar250`.
* Os eventos de merchandising da sintaxe do produto são mapeados em `xdm.productListItems[]._experience.analytics.event1to100.event1.value` para `xdm.productListItems[]._experience.analytics.event901to1000.event1000.value`. Os campos XDM da [serialização de eventos](events/event-serialization.md) são mapeados em `xdm.productListItems[]._experience.analytics.event1to100.event1.id` a `xdm.productListItems[]._experience.analytics.event901to1000.event1000.id`.

>[!NOTE]
>
>Ao definir eventos em `productListItems`, não é necessário defini-los na string do evento. Se estiverem definidos em ambos os lugares, o valor na string do evento terá prioridade.

O exemplo a seguir mostra um único [produto](products.md) que usa vários eventos e eVars de merchandising:

```json
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

Se estiver usando o [**objeto de dados**](/help/implement/aep-edge/data-var-mapping.md), as eVars de merchandising com sintaxe de produto serão definidas em `data.__adobe.analytics.products`, usando a mesma sintaxe que a variável `products` do AppMeasurement. O equivalente do objeto de dados do exemplo XDM acima:

```json
"data": {
  "__adobe": {
    "analytics": {
      "products": ";Bahama Shirt;3;12.99;event4|event10=2:abcd;eVar10=green|eVar33=large"
    }
  }
}
```

## Implementar utilizando a sintaxe da variável de conversão

Use a [!UICONTROL Sintaxe de Variável de Conversão] quando o valor de eVar não estiver disponível para definição na variável `products`. Normalmente, significa que a página do seu produto não tem o contexto do canal de merchandising ou do método de descoberta. Nesses casos, defina o eVar de merchandising na página em que o evento compulsório ocorre ou antes dela. O valor persiste até expirar ou é substituído por um novo valor.

Quando uma ocorrência contém a variável `products` e um [!UICONTROL Evento compulsório de merchandising] selecionado, o valor atual da eVar vincula-se a cada produto nessa ocorrência. Definir o eVar ao lado de um produto sem um evento compulsório não vincula o valor. Se uma associação posterior substituirá uma existente dependerá da configuração [!UICONTROL Alocação]. Consulte [Como a associação e a alocação funcionam](/help/components/dimensions/evar-merchandising.md#how-binding-and-allocation-work).

Para obter um exemplo que define várias eVars de método de descoberta de produto de uma só vez, consulte [Prática recomendada: métodos de descoberta de produto](/help/components/dimensions/evar-merchandising.md#best-practice-product-finding-methods).

O exemplo a seguir define um eVar de merchandising antes do evento compulsório:

```js
// Place on the same or previous page before the binding event:
s.eVar1 = "Aviary";

// Place on the page where the binding event occurs:
s.events = "prodView";
s.products = ";Canary";
```

Se o [!UICONTROL Evento de Exibição de Produto] for um evento de associação, o valor `"Aviary"` para `eVar1` será associado ao produto `"Canary"`. Eventos bem-sucedidos subsequentes que envolvem este produto são creditados a `"Aviary"`. O valor `"Aviary"` também se associa a produtos em ocorrências posteriores que contenham um evento compulsório, até que uma das seguintes condições seja atendida:

* O eVar expira (com base na configuração [!UICONTROL Expirar após]).
* A eVar de merchandising é substituída por um novo valor.

### Sintaxe de variável de conversão usando o SDK da Web

Se estiver usando o [**objeto XDM**](/help/implement/aep-edge/xdm-var-mapping.md), a sintaxe operará de forma semelhante à implementação de outros [eVars](evar.md) e [eventos](events/events-overview.md). Se estiver usando o [**objeto de dados**](/help/implement/aep-edge/data-var-mapping.md), a sintaxe segue o AppMeasurement.

O espelhamento do XDM no exemplo do AppMeasurement acima seria semelhante ao seguinte.

Defina a eVar na mesma chamada de evento ou na anterior:

```json
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

Defina o evento compulsório e os valores da string de produtos:

```json
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

Os objetos de dados que espelham o exemplo do AppMeasurement acima seriam semelhantes ao seguinte.

Defina a eVar na mesma chamada de evento ou na anterior:

```json
"data": {
  "__adobe": {
    "analytics": {
      "eVar1": "Aviary"
    }
  }
}
```

Defina o evento compulsório e os valores da string de produtos:

```json
"data": {
  "__adobe": {
    "analytics": {
      "events": "prodView",
      "products": ";Canary"
    }
  }
}
```

