---
title: Tempo antes do evento
description: A quantidade de tempo entre a métrica e a primeira ocorrência da visita.
translation-type: tm+mt
source-git-commit: 1869d69566d26aa7d99c520efc2e835901439d48
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 0%

---


# Tempo antes do evento

A dimensão &#39;Tempo anterior ao evento&#39; relata a quantidade de tempo decorrido entre a primeira ocorrência da visita e a métrica desejada. Essa dimensão é útil para determinar a quantidade de tempo necessário para atingir um evento bem-sucedido, como um envio de formulário ou uma compra.

## Preencher esta dimensão com dados

Embora tecnicamente esta dimensão funcione de forma imediata para todas as implementações, funciona melhor com eventos personalizados e de compra. A Adobe recomenda implementar eventos personalizados em seu site. Se você implementar eventos personalizados, nenhuma implementação adicional será necessária para essa dimensão.

## Valores de dimensão

Os valores de dimensão incluem compartimentos baseados em tempo que variam de `"Less than 1 minute"` a `"More than 15 hours"`. Por exemplo, se levasse um visitante de 23 minutos da primeira ocorrência para uma compra, ela pertenceria abaixo do valor da `"10 to 30 minutes"` dimensão.
