---
title: Substituições de variável
description: As substituições de variáveis permitem alterar um valor de variável por um único rastreamento ou chamada de link de rastreamento.
feature: Implementation Basics
exl-id: e297ef94-c5f7-42b1-a9d0-57e073f0d1a9
role: Developer
TQID: 'https://experienceleague.adobe.com/IVA-JMaZPrKpF1NhhL6o3uiCQOOCtZerk78aQTqJAyc'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 106
ht-degree: 100%

---

# Substituições de variável

As substituições de variáveis permitem alterar os valores do Analytics para uma única ocorrência, sem afetar as variáveis existentes na página.

## Fluxo de trabalho

1. Crie um novo objeto JavaScript. O nome do objeto pode ser o que você desejar.

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
