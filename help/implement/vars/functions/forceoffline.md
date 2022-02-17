---
title: forceOffline
description: Defina manualmente o estado online do AppMeasurement.
feature: Variables
exl-id: 2e48bdf6-7de7-4976-86dd-ef3d558769c7
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 100%

---

# forceOffline

O método `forceOffline()` permite substituir o estado do AppMeasurement detectado automaticamente.

>[!IMPORTANT]
>
>Use essa função somente quando [`trackOffline`](../config-vars/trackoffline.md) estiver ativada. Usar essa função fora do rastreamento offline pode causar perda de dados.

O AppMeasurement detecta automaticamente o estado online do dispositivo. Você pode usar o método `forceOffline()` para forçar o AppMeasurement a tratar ocorrências como se o dispositivo estivesse offline. Esse método não aceita argumentos e não retorna nenhum valor. Seu único objetivo é substituir o estado online no AppMeasurement.

## Forçar o uso offline de tags na Adobe Experience Platform

Não há um campo dedicado na interface da Coleção de dados para usar essa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.forceOffline() no AppMeasurement e no editor de código personalizado do 

Você pode chamar o método `s.forceOffline()` em qualquer lugar na sua implementação depois de instanciar o objeto do Analytics.

```js
s.forceOffline();
```
