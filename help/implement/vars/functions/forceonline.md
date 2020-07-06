---
title: forceOnline
description: Defina manualmente o estado online do AppMeasurement.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 100%

---


# forceOnline

O método `forceOnline()` permite substituir o estado do AppMeasurement detectado automaticamente.

>[!IMPORTANT]
>
>Use esse método somente quando a [`trackOffline`](../config-vars/trackoffline.md) estiver ativada. Usar essa função fora do rastreamento offline pode causar perda de dados.

O AppMeasurement detecta automaticamente o estado online do dispositivo. Você pode usar o método `forceOnline()` para forçar o AppMeasurement a tratar ocorrências como se o dispositivo estivesse online. Esse método não aceita argumentos e não retorna nenhum valor. Seu único objetivo é substituir o estado online no AppMeasurement.

## Forçar rastreamento online no Adobe Experience Platform Launch

Não há um campo dedicado no Launch para usar essa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.forceOnline() no AppMeasurement e no editor de código personalizado do Launch

Você pode chamar o método `s.forceOnline()` em qualquer lugar na sua implementação depois de instanciar o objeto do Analytics.

```js
s.forceOnline();
```
