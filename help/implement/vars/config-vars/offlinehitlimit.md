---
title: offlineHitLimit
description: Determine o número máximo de ocorrências a serem colocadas em fila para rastreamento offline.
feature: Variables
exl-id: de6478b3-b95f-4edc-8427-7b915a46b3ba
role: Admin, Developer
source-git-commit: 8bc5e649c5b5852232f4baddcddad0766bc1569a
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 39%

---

# offlineHitLimit

O rastreamento offline é uma maneira opcional de coletar dados no Adobe Analytics. Se um visitante se desconectar da Internet, mas continuar a navegar em seu site, as ocorrências serão armazenadas em uma fila offline até que o dispositivo se reconecte à Internet. O rastreamento offline é usado principalmente para aplicativos móveis.

A variável `offlineHitLimit` coloca um limite no número de ocorrências que o dispositivo armazena localmente. Essa variável só funciona se o [`trackOffline`](trackoffline.md) estiver ativado.

## Limite de ocorrências offline usando o SDK da Web

O SDK da Web não oferece suporte ao rastreamento offline.

## Limite de ocorrências offline usando a extensão do Adobe Analytics

Não há um campo dedicado na extensão do Adobe Analytics para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.offlineHitLimit no AppMeasurement e o editor de código personalizado da extensão do Analytics

A variável `s.offlineHitLimit` é um número inteiro que representa o número máximo de ocorrências que um dispositivo armazena enquanto está offline. Se essa variável não estiver definida, o padrão será `10`. Você pode defini-lo como qualquer valor inteiro. Ao definir valores altos, lembre-se dos limites de armazenamento local no navegador do visitante. Normalmente, esse limite é de 5 a 10 MB.

```js
s.offlineHitLimit = 100;
```
