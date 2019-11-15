---
description: Descreve como ativar e implementar uma variável de comercialização.
keywords: Analytics Implementation;merchandising;variable;product syntax;Conversion Variable Syntax;s.products
solution: Analytics
title: Implementar uma variável de merchandising
topic: Developer and implementation
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Implementar uma variável de merchandising

Descreve como ativar e implementar uma variável de comercialização.

## Ativar uma variável de comercialização

A comercialização pode ser ativada para qualquer eVar personalizada em Ferramentas **** administrativas &gt; Conjuntos **** de relatórios &gt; Variáveis **[!UICONTROL de]** conversão.

![](assets/merch-enable.png)

| Configuração | Descrição |
|--- |--- |
| Expirar após | Determina por quanto tempo os valores de comercialização devem persistir. |
| Comercialização | **** Sintaxe do produto: O valor é definido em `s.products`.<br>**** Sintaxe da variável de conversão: O valor é definido na eVar de comercialização designada. |
| Evento de vinculação de comercialização (somente sintaxe de variável de conversão) | Indica quando um produto deve ser vinculado à categoria de comercialização atual. Vários eventos podem ser selecionados mantendo a tecla Ctrl pressionada e clicando em vários itens na lista. Você pode selecionar um evento somente quando a "Sintaxe de variável de conversão" é selecionada. |

## Como implementar usando a sintaxe de produto

Quando a Sintaxe de produto está ativada, a categoria de comercialização é preenchida diretamente na variável de produtos, portanto, não é necessário selecionar e configurar um evento de vinculação. Este é o método recomendado e deve ser utilizado, salvo quando o valor não está disponível para definição em `s.products` quando o evento bem-sucedido ocorre.

### Sintaxe

```js
s.products="category;product;quantity;price;event_incrementer;eVarN=merch_category|eVarM=merch_category2";
```

### Exemplo

```js
s.events="prodView";
s.products=";Snow Goggles;;;;eVar1=goggles";
```

O valor "óculos" para eVar1 é atribuído ao produto "Óculos de neve". Todos os eventos subsequentes bem-sucedidos (anúncios de produtos, check-outs, compras e assim por diante) que envolvem este produto são creditados a "óculos".

## Como implementar usando uma sintaxe de variável de conversão

A Sintaxe de variável de conversão deve ser usada quando o valor da eVar não está disponível para definição em `s.products`. Normalmente, isso significa que sua página não tem o contexto do canal de comercialização ou método de pesquisa. Nesses casos, você deve definir a variável de comercialização antes de chegar na página do produto e o valor persiste até o evento de vinculação ocorrer.

Quando o evento de vinculação selecionado durante a configuração ocorre, o valor persistido da eVar está associado ao produto. Por exemplo, se prodView é especificado como o evento de vinculação, a categoria de comercialização está vinculada à lista de produtos atual somente quando o evento ocorre. Somente eventos de vinculação subsequentes podem atualizar uma eVar de comercialização já atribuída a um produto.

### Sintaxe

Coloque na mesma página ou na página anterior antes do evento de vinculação:

```js
s.eVar1="merchandising_category";
```

Local na página onde o evento de vinculação ocorre:

```js
s.events="prodView";
s.products="category;product";
```

### Exemplo

Na página 1 da visita:

```js
s.eVar1="Outdoors"
```

Na página 2 da visita:

```js
s.events="prodView";
s.products=";Snow Goggles";
```

O valor "Externo" para eVar1 é atribuído ao produto "Óculos de neve". Todos os eventos bem-sucedidos subsequentes (anúncios de produto, finalizações, compras e assim por diante) que envolvem este produto são creditados em "Óculos de neve". Além disso, o valor atual da variável de comercialização está vinculado a todos os produtos subsequentes até que uma destas condições seja atendida:

* eVar expira (com base na configuração "Expirar após")
* A eVar de comercialização é substituída por um novo valor.

## Informações adicionais externas

[Comercialização](https://analyticsdemystified.com/adobe-analytics/advanced-conversion-syntax-merchandising/) de sintaxe de conversão avançada em [!DNL analyticsdemystified.com]
