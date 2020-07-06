---
title: eVar (merchandising)
description: Variáveis personalizadas que se vinculam a produtos individuais.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 29%

---


# eVar (merchandising)

*Esta página de ajuda descreve como implementar eVars de comercialização. For information on how merchandising eVars work as a dimension, see[eVars (Merchandising)](/help/components/dimensions/evar-merchandising.md)in the Components user guide.*

## Configurar eVars nas configurações do conjunto de relatórios

Antes de usar eVars na implementação, certifique-se de configurar a eVar para a sintaxe desejada nas configurações do conjunto de relatórios. Consulte [Variáveis de conversão](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) no Guia de administração.

>[!IMPORTANT]
>
>Falha ao configurar corretamente eVars de comercialização resulta em valores inesperados ou perda de dados para a variável. Verifique se ele está configurado corretamente para sua implementação.

## Implementar usando a sintaxe do produto

When &#39;Product Syntax&#39; is enabled, the merchandising category is populated directly within the `products` variable, so selecting and setting a binding event is not required. Este é o método recomendado e deve ser utilizado, salvo quando o valor não está disponível para definição em `products` quando o evento bem-sucedido ocorre.

```js
// The bare minimum to set a merchandising eVar with product syntax
s.products = ";Example product;;;;eVar1=Example merchandising value";

// An example single product with product syntax
s.products = "Example category;Example product;1;5.99;event1=1;eVar1=Turtles";

// Tie a merchandising eVar to a different values on two different products
s.products = "Birds;Scarlet Macaw;1;4200;;eVar1=talking bird,Birds;Turtle dove;2;550;;eVar1=love birds";
```

The value for `eVar1` is assigned to the product. Todos os eventos bem-sucedidos subsequentes que envolvem este produto são creditados no valor da eVar.

## Implementar usando a sintaxe da variável de conversão

Conversion Variable Syntax is used when the eVar value is not available to set in the `products` variable. Normalmente, esse cenário significa que sua página não tem o contexto do canal de comercialização ou do método de localização. Nesses casos, você define a variável de comercialização antes de chegar à página do produto e o valor persiste até que o evento de vinculação ocorra.

Quando o evento de vinculação selecionado durante a configuração ocorre, o valor persistido da eVar está associado ao produto. For example, if `prodView` is specified as the binding event, the merchandising category is tied to the current product list only at the time the event occurs. Somente eventos de vinculação subsequentes podem atualizar uma eVar de comercialização já atribuída a um produto.

```js
// Place on the same or previous page before the binding event:
s.eVar1 = "Aviary";

// Place on the page where the binding event occurs:
s.events = "prodView";
s.products = "Birds;Canary";
```

The value `"Aviary"` for `eVar1` is assigned to the product `"Canary"`. Todos os eventos bem-sucedidos subsequentes que envolvem este produto são creditados a `"Canary"`. Além disso, o valor atual da variável de comercialização está vinculado a todos os produtos subsequentes até que uma destas condições seja atendida:

* A eVar expira (com base na configuração &quot;Expirar após&quot;)
* A eVar de comercialização é substituída por um novo valor.
