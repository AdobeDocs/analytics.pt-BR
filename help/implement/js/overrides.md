---
title: Substituições de variável
description: As substituições de variáveis permitem alterar um valor de variável por um único rastreamento ou chamada de link de rastreamento.
translation-type: tm+mt
source-git-commit: 1f0fd2dcb0454ad9bc2e0c2141b5e17470c6a5de

---


# Substituições de variável

As substituições de variáveis permitem alterar os valores do Analytics para uma única ocorrência sem afetar as variáveis existentes na página.

## Fluxo de trabalho

1. Crie um novo objeto JavaScript. O nome do objeto pode ser qualquer coisa que você desejar.

   ```js
   var y = new Object();
   ```

2. Atribua propriedades válidas do Analytics a este objeto:

   ```js
   y.eVar1 = "New value";
   y.events = "event2";
   ```

3. Use o objeto como um argumento na chamada de rastreamento apropriada:

   ```js
   // Use the override object in a standard page view call
   s.t(y);
   
   // Use the override object in a link tracking call
   s.tl(this,'o','Example override link',y);
   ```

Quando uma chamada de rastreamento recebe um objeto no parâmetro overrides, todos os valores válidos no objeto override substituem os valores no objeto padrão do Analytics. As variáveis já definidas no objeto existente do Analytics não são afetadas.
