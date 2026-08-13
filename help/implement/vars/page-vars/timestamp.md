---
title: carimbo de data e hora
description: Defina manualmente o carimbo de data e hora da ocorrência.
feature: Appmeasurement Implementation
exl-id: 9d5ce5ef-2d84-4f65-b2e3-7aa3e219bc34
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/f2r9jWtF5HgCP6jUKg3YnLFxNwx1DiUBI-2Nquy5-K0'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 1ed4ab984231b7c72580c5ae505b1a16c0330c2f
workflow-type: tm+mt
source-wordcount: 304
ht-degree: 67%

---

# carimbo de data e hora

A variável `timestamp` define manualmente o carimbo de data e hora da ocorrência para conjuntos de relatórios com carimbo de data e hora habilitado.

>[!WARNING]
>
>Não use essa variável se o conjunto de relatórios não estiver configurado explicitamente para aceitar ocorrências com carimbo de data e hora. O AppMeasurement define automaticamente a hora de uma ocorrência para conjuntos de relatórios que não suportam ocorrências com carimbo de data e hora. Se você enviar uma ocorrência com essa variável para um conjunto de relatórios não compatível com carimbos de data e hora, esses dados serão perdidos permanentemente.

## Carimbo de data e hora usando o Web SDK

O carimbo de data/hora é [mapeado para o Adobe Analytics](/help/implement/aep-edge/xdm-var-mapping.md) no campo XDM `xdm.timestamp`. Esse campo só oferece suporte a horário Unix.

## Carimbo de data e hora usando a extensão do Adobe Analytics

Não há um campo dedicado na extensão do Adobe Analytics para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.timestamp no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.timestamp` é uma string que contém a data e a hora da ocorrência. Os formatos válidos de carimbo de data/hora incluem [ISO 8601](https://datatracker.ietf.org/doc/html/rfc3339#section-5.6) e [Unix time](https://pt.wikipedia.org/wiki/Era_Unix) em segundos.

```js
// Timestamp using ISO 8601
s.timestamp = "2026-01-01T00:00:00Z";

// Timestamp using Unix timestamp
s.timestamp = "1577836800";

// Automatically get the current Unix timestamp
s.timestamp = Math.round(new Date().getTime()/1000);

// Automatically get the current ISO 8601 timestamp
s.timestamp = new Date().toISOString();
```

## Valores em ISO 8601

As datas e horas expressas em [ISO 8601](https://datatracker.ietf.org/doc/html/rfc3339#section-5.6) podem assumir várias formas diferentes. A Adobe não é compatível com todos os recursos do ISO 8601.

* A data e a hora devem ser fornecidas, separadas por `T`.
* São necessárias horas e minutos; segundos são opcionais, porém recomendados.
* Não há suporte para datas semanais e datas ordinais.
* A data pode estar no formato padrão ou estendido. Por exemplo, `2026-01-01T00:00:00Z` e `20260101T000000Z` são válidos.
* Minutos e segundos fracionais são tecnicamente válidos, mas as frações são ignoradas. O Adobe Analytics oferece suporte a carimbos de data e hora somente com precisão de segundo nível. Se a precisão de nível de milissegundo for uma prioridade para sua organização, considere usar o Customer Journey Analytics.
* Fusos horários são suportados em formatos padrão e estendidos.

A seguir estão exemplos válidos de valores ISO 8601 na variável `timestamp`:

```text
2026-01-01T00:00:00+00:00
2026-01-01T00:00:00Z
2026-01-01T00:00:00
2026-01-01T00:00
20260101T000000+0000
20260101T000000Z
20260101T000000
20260101T0000
```
