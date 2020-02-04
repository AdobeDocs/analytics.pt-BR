---
title: timestamp
description: Defina manualmente o carimbo de data e hora da ocorrência.
translation-type: tm+mt
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# timestamp

A `timestamp` variável define manualmente o carimbo de data e hora da ocorrência para conjuntos de relatórios com carimbo de data e hora ativado.

> [!WARNING] Não use essa variável se o conjunto de relatórios não estiver configurado explicitamente para aceitar ocorrências com carimbos de data e hora. O AppMeasurement define automaticamente a hora de uma ocorrência para conjuntos de relatórios que não suportam ocorrências com carimbo de data e hora. Se você enviar uma ocorrência com essa variável para um conjunto de relatórios que não suporta carimbos de data e hora, esses dados serão perdidos permanentemente.

## Carimbo de data e hora no Adobe Experience Platform Launch

Não há um campo dedicado no Launch para usar essa variável. Use o editor de código personalizado, após a sintaxe do AppMeasurement.

## s.timestamp no AppMeasurement e no editor de código personalizado Iniciar

A `s.timestamp` variável é uma string que contém a data e a hora da ocorrência. Os formatos válidos de carimbo de data e hora incluem [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) e hora [](https://en.wikipedia.org/wiki/Unix_time)Unix.

```js
// Timestamp using ISO 8601
s.timestamp = "2020-01-01T00:00:00Z";

// Timestamp using Unix timestamp
s.timestamp = "1577836800";

// Automatically get the current Unix timestamp
s.timestamp = Math.round(new Date().getTime()/1000);

// Automatically get the current ISO 8601 timestamp
s.timestamp = new Date().toISOString();
```

## Valores ISO 8601

As datas e horas expressas em [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) podem assumir várias formas diferentes. A Adobe não é compatível com todos os recursos do ISO 8601.

* Both the date and time must be provided, separated by `T`.
* São necessárias horas e minutos; segundos são opcionais, mas são recomendados.
* Não há suporte para datas semanais e datas ordinais.
* A data pode estar no formato padrão ou estendido.  Por exemplo, `2020-01-01T00:00:00Z` e ambos `20200101T000000Z` são válidos.
* Minutos e segundos fracionais são tecnicamente válidos, mas as frações são ignoradas pela Adobe.
* Os fusos horários são suportados em formatos padrão e estendidos.

A seguir estão exemplos válidos de valores ISO 8601 na `timestamp` variável:

```text
2020-01-01T00:00:00+00:00
2020-01-01T00:00:00Z
2020-01-01T00:00:00
2020-01-01T00:00
20200101T000000+0000
20200101T000000Z
20200101T000000
20200101T0000
```
