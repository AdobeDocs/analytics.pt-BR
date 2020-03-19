---
title: forceOffline
description: Defina manualmente o estado online do AppMeasurement.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# forceOffline

O `forceOffline()` método permite substituir o estado detectado automaticamente do AppMeasurement.

> [!IMPORTANT] Use essa função somente quando [`trackOffline`](../config-vars/trackoffline.md) estiver ativada. Usar essa função fora do rastreamento offline pode causar perda de dados.

O AppMeasurement detecta automaticamente o estado online do dispositivo. Você pode usar o `forceOffline()` método para forçar o AppMeasurement a tratar ocorrências como se o dispositivo estivesse offline. Esse método não aceita argumentos e não retorna nenhum valor. Seu único objetivo é substituir o estado online no AppMeasurement.

## Forçar off-line no lançamento da plataforma Adobe Experience

Não há um campo dedicado no Launch para usar essa variável. Use o editor de código personalizado, após a sintaxe do AppMeasurement.

## s.forceOffline() no AppMeasurement e Iniciar editor de código personalizado

Você pode chamar o `s.forceOffline()` método em qualquer lugar na sua implementação depois de instanciar o objeto do Analytics.

```js
s.forceOffline();
```
