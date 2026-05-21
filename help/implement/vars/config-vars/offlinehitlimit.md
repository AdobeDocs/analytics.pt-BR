---
title: offlineHitLimit
description: Determine o número máximo de ocorrências a serem colocadas em fila para rastreamento offline.
feature: Appmeasurement Implementation
exl-id: de6478b3-b95f-4edc-8427-7b915a46b3ba
role: Admin, Developer
TQID: https://experienceleague.adobe.com/-uvCAqUO0A-7XjlemN4XwHXVG9DFK-UoVTW77up9-AY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 194
ht-degree: 39%

---

# offlineHitLimit

O rastreamento offline é uma maneira opcional de coletar dados no Adobe Analytics. Se um visitante se desconectar da Internet, mas continuar a navegar em seu site, as ocorrências serão armazenadas em uma fila offline até que o dispositivo se reconecte à Internet. O rastreamento offline é usado principalmente para aplicativos móveis.

A variável `offlineHitLimit` coloca um limite no número de ocorrências que o dispositivo armazena localmente. Essa variável só funciona se o [`trackOffline`](trackoffline.md) estiver habilitado.

## Limite de ocorrências offline usando o Web SDK

O Web SDK não oferece suporte ao rastreamento offline.

## Limite de ocorrências offline usando a extensão do Adobe Analytics

Não há um campo dedicado na extensão do Adobe Analytics para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.offlineHitLimit no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.offlineHitLimit` é um número inteiro que representa o número máximo de ocorrências que um dispositivo armazena enquanto está offline. Se essa variável não estiver definida, o padrão será `10`. Você pode defini-lo como qualquer valor inteiro. Ao definir valores altos, lembre-se dos limites de armazenamento local no navegador do visitante. Normalmente, esse limite é de 5 a 10 MB.

```js
s.offlineHitLimit = 100;
```
