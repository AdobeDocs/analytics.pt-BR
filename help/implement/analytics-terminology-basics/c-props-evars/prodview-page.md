---
description: A variável products é usada para rastrear produtos e categorias de produto (assim como quantidade e preço da compra).
keywords: Analytics Implementation;products variable;product view;success event
title: Página de exibição detalhada do produto
topic: Developer and implementation
uuid: 464c9daf-b042-4fb8-8ca6-e104c0bcef45
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Página de exibição detalhada do produto

A variável products é usada para rastrear produtos e categorias de produto (assim como quantidade e preço da compra).

Um evento bem-sucedido deve sempre ser definido juntamente com a variável *`products`*.

```js
s.events="prodView"
```

> [!NOTE]Embora, *`prodView`* seja tratado na implementação como um evento, ele não tem a mesma flexibilidade na interface. O evento *`prodView`* é uma instância do produto e só fica disponível no relatório de *`products`*. A Adobe recomenda usar um evento *`custom`*, além do evento *`prodView`*. Dessa forma, você poderá ver as métricas de exibição do produto juntamente com outras métricas em outros relatórios de conversão.

```js
s.products=";diamond earrings (54321)"
```

> [!NOTE]A sintaxe da string de produtos deve começar com um ponto e vírgula. Esse é um requisito legado da sintaxe. Ele era usado previamente para delimitar a categoria e o produto, mas isso cria uma limitação dentro da interface, caso você queira alterar a forma de classificação dos produtos. Para ter flexibilidade máxima na criação de relatórios, é melhor deixar em branco e usar Classificações para configurar categorias.

## Shopping Cart Page (scOpen, scAdd, scRemove ) {#section_469B64F4150149DFB6B2C731279C0BC7}

```js
s.events="scOpen,scAdd"
s.products=";SKU"
```

## Primeira página de checkout {#section_E15607A9AECB44F79631926C853CF64E}

```js
s.events="scCheckout"
s.products=";SKU"
```

## Página de confirmação {#section_E006943CD5FD42358086581CA44B9660}

```js
s.events="purchase"
s.products=";SKU"
```

> [!NOTE]Embora o uso do SKU na string do produto possa tornar o *`products`* relatório menos legível, ele fornece a flexibilidade máxima posteriormente quando você deseja classificar os produtos. Você pode criar categorias do SKU que indicam finalização, fabricante, categoria e subcategoria.

Quando a variável *`products`* for definida juntamente com o evento *`purchase`*, a quantidade de compra e o preço total da compra serão incluídos no valor dos produtos, como mostrado acima.
