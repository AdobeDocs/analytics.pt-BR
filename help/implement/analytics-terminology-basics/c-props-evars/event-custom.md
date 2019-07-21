---
description: Os eventos predefinidos permitem definir o tipo de sucesso que você quer rastrear.
keywords: Implementação do Analytics; Evento personalizado
seo-description: Os eventos predefinidos permitem definir o tipo de sucesso que você quer rastrear.
seo-title: O que é um evento personalizado?
solution: Analytics
title: O que é um evento personalizado?
topic: Desenvolvedor e implementação
uuid: 8 e 78 ba 04-9 b 4 c -4566-980 c-c 24 dd 9 d 82d 82
translation-type: tm+mt
source-git-commit: d7056c233e784a073c75c55f396ff43c9e0d1c71

---


# O que é um evento personalizado?

Os eventos predefinidos permitem definir o tipo de sucesso que você quer rastrear.

Embora semelhantes aos eventos [!UICONTROL predefinidos], os eventos [!UICONTROL personalizados] permitem definir sua própria métrica de sucesso. For example, if you have a newsletter, your success event could be _Registration_. Clearly, _Registration_ is not part of the [!UICONTROL predefined] events. Usando um evento [!UICONTROL personalizado], você pode rastrear o número de visitantes que se registram no seu boletim informativo. Os Eventos [!UICONTROL personalizados] seguem a sintaxe padrão mostrada abaixo.

```js
s.events="event3"
```

O código acima mostra como atribuir um evento à variável _variável_ de eventos. If you do not modify the event name in the interface, _event3_ would display in the interface.

Por padrão, os eventos bem-sucedidos são configurados como eventos _contadores_. Eventos contadores contam o número de vezes que um evento bem-sucedido foi definido. Alguns eventos bem-sucedidos exigem que um evento seja incrementado por um valor personalizado. These events can be set either as _numeric_ events or _currency_ events. É possível alterar o tipo de evento no Console de administração.
