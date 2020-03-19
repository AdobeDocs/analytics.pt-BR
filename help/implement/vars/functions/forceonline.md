---
title: forceOnline
description: Defina manualmente o estado online do AppMeasurement.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# forceOnline

O `forceOnline()` método permite substituir o estado detectado automaticamente do AppMeasurement.

> [!IMPORTANT] Use este método somente quando [`trackOffline`](../config-vars/trackoffline.md) estiver ativado. Usar essa função fora do rastreamento offline pode causar perda de dados.

O AppMeasurement detecta automaticamente o estado online do dispositivo. Você pode usar o `forceOnline()` método para forçar o AppMeasurement a tratar as ocorrências como se o dispositivo estivesse online. Esse método não aceita argumentos e não retorna nenhum valor. Seu único objetivo é substituir o estado online no AppMeasurement.

## Forçar on-line no lançamento da plataforma Adobe Experience

Não há um campo dedicado no Launch para usar essa variável. Use o editor de código personalizado, após a sintaxe do AppMeasurement.

## s.forceOnline() no AppMeasurement e Iniciar editor de código personalizado

Você pode chamar o `s.forceOnline()` método em qualquer lugar na sua implementação depois de instanciar o objeto do Analytics.

```js
s.forceOnline();
```
