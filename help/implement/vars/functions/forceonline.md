---
title: forceOnline
description: Defina manualmente o estado online do AppMeasurement.
exl-id: 318408bf-bec6-49aa-a762-9d2eebab233e
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
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
