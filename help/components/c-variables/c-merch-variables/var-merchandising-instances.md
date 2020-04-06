---
description: Descreve como as instâncias são contadas em variáveis de comercialização.
keywords: Analytics Implementation
title: Instâncias em variáveis de merchandising
topic: Developer and implementation
uuid: 4cdfd53e-88aa-48cf-a135-98f7fc8dcece
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Instâncias em variáveis de merchandising

Descreve como as instâncias são contadas em variáveis de comercialização.

No momento, as instâncias não são compatíveis com variáveis de comercialização. Se você notar instâncias em um relatório que contém uma variável de comercialização, isso indica que a eVar está sendo definida em alguns locais fora da string de produtos e não deve ser considerada uma contagem verdadeira de instâncias para a variável de comercialização selecionada.

Se você estiver usando a Sintaxe de variável de conversão, uma instância será contada sempre que a variável for definida. No entanto, a instância é atribuída a &quot;Nenhum&quot;, a menos que o seguinte ocorra sempre que a variável for definida:

* Um evento de vínculo está definido.
* A variável products está definida.
* A eVar de comercialização tem um valor.

Por exemplo, a seguinte instância da eVar1 está alocada para &quot;Exterior:Óculos de Esqui&quot;:

```js
s.eVar1="Outdoors:Ski Goggles" 
s.events="prodView" 
s.products=";Fernie Snow Goggles"
```

No entanto, no próximo exemplo, a instância da eVar1 é alocada como &quot;Nenhum&quot;, pois todas as condições não são atendidas quando a eVar é definida (não há evento de vínculo e a variável products não está definida):

Página 1 da visita:

```js
s.eVar1="Outdoors:Ski Goggles"
```

Página 2 da visita:

```js
s.events="prodView" 
s.products=";Fernie Snow Goggles"
```

A alocação para &quot;Nenhum&quot; ocorre se você definir um valor para uma eVar em uma página onde nenhum evento de vínculo ocorre, ou se você definir o valor da eVar na sequência de produtos sem um evento de vínculo.

>[!NOTE] A funcionalidade atual para contar instâncias em variáveis de merchandising está sendo analisada e deve mudar em uma versão futura.

