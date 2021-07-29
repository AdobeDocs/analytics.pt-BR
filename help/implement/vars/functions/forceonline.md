---
title: forceOnline
description: Defina manualmente o estado online do AppMeasurement.
exl-id: 318408bf-bec6-49aa-a762-9d2eebab233e
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 83%

---

# forceOnline

O método `forceOnline()` permite substituir o estado do AppMeasurement detectado automaticamente.

>[!IMPORTANT]
>
>Use esse método somente quando a [`trackOffline`](../config-vars/trackoffline.md) estiver ativada. Usar essa função fora do rastreamento offline pode causar perda de dados.

O AppMeasurement detecta automaticamente o estado online do dispositivo. Você pode usar o método `forceOnline()` para forçar o AppMeasurement a tratar ocorrências como se o dispositivo estivesse online. Esse método não aceita argumentos e não retorna nenhum valor. Seu único objetivo é substituir o estado online no AppMeasurement.

## Forçar o uso online de tags no Adobe Experience Platform

Não há um campo dedicado na interface do usuário da coleta de dados para usar essa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.forceOnline() no AppMeasurement e no editor de código personalizado do 

Você pode chamar o método `s.forceOnline()` em qualquer lugar na sua implementação depois de instanciar o objeto do Analytics.

```js
s.forceOnline();
```
