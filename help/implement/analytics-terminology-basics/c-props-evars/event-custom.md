---
description: Os eventos predefinidos permitem definir o tipo de sucesso que você quer rastrear.
keywords: Analytics Implementation;custom event
solution: Analytics
title: O que é um evento personalizado?
topic: Developer and implementation
uuid: 8e78ba04-9b4c-4566-980c-c24dd9d82236
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# O que é um evento personalizado?

Os eventos predefinidos permitem definir o tipo de sucesso que você quer rastrear.

Embora semelhantes aos eventos [!UICONTROL predefinidos], os eventos [!UICONTROL personalizados] permitem definir sua própria métrica de sucesso. Por exemplo, se você tiver um informativo, seu evento bem-sucedido pode ser _Registro_. Claramente, o _Registro_ não faz parte dos eventos [!UICONTROL predefinidos]. Usando um evento [!UICONTROL personalizado], você pode rastrear o número de visitantes que se registram no seu boletim informativo. Os Eventos [!UICONTROL personalizados] seguem a sintaxe padrão mostrada abaixo.

```js
s.events="event3"
```

O código acima mostra como atribuir um evento à variável Variável de _eventos_. Se você não modificar o nome do evento na interface, _event3_ será exibido na interface.

Por padrão, os eventos bem-sucedidos são configurados como eventos _contadores_. Eventos contadores contam o número de vezes que um evento bem-sucedido foi definido. Alguns eventos bem-sucedidos exigem que um evento seja incrementado por um valor personalizado. Esses eventos podem ser definidos como _numéricos_ ou de _moeda_. Você pode alterar o tipo de evento no Admin Console.
