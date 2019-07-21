---
description: A variável products é usada para rastrear produtos e categorias de produto (assim como quantidade e preço da compra).
keywords: Implementação do Analytics; variável products; exibição do produto; evento bem-sucedido
seo-description: A variável products é usada para rastrear produtos e categorias de produto (assim como quantidade e preço da compra).
seo-title: Página detalhada de visualização do produto
solution: Analytics
title: Página detalhada de visualização do produto
topic: Desenvolvedor e implementação
uuid: 464 c 9 daf-b 042-4 fb 8-8 ca 6-e 104 c 0 bcef 45
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Página detalhada de visualização do produto

A variável products é usada para rastrear produtos e categorias de produto (assim como quantidade e preço da compra).

A success event should always be set in conjunction with the *`products`* variable.

```js
s.events="prodView"
```

>[!NOTE]
>
>While *`prodView`* is treated in implementation like an event, it does not have the same flexibility in the interface. The *`prodView`*event is an instance of the product and is only available in the *`products`* report. Adobe recommends you use a *`custom`* event in addition to the *`prodView`* event. Dessa forma, você poderá ver as métricas de exibição do produto juntamente com outras métricas em outros relatórios de conversão.

```js
s.products=";diamond earrings (54321)"
```

>[!NOTE]
>
>A sintaxe de string products deve começar com um ponto-e-vírgula. Esse é um requisito legado da sintaxe. Ele era usado previamente para delimitar a categoria e o produto, mas isso cria uma limitação dentro da interface, caso você queira alterar a forma de classificação dos produtos. Para ter flexibilidade máxima na criação de relatórios, é melhor deixar em branco e usar Classificações para configurar categorias.

## Shopping Cart Page (scOpen, scAdd, scRemove ) {#section_469B64F4150149DFB6B2C731279C0BC7}

```js
s.events="scOpen,scAdd" 
s.products=";SKU" 
```

## Primeira página de checkout {#section_E15607A9AECB44F79631926C853CF64E}

```js
s.events="scCheckout" 
s.products=”;SKU" 
```

## Página de confirmação {#section_E006943CD5FD42358086581CA44B9660}

```js
s.events="purchase" 
s.products=";SKU" 
```

>[!NOTE]
>
>While using the SKU in the product string may make the *`products`* report less readable, it provides the maximum flexibility later when you want to classify your products. Você pode criar categorias do SKU que indicam finalização, fabricante, categoria e subcategoria.

Quando a variável *`products`* for definida juntamente com o evento *`purchase`, a quantidade de compra e o preço total da compra serão incluídos no valor dos produtos, como mostrado acima.*
