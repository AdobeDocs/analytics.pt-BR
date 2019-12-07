---
description: Descreve como as instâncias são contadas em variáveis de comercialização.
keywords: Analytics Implementation
title: Instâncias em variáveis de merchandising
topic: Developer and implementation
uuid: 4cdfd53e-88aa-48cf-a135-98f7fc8dcece
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Instâncias em variáveis de merchandising

Descreve como as instâncias são contadas em variáveis de comercialização.

No momento, as instâncias não são compatíveis com variáveis de merchandising. Se você encontrar instâncias em um relatório contendo uma variável de merchandising, é porque a eVar está sendo definida em locais externos à cadeia de caracteres do produto e não deve ser considerada como uma contagem verdadeira das instâncias da variável de merchandising selecionada.

Se você usa a Sintaxe de variável de conversão, uma instância é contada sempre que a variável é definida. No entanto, a instância é atribuída como "Nenhum", salvo quando o seguinte ocorre sempre que a variável é definida:

* Um evento de vinculação está configurado.
* A variável de produtos está configurada.
* A eVar de comercialização tem um valor.

Por exemplo, a seguinte instância da eVar1 está alocada para "Exterior:Óculos de ski":

```js
s.eVar1="Outdoors:Ski Goggles" 
s.events="prodView" 
s.products=";Fernie Snow Goggles"
```

No entanto, no próximo exemplo, a instância da eVar1 está alocada como "Nenhum", pois todas as condições não são atendidas quando a eVar é definida (não há evento de vinculação e a variável de produtos não está configurada):

Página 1 da visita:

```js
s.eVar1="Outdoors:Ski Goggles"
```

Página 2 da visita:

```js
s.events="prodView" 
s.products=";Fernie Snow Goggles"
```

A alocação para "Nenhum" ocorre se você define um valor para uma eVar em uma página na qual nenhum evento de vinculação ocorre, ou se você define o valor da eVar na sequência de produtos sem um evento de vinculação.

> [!NOTE] A funcionalidade atual para contar instâncias em variáveis de merchandising está sendo analisada e deve mudar em uma versão futura.

