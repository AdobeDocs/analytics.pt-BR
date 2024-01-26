---
title: forceOffline
description: Defina manualmente o estado online do AppMeasurement.
feature: Variables
exl-id: 2e48bdf6-7de7-4976-86dd-ef3d558769c7
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 80%

---

# forceOffline

O método `forceOffline()` permite substituir o estado do AppMeasurement detectado automaticamente.

>[!WARNING]
>
>Use essa função somente quando [`trackOffline`](../config-vars/trackoffline.md) estiver ativada. Usar essa função fora do rastreamento offline pode causar perda de dados.

O AppMeasurement detecta automaticamente o estado online do dispositivo. Você pode usar o método `forceOffline()` para forçar o AppMeasurement a tratar ocorrências como se o dispositivo estivesse offline. Esse método não aceita argumentos e não retorna nenhum valor. Seu único objetivo é substituir o estado online no AppMeasurement.

## Forçar o uso offline do SDK da Web

O SDK da Web não oferece suporte ao rastreamento offline.

## Forçar o uso offline da extensão do Adobe Analytics

Não há um campo dedicado na extensão do Adobe Analytics para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.forceOffline() no AppMeasurement e no editor de código personalizado da extensão do Analytics

Você pode chamar o método `s.forceOffline()` em qualquer lugar na sua implementação depois de instanciar o objeto do Analytics.

```js
s.forceOffline();
```
