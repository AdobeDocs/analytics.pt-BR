---
title: forceOnline
description: Defina manualmente o estado online do AppMeasurement.
feature: Variables
exl-id: 318408bf-bec6-49aa-a762-9d2eebab233e
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 80%

---

# forceOnline

O método `forceOnline()` permite substituir o estado do AppMeasurement detectado automaticamente.

>[!WARNING]
>
>Use esse método somente quando a [`trackOffline`](../config-vars/trackoffline.md) estiver ativada. Usar essa função fora do rastreamento offline pode causar perda de dados.

O AppMeasurement detecta automaticamente o estado online do dispositivo. Você pode usar o método `forceOnline()` para forçar o AppMeasurement a tratar ocorrências como se o dispositivo estivesse online. Esse método não aceita argumentos e não retorna nenhum valor. Seu único objetivo é substituir o estado online no AppMeasurement.

## Forçar o uso online do SDK da Web

O SDK da Web não oferece suporte ao rastreamento offline.

## Forçar o uso online da extensão do Adobe Analytics

Não há um campo dedicado na extensão do Adobe Analytics para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.forceOnline() no AppMeasurement e no editor de código personalizado da extensão do Analytics

Você pode chamar o método `s.forceOnline()` em qualquer lugar na sua implementação depois de instanciar o objeto do Analytics.

```js
s.forceOnline();
```
