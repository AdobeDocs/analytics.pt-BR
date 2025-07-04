---
title: produtos
description: Envie dados sobre quais produtos são exibidos ou que estão no carrinho.
feature: Appmeasurement Implementation
exl-id: f26e7c93-f0f1-470e-a7e5-0e310ec666c7
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 67%

---

# produtos

A variável `products` rastreia produtos e propriedades associadas a eles. Normalmente, essa variável é definida em páginas de produto individuais, em páginas de carrinho de compras e em páginas de confirmação de compra. É uma variável de muitos valores, o que significa que você pode enviar vários produtos na mesma ocorrência e a Adobe analisa o valor e o divide em itens de dimensão separados.

>[!NOTE]
>
>Se essa variável for definida em uma ocorrência sem a [`events`](events/events-overview.md) variável, a métrica [Visualizações de produto](/help/components/metrics/product-views.md) será incrementada em 1. Defina os eventos apropriados em cada ocorrência com a variável `products`.

## Produtos que usam o Web SDK

Se estiver usando o [**objeto XDM**](/help/implement/aep-edge/xdm-var-mapping.md), os produtos serão mapeados para as seguintes variáveis:

* Categoria mapeada para `xdm.productListItems[].productCategories[].categoryID`. Ele usa o primeiro item na matriz `productCategories[]`. `lineItemId` também mapeia corretamente, mas a Adobe recomenda `categoryID`, pois é o XDM padrão. Se ambos os campos XDM estiverem presentes, `lineItemId` terá prioridade.
* Produto mapeado para `xdm.productListItems[].SKU` ou `xdm.productListItems[].name`. Se ambos os campos XDM estiverem presentes, `xdm.productListItems[].SKU` será usado.
* A quantidade está mapeada para `xdm.productListItems[].quantity`.
* Preço mapeado para `xdm.productListItems[].priceTotal`.
* As eVars de merchandising são mapeadas de `xdm.productListItems._experience.analytics.customDimensions.eVars.eVar1` a `xdm.productListItems._experience.analytics.customDimensions.eVars.eVar250`, dependendo de qual eVar você deseja vincular a um produto.
* Os eventos de merchandising são mapeados de `xdm.productListItems[]._experience.analytics.event1to100.event1.value` a `xdm.productListItems._experience.analytics.event901to1000.event1000.value`, dependendo do evento que você deseja vincular a um produto. Se você definir um evento em um desses campos, ele será automaticamente incluído na sequência de caracteres [event](events/events-overview.md) enviada ao Adobe Analytics.

```json
{
  "xdm": {
    "productListItems": [{
      "productCategories": [{
        "categoryID": "Men's"
      }],
      "name": "Hiking boot",
      "quantity": 1,
      "priceTotal": 49.99
    },
    {
      "productCategories": [{
        "categoryID": "Camping"
      }],
      "name": "Hunting blind",
      "quantity": 3,
      "priceTotal": 699.69
    }]
  }
}
```

Se estiver usando o [**objeto de dados**](/help/implement/aep-edge/data-var-mapping.md), a variável products usará `data.__adobe.analytics.products` após a sintaxe do AppMeasurement. Se você definir esse campo, quaisquer produtos definidos no objeto XDM serão substituídos e não enviados para o Adobe Analytics.

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "products": "Archery;Fletched arrow;12;159.99"
      }
    }
  }
}
```

## Produtos que usam a extensão Adobe Analytics

Não há um campo dedicado na Coleção de dados da Adobe Experience Platform para definir essa variável; no entanto, várias extensões de terceiros podem ajudar.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique em [!UICONTROL Catálogo] para ver todas as extensões disponíveis.
4. Pesquise usando o termo &quot;produto&quot;, que revela várias extensões disponíveis para ajudar a definir essa variável.

Você pode usar uma dessas extensões ou usar o editor de código personalizado abaixo, que está após a sintaxe do AppMeasurement.

## s.products no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.products` é uma string que contém vários campos delimitados por produto. Delimite cada campo com um ponto e vírgula (`;`) na sequência de caracteres.

* **Categoria** (opcional): a categoria do produto. O comprimento máximo deste campo é de 100 bytes.
* **Nome do produto** (obrigatório): o nome do produto. O comprimento máximo deste campo é de 100 bytes.
* **Quantidade** (opcional): a quantidade de produtos como esse que estão no carrinho. Esse campo se aplica somente às ocorrências com o evento de compra.
* **Preço** (opcional): o preço total do produto em formato decimal. Se a quantidade for superior a um, defina o preço total e não o preço individual do produto. Ajuste a moeda desse valor para corresponder ao da variável [`currencyCode`](../config-vars/currencycode.md). Não inclua o símbolo da moeda nesse campo. Esse campo se aplica somente às ocorrências com o evento de compra.
* **Eventos** (opcional): eventos vinculados ao produto. Delimite vários eventos usando uma barra vertical (`|`). Consulte [Eventos](events/events-overview.md) para obter mais informações.
* **eVars** (opcional): eVars de merchandising ligadas ao produto. Delimite várias eVars de merchandising usando uma barra vertical (`|`). Consulte [eVar de merchandising](evar-merchandising.md) para obter mais informações.

```js
// Set a single product using all available fields
s.products = "Example category;Example product;1;3.50;event1=4.99|event2=5.99;eVar1=Example merchandising value 1|eVar2=Example merchandising value 2";
```

Essa variável suporta vários produtos na mesma ocorrência. Ela é valiosa para carrinhos de compras e compras que contêm vários produtos. O comprimento máximo para toda a cadeia de caracteres `products` é de 64k bytes. Separe cada produto usando uma vírgula (`,`) na string.

```js
// Set multiple products - useful for when a visitor views their shopping cart
s.products = "Example category 1;Example product 1;1;3.50,Example category 2;Example product 2;1;5.99";
```

>[!WARNING]
>
>Retire todos os pontos e vírgulas, vírgulas e barra vertical dos nomes de produtos, categorias e valores de eVar de merchandising. Se o nome de um produto incluir uma vírgula, o AppMeasurement a analisa como o início de um novo produto. Essa análise incorreta descarta o restante da string do produto, causando dados incorretos em dimensões e relatórios.

## Exemplos

A variável `products` é flexível ao omitir campos e incluir vários produtos. Essa flexibilidade pode facilitar a perda de um delimitador, o que faz com que sua implementação envie dados incorretos para a Adobe.

```js
// Include only product and category. Common on individual product pages
s.products = "Example category;Example product";

// Include only product name
s.products = ";Example product";

// One product has a category, the other does not. Note the comma and adjacent semicolon to omit category
s.products = "Example category;Example product 1,;Example product 2";

// A visitor purchases a single product; record quantity and price
s.events = "purchase";
s.products = ";Example product;1;6.99";

// A visitor purchases multiple products with different quantities
s.events = "purchase";
s.products = ";Example product 1;9;26.91,Example category;Example product 2;4;9.96";

// Attribute currency event1 only to product 2 and not product 1
s.events = "event1";
s.products = ";Example product 1;1;1.99,Example category 2;Example product 2;1;2.69;event1=1.29";

// Use multiple numeric events in the product string
s.events = "event1,event2";
s.products = ";Example product;1;4.20;event1=2.3|event2=5";

// Use merchandising eVars without any events. Note the adjacent semicolons to skip events
s.products = ";Example product;1;6.69;;eVar1=Merchandising value";

// Use merchandising eVars without category, quantity, price, or events
s.products = ";Example product;;;;eVar1=Merchandising value";

// Multiple products using multiple different events and multiple different merchandising eVars
s.events = "event1,event2,event3,event4,purchase";
s.products = "Example category 1;Example product 1;3;12.60;event1=1.4|event2=9;eVar1=Merchandising value|eVar2=Another merchandising value,Example category 2;Example product 2;1;59.99;event3=6.99|event4=1;eVar3=Merchandising value 3|eVar4=Example value four";
```

Se estiver usando a `digitalData` [camada de dados](../../prepare/data-layer.md), você poderá iterar através da matriz de objetos `digitalData.product`:

```js
for(var i = 0; i < digitalData.product.length; i++) {
    // Add individual product info to the product string
    s.products += digitalData.product[i].category.primaryCategory + ";" + digitalData.product[i].productInfo.productName;
    // If there are more products, add a comma
    if(i != digitalData.product.length - 1) {
        s.products += ",";
    }
}
```
