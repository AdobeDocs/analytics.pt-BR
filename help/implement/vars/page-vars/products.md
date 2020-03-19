---
title: products
description: Envie dados sobre quais produtos são exibidos ou no carrinho.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# products

A `products` variável rastreia produtos e propriedades associadas a eles. Normalmente, essa variável é definida em páginas de produto individuais, páginas de carrinho de compras e páginas de confirmação de compra. É uma variável de vários valores, o que significa que você pode enviar vários produtos na mesma ocorrência e a Adobe analisa o valor em valores de dimensão separados.

> [!NOTE] Se essa variável for definida em uma ocorrência sem um evento de carrinho de compras na [`events`](events/events-overview.md) variável, a métrica &quot;Exibições do produto&quot; será incrementada em 1. Certifique-se de definir o evento de carrinho de compras apropriado em cada ocorrência.

## Produtos no Adobe Experience Platform Launch

Não há um campo dedicado no Launch para definir essa variável; no entanto, existem várias extensões de terceiros para ajudar.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá para a [!UICONTROL Extensions] guia e clique em [!UICONTROL Catalog] para ver todas as extensões disponíveis.
4. Procure o termo &quot;produto&quot;, que revela várias extensões disponíveis para ajudar a definir essa variável.

Você pode usar uma dessas extensões ou pode usar o editor de código personalizado após a sintaxe do AppMeasurement abaixo.

## s.products no AppMeasurement e no editor de código personalizado do Launch

A `s.products` variável é uma string que contém vários campos delimitados por produto. Cada produto individual pode conter até 100 bytes em todos os campos. Delimite cada campo com um ponto-e-vírgula (`;`) na string.

* **Categoria** (opcional): A categoria de produto abrangente. Sua organização decide como agrupar produtos em categorias.
* **Nome** do produto (obrigatório): O nome do produto.
* **Quantidade** (opcional): Quantos deste produto estão no carrinho. Esse campo se aplica somente às ocorrências com o evento purchase.
* **Preço** (opcional): O preço total do produto como uma casa decimal. Se a quantidade for superior a um, defina o preço no total e não o preço individual do produto. Alinhe a moeda desse valor para corresponder à [`currencyCode`](../config-vars/currencycode.md) variável. Não inclua o símbolo de moeda neste campo. Esse campo se aplica somente às ocorrências com o evento purchase.
* **Eventos** (opcional): Eventos vinculados ao produto. Delimitar vários eventos com um pipe (`|`). Consulte [eventos](events/events-overview.md) para obter mais informações.
* **eVars** (opcional): eVars de comercialização ligadas ao produto. Delimitar várias eVars de comercialização com um pipe (`|`). Consulte eVars [de comercialização](../../../components/c-variables/c-merch-variables/var-merchandising.md) para obter mais informações.

```js
// Set a single product using all available fields
s.products = "Example category;Example product;1;3.50;event1=4.99|event2=5.99;eVar1=Example merchandising value 1|eVar2=Example merchandising value 2";
```

Essa variável suporta vários produtos na mesma ocorrência. Ele é valioso para carrinhos de compras e compras que contêm vários produtos. Embora haja um limite de 100 bytes por produto, o comprimento total da `products` variável é 64 K. Separe cada produto com uma vírgula (`,`) na string.

```js
// Set multiple products - useful for when a visitor views their shopping cart
s.products = "Example category 1;Example product 1;1;3.50,Example category 2;Example product 2,1,5.99";
```

> [!IMPORTANT] Retire todos os pontos-e-vírgulas, vírgulas e tubulações dos nomes de produtos, categorias e valores de eVar de comercialização. Se o nome de um produto incluir uma vírgula, o AppMeasurement a analisa como o início de um novo produto. Essa análise incorreta descarta o restante da string do produto, causando dados incorretos em dimensões e relatórios.

## Exemplos

A `products` variável é flexível ao omitir campos e incluir vários produtos. Essa flexibilidade pode facilitar a perda de um delimitador, o que faz com que sua implementação envie dados incorretos para a Adobe.

```js
// Include only product and category. Common on individual product pages
s.products = "Example category;Example product";

// Include only product name if you do not want to use product category
s.products = ";Example product";

// One product has a category, the other does not. Note the comma and adjacent semicolon to omit category
s.products = "Example category;Example product,;Example product";

// A visitor purchases a single product; record quantity and price
s.events = "purchase";
s.products = "Example category;Example product;1;6.99";

// A visitor purchases multiple products with different quantities
s.events = "purchase";
s.products = "Example category;Example product 1;9;26.91,Example category;Example product 2;4;9.96";

// Attribute currency event1 only to product 2 and not product 1
s.events = "event1";
s.products = "Example category 1;Example product 1;1;1.99,Example category 2;Example product 2;1;2.69;event1=1.29";

// Use multiple numeric events in the product string
s.events = "event1,event2";
s.products = "Example category;Example product;1;4.20;event1=2.3|event2=5";

// Use merchandising eVars without any events. Note the adjacent semicolons to skip events
s.products = "Example category;Example product;1;6.69;;eVar1=Merchandising value";

// Use merchandising eVars without category, quantity, price, or events
s.products = ";Example product;;;;eVar1=Merchandising value";

// Multiple products using multiple different events and multiple different merchandising eVars
s.events = "event1,event2,event3,event4,purchase";
s.products = "Example category 1;Example product 1;3;12.60;event1=1.4|event2=9;eVar1=Merchandising value|eVar2=Another merchandising value,Example category 2;Example product 2;1;59.99;event3=6.99|event4=1;eVar3=Merchandising value 3|eVar4=Example value four";
```
